# Chapter 15: Live Project – Complete EKS Cluster Deployment

## Prerequisites
- All previous chapters completed (especially Modules, Workspaces, State Management)
- AWS account with appropriate permissions
- kubectl installed locally
- AWS CLI configured
- Basic Kubernetes knowledge (pods, services, deployments)
- Estimated reading time: 70-90 minutes

## 1. Introduction

### Why This Topic Matters

This is where theory meets reality. We're deploying a production-grade Amazon EKS (Elastic Kubernetes Service) cluster using Terraform. This is a **real project** that companies use in production. By the end, you'll have:

- Complete EKS cluster with worker nodes
- VPC with proper networking
- IAM roles and policies configured
- Security groups properly set up
- kubectl configured to manage cluster
- Sample application deployed
- Load balancer exposing application
- Complete infrastructure as code

**The Reality:**
```
This one project combines:
✓ VPC + Subnets (Chapter 11)
✓ IAM roles (AWS knowledge)
✓ EC2 instances (Chapter 11)
✓ Kubernetes (EKS)
✓ Load balancers
✓ Security groups
✓ State management (Chapter 13)
✓ Modules (Chapter 14)

Value: $20,000+ annual infrastructure
Code: ~500 lines of Terraform
```

### What You'll Learn

- EKS cluster architecture
- VPC design for Kubernetes
- IAM roles for EKS
- Node groups and autoscaling
- Deploying applications to EKS
- Exposing services with Load Balancer
- Complete CI/CD integration points
- Production best practices
- Cost optimization strategies
- Troubleshooting EKS issues

### The Problem Being Solved

**Manual Approach (Old Way):**
```
1. Create VPC manually (30 minutes)
2. Create subnets manually (20 minutes)
3. Create internet gateway (5 minutes)
4. Create NAT gateway (10 minutes)
5. Configure route tables (15 minutes)
6. Create IAM roles (20 minutes)
7. Create security groups (15 minutes)
8. Create EKS cluster via console (30 minutes)
9. Wait for cluster (10-15 minutes)
10. Create node group (20 minutes)
11. Wait for nodes (10 minutes)
12. Configure kubectl (10 minutes)

Total: ~3 hours
Repeatability: Low
Version control: None
Documentation: Manual
```

**Terraform Approach (Modern Way):**
```bash
terraform apply

Total: 20 minutes
Repeatability: 100%
Version control: Git
Documentation: Code itself
```

### Project Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                      AWS Region (us-east-1)                  │
│                                                              │
│  ┌────────────────────────────────────────────────────┐    │
│  │              VPC (10.0.0.0/16)                     │    │
│  │                                                     │    │
│  │  ┌─────────────────┐      ┌─────────────────┐    │    │
│  │  │  Public Subnet  │      │  Public Subnet  │    │    │
│  │  │   us-east-1a    │      │   us-east-1b    │    │    │
│  │  │  10.0.1.0/24    │      │  10.0.2.0/24    │    │    │
│  │  │                 │      │                 │    │    │
│  │  │  [NAT Gateway]  │      │  [NAT Gateway]  │    │    │
│  │  └─────────────────┘      └─────────────────┘    │    │
│  │           │                         │             │    │
│  │  ┌─────────────────┐      ┌─────────────────┐    │    │
│  │  │ Private Subnet  │      │ Private Subnet  │    │    │
│  │  │   us-east-1a    │      │   us-east-1b    │    │    │
│  │  │  10.0.11.0/24   │      │  10.0.12.0/24   │    │    │
│  │  │                 │      │                 │    │    │
│  │  │  [EKS Node 1]   │      │  [EKS Node 2]   │    │    │
│  │  │  [EKS Node 3]   │      │  [EKS Node 4]   │    │    │
│  │  └─────────────────┘      └─────────────────┘    │    │
│  │           │                         │             │    │
│  │           └────────┬────────────────┘             │    │
│  │                    │                              │    │
│  │           ┌────────▼────────┐                    │    │
│  │           │  EKS Cluster    │                    │    │
│  │           │  Control Plane  │                    │    │
│  │           └─────────────────┘                    │    │
│  │                                                   │    │
│  └────────────────────────────────────────────────────┘    │
│                                                              │
│  ┌─────────────────────────────────────┐                   │
│  │    Application Load Balancer         │                   │
│  │    (Created by Kubernetes)           │                   │
│  └─────────────────────────────────────┘                   │
│                     │                                        │
└─────────────────────┼────────────────────────────────────────┘
                      │
                      ▼
                 [Internet]
```

---

## 2. Concept Overview

### What is EKS?

**Amazon EKS (Elastic Kubernetes Service):**
- Managed Kubernetes service
- AWS manages control plane (master nodes)
- You manage worker nodes
- Highly available (multi-AZ)
- Integrates with AWS services (IAM, VPC, ELB, etc.)

**Key Components:**
```
1. Control Plane (Managed by AWS)
   - API Server
   - etcd (cluster state)
   - Scheduler
   - Controller Manager

2. Data Plane (Managed by You)
   - Worker Nodes (EC2 instances)
   - Pods (containers)
   - Applications

3. Networking
   - VPC
   - Subnets (public + private)
   - NAT Gateways
   - Internet Gateway
   - Security Groups

4. IAM
   - Cluster Role
   - Node Role
   - Service Accounts
```

### Why Private Subnets for Nodes?

```
Security Best Practice:

Public Subnet:
├─ NAT Gateway (allows outbound internet)
└─ Load Balancer (receives inbound traffic)

Private Subnet:
├─ EKS Nodes (no direct internet access)
└─ Pods (isolated from internet)

Benefits:
✓ Nodes can't be directly accessed from internet
✓ Pods pull images via NAT (outbound only)
✓ Load Balancer handles inbound traffic
✓ Defense in depth
```

---

## 3. Core Theory

### EKS Networking Requirements

**Subnet Requirements:**
```
1. Public Subnets (2+ across AZs)
   - For Load Balancers
   - For NAT Gateways
   - Tag: kubernetes.io/role/elb = 1

2. Private Subnets (2+ across AZs)
   - For EKS Nodes
   - For Pods
   - Tag: kubernetes.io/role/internal-elb = 1

3. Both must be tagged:
   - kubernetes.io/cluster/<cluster-name> = shared
```

**CIDR Planning:**
```
VPC: 10.0.0.0/16 (65,536 IPs)

Public Subnets:
├─ us-east-1a: 10.0.1.0/24 (256 IPs)
└─ us-east-1b: 10.0.2.0/24 (256 IPs)

Private Subnets:
├─ us-east-1a: 10.0.11.0/24 (256 IPs)
└─ us-east-1b: 10.0.12.0/24 (256 IPs)

Reserved by AWS: 5 IPs per subnet
Usable per subnet: 251 IPs
```

### IAM Roles for EKS

**Cluster Role (for EKS control plane):**
```
Allows EKS to:
- Manage EC2 instances
- Manage ENIs (network interfaces)
- Write logs to CloudWatch
- Call AWS APIs
```

**Node Role (for worker nodes):**
```
Allows nodes to:
- Join EKS cluster
- Pull container images from ECR
- Write logs to CloudWatch
- Access AWS services (S3, etc.)
```

---

## 4. Step-by-Step Walkthrough

### Complete EKS Project Structure

```
eks-project/
├── main.tf                 # Root module
├── variables.tf            # Input variables
├── outputs.tf              # Outputs
├── vpc.tf                  # VPC resources
├── eks-cluster.tf          # EKS cluster
├── eks-node-group.tf       # EKS worker nodes
├── security-groups.tf      # Security groups
├── iam.tf                  # IAM roles
├── terraform.tfvars        # Variable values
└── kubernetes-app/         # Sample application
    ├── deployment.yaml
    └── service.yaml
```

### Step 1: VPC Configuration

**vpc.tf:**
```hcl
# VPC
resource "aws_vpc" "main" {
  cidr_block           = var.vpc_cidr
  enable_dns_hostnames = true
  enable_dns_support   = true
  
  tags = {
    Name = "${var.cluster_name}-vpc"
    "kubernetes.io/cluster/${var.cluster_name}" = "shared"
  }
}

# Internet Gateway
resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id
  
  tags = {
    Name = "${var.cluster_name}-igw"
  }
}

# Public Subnets
resource "aws_subnet" "public" {
  count = length(var.availability_zones)
  
  vpc_id                  = aws_vpc.main.id
  cidr_block              = cidrsubnet(var.vpc_cidr, 8, count.index)
  availability_zone       = var.availability_zones[count.index]
  map_public_ip_on_launch = true
  
  tags = {
    Name = "${var.cluster_name}-public-${var.availability_zones[count.index]}"
    "kubernetes.io/cluster/${var.cluster_name}" = "shared"
    "kubernetes.io/role/elb"                     = "1"
  }
}

# Private Subnets
resource "aws_subnet" "private" {
  count = length(var.availability_zones)
  
  vpc_id            = aws_vpc.main.id
  cidr_block        = cidrsubnet(var.vpc_cidr, 8, count.index + 10)
  availability_zone = var.availability_zones[count.index]
  
  tags = {
    Name = "${var.cluster_name}-private-${var.availability_zones[count.index]}"
    "kubernetes.io/cluster/${var.cluster_name}" = "shared"
    "kubernetes.io/role/internal-elb"           = "1"
  }
}

# Elastic IPs for NAT Gateways
resource "aws_eip" "nat" {
  count  = length(var.availability_zones)
  domain = "vpc"
  
  tags = {
    Name = "${var.cluster_name}-nat-eip-${count.index + 1}"
  }
  
  depends_on = [aws_internet_gateway.main]
}

# NAT Gateways
resource "aws_nat_gateway" "main" {
  count = length(var.availability_zones)
  
  allocation_id = aws_eip.nat[count.index].id
  subnet_id     = aws_subnet.public[count.index].id
  
  tags = {
    Name = "${var.cluster_name}-nat-${var.availability_zones[count.index]}"
  }
  
  depends_on = [aws_internet_gateway.main]
}

# Route Table for Public Subnets
resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id
  
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.main.id
  }
  
  tags = {
    Name = "${var.cluster_name}-public-rt"
  }
}

# Route Table Association for Public Subnets
resource "aws_route_table_association" "public" {
  count = length(var.availability_zones)
  
  subnet_id      = aws_subnet.public[count.index].id
  route_table_id = aws_route_table.public.id
}

# Route Tables for Private Subnets (one per AZ)
resource "aws_route_table" "private" {
  count = length(var.availability_zones)
  
  vpc_id = aws_vpc.main.id
  
  route {
    cidr_block     = "0.0.0.0/0"
    nat_gateway_id = aws_nat_gateway.main[count.index].id
  }
  
  tags = {
    Name = "${var.cluster_name}-private-rt-${var.availability_zones[count.index]}"
  }
}

# Route Table Association for Private Subnets
resource "aws_route_table_association" "private" {
  count = length(var.availability_zones)
  
  subnet_id      = aws_subnet.private[count.index].id
  route_table_id = aws_route_table.private[count.index].id
}
```

### Step 2: IAM Roles

**iam.tf:**
```hcl
# EKS Cluster IAM Role
resource "aws_iam_role" "cluster" {
  name = "${var.cluster_name}-cluster-role"
  
  assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [{
      Action = "sts:AssumeRole"
      Effect = "Allow"
      Principal = {
        Service = "eks.amazonaws.com"
      }
    }]
  })
}

# Attach required policies to cluster role
resource "aws_iam_role_policy_attachment" "cluster_AmazonEKSClusterPolicy" {
  policy_arn = "arn:aws:iam::aws:policy/AmazonEKSClusterPolicy"
  role       = aws_iam_role.cluster.name
}

resource "aws_iam_role_policy_attachment" "cluster_AmazonEKSVPCResourceController" {
  policy_arn = "arn:aws:iam::aws:policy/AmazonEKSVPCResourceController"
  role       = aws_iam_role.cluster.name
}

# EKS Node IAM Role
resource "aws_iam_role" "node" {
  name = "${var.cluster_name}-node-role"
  
  assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [{
      Action = "sts:AssumeRole"
      Effect = "Allow"
      Principal = {
        Service = "ec2.amazonaws.com"
      }
    }]
  })
}

# Attach required policies to node role
resource "aws_iam_role_policy_attachment" "node_AmazonEKSWorkerNodePolicy" {
  policy_arn = "arn:aws:iam::aws:policy/AmazonEKSWorkerNodePolicy"
  role       = aws_iam_role.node.name
}

resource "aws_iam_role_policy_attachment" "node_AmazonEKS_CNI_Policy" {
  policy_arn = "arn:aws:iam::aws:policy/AmazonEKS_CNI_Policy"
  role       = aws_iam_role.node.name
}

resource "aws_iam_role_policy_attachment" "node_AmazonEC2ContainerRegistryReadOnly" {
  policy_arn = "arn:aws:iam::aws:policy/AmazonEC2ContainerRegistryReadOnly"
  role       = aws_iam_role.node.name
}
```

### Step 3: Security Groups

**security-groups.tf:**
```hcl
# Security Group for EKS Cluster
resource "aws_security_group" "cluster" {
  name        = "${var.cluster_name}-cluster-sg"
  description = "Security group for EKS cluster"
  vpc_id      = aws_vpc.main.id
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  tags = {
    Name = "${var.cluster_name}-cluster-sg"
  }
}

# Security Group for EKS Nodes
resource "aws_security_group" "node" {
  name        = "${var.cluster_name}-node-sg"
  description = "Security group for EKS nodes"
  vpc_id      = aws_vpc.main.id
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  tags = {
    Name                                        = "${var.cluster_name}-node-sg"
    "kubernetes.io/cluster/${var.cluster_name}" = "owned"
  }
}

# Allow nodes to communicate with cluster API
resource "aws_security_group_rule" "cluster_ingress_node_https" {
  type                     = "ingress"
  from_port                = 443
  to_port                  = 443
  protocol                 = "tcp"
  security_group_id        = aws_security_group.cluster.id
  source_security_group_id = aws_security_group.node.id
}

# Allow cluster to communicate with nodes
resource "aws_security_group_rule" "node_ingress_cluster" {
  type                     = "ingress"
  from_port                = 1025
  to_port                  = 65535
  protocol                 = "tcp"
  security_group_id        = aws_security_group.node.id
  source_security_group_id = aws_security_group.cluster.id
}

# Allow nodes to communicate with each other
resource "aws_security_group_rule" "node_ingress_self" {
  type              = "ingress"
  from_port         = 0
  to_port           = 65535
  protocol          = "-1"
  security_group_id = aws_security_group.node.id
  self              = true
}
```

### Step 4: EKS Cluster

**eks-cluster.tf:**
```hcl
resource "aws_eks_cluster" "main" {
  name     = var.cluster_name
  role_arn = aws_iam_role.cluster.arn
  version  = var.kubernetes_version
  
  vpc_config {
    subnet_ids              = concat(aws_subnet.public[*].id, aws_subnet.private[*].id)
    security_group_ids      = [aws_security_group.cluster.id]
    endpoint_private_access = true
    endpoint_public_access  = true
  }
  
  enabled_cluster_log_types = ["api", "audit", "authenticator", "controllerManager", "scheduler"]
  
  depends_on = [
    aws_iam_role_policy_attachment.cluster_AmazonEKSClusterPolicy,
    aws_iam_role_policy_attachment.cluster_AmazonEKSVPCResourceController,
  ]
  
  tags = {
    Name = var.cluster_name
  }
}
```

### Step 5: EKS Node Group

**eks-node-group.tf:**
```hcl
resource "aws_eks_node_group" "main" {
  cluster_name    = aws_eks_cluster.main.name
  node_group_name = "${var.cluster_name}-node-group"
  node_role_arn   = aws_iam_role.node.arn
  subnet_ids      = aws_subnet.private[*].id
  
  instance_types = var.node_instance_types
  
  scaling_config {
    desired_size = var.node_desired_size
    max_size     = var.node_max_size
    min_size     = var.node_min_size
  }
  
  update_config {
    max_unavailable = 1
  }
  
  depends_on = [
    aws_iam_role_policy_attachment.node_AmazonEKSWorkerNodePolicy,
    aws_iam_role_policy_attachment.node_AmazonEKS_CNI_Policy,
    aws_iam_role_policy_attachment.node_AmazonEC2ContainerRegistryReadOnly,
  ]
  
  tags = {
    Name = "${var.cluster_name}-node-group"
  }
}
```

### Step 6: Variables

**variables.tf:**
```hcl
variable "cluster_name" {
  description = "Name of the EKS cluster"
  type        = string
  default     = "my-eks-cluster"
}

variable "kubernetes_version" {
  description = "Kubernetes version"
  type        = string
  default     = "1.28"
}

variable "region" {
  description = "AWS region"
  type        = string
  default     = "us-east-1"
}

variable "vpc_cidr" {
  description = "CIDR block for VPC"
  type        = string
  default     = "10.0.0.0/16"
}

variable "availability_zones" {
  description = "Availability zones"
  type        = list(string)
  default     = ["us-east-1a", "us-east-1b"]
}

variable "node_instance_types" {
  description = "Instance types for node group"
  type        = list(string)
  default     = ["t3.medium"]
}

variable "node_desired_size" {
  description = "Desired number of nodes"
  type        = number
  default     = 2
}

variable "node_min_size" {
  description = "Minimum number of nodes"
  type        = number
  default     = 1
}

variable "node_max_size" {
  description = "Maximum number of nodes"
  type        = number
  default     = 4
}
```

### Step 7: Outputs

**outputs.tf:**
```hcl
output "cluster_id" {
  description = "EKS cluster ID"
  value       = aws_eks_cluster.main.id
}

output "cluster_endpoint" {
  description = "Endpoint for EKS control plane"
  value       = aws_eks_cluster.main.endpoint
}

output "cluster_security_group_id" {
  description = "Security group ID attached to the EKS cluster"
  value       = aws_eks_cluster.main.vpc_config[0].cluster_security_group_id
}

output "cluster_name" {
  description = "Kubernetes Cluster Name"
  value       = aws_eks_cluster.main.name
}

output "cluster_certificate_authority_data" {
  description = "Base64 encoded certificate data required to communicate with the cluster"
  value       = aws_eks_cluster.main.certificate_authority[0].data
  sensitive   = true
}

output "region" {
  description = "AWS region"
  value       = var.region
}

output "configure_kubectl" {
  description = "Command to configure kubectl"
  value       = "aws eks update-kubeconfig --region ${var.region} --name ${aws_eks_cluster.main.name}"
}
```

### Step 8: Main Configuration

**main.tf:**
```hcl
terraform {
  required_version = ">= 1.5.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
  
  backend "s3" {
    bucket         = "my-terraform-state-bucket"
    key            = "eks/terraform.tfstate"
    region         = "us-east-1"
    dynamodb_table = "terraform-locks"
    encrypt        = true
  }
}

provider "aws" {
  region = var.region
}
```

### Step 9: Deploy Infrastructure

```bash
# Initialize Terraform
terraform init

# Validate configuration
terraform validate

# Plan deployment
terraform plan

# Apply (creates infrastructure)
terraform apply

# Output:
# ...
# Apply complete! Resources: 47 added, 0 changed, 0 destroyed.
# 
# Outputs:
# cluster_endpoint = "https://ABCDEF123.gr7.us-east-1.eks.amazonaws.com"
# cluster_name = "my-eks-cluster"
# configure_kubectl = "aws eks update-kubeconfig --region us-east-1 --name my-eks-cluster"
```

**Wait Time:**
- Cluster creation: ~10-15 minutes
- Node group creation: ~5-10 minutes
- Total: ~15-25 minutes

### Step 10: Configure kubectl

```bash
# Update kubeconfig
aws eks update-kubeconfig --region us-east-1 --name my-eks-cluster

# Verify connection
kubectl get nodes

# Output:
# NAME                          STATUS   ROLES    AGE   VERSION
# ip-10-0-11-123.ec2.internal   Ready    <none>   5m    v1.28.0-eks-abc123
# ip-10-0-12-234.ec2.internal   Ready    <none>   5m    v1.28.0-eks-abc123

# Check cluster info
kubectl cluster-info

# Output:
# Kubernetes control plane is running at https://ABCDEF123.gr7.us-east-1.eks.amazonaws.com
```

### Step 11: Deploy Sample Application

**kubernetes-app/deployment.yaml:**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.25
        ports:
        - containerPort: 80
        resources:
          requests:
            memory: "64Mi"
            cpu: "250m"
          limits:
            memory: "128Mi"
            cpu: "500m"
```

**kubernetes-app/service.yaml:**
```yaml
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  type: LoadBalancer
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
```

**Deploy:**
```bash
# Apply deployment
kubectl apply -f kubernetes-app/deployment.yaml

# Output:
# deployment.apps/nginx-deployment created

# Check pods
kubectl get pods

# Output:
# NAME                                READY   STATUS    RESTARTS   AGE
# nginx-deployment-5d59cd8976-2xqfg   1/1     Running   0          30s
# nginx-deployment-5d59cd8976-8klpn   1/1     Running   0          30s
# nginx-deployment-5d59cd8976-wr4kb   1/1     Running   0          30s

# Apply service
kubectl apply -f kubernetes-app/service.yaml

# Output:
# service/nginx-service created

# Get service (wait for LoadBalancer)
kubectl get service nginx-service

# Output:
# NAME            TYPE           CLUSTER-IP       EXTERNAL-IP                                                              PORT(S)        AGE
# nginx-service   LoadBalancer   172.20.123.456   a1b2c3d4e5f6g7h8.us-east-1.elb.amazonaws.com   80:32145/TCP   2m

# Test application
curl http://a1b2c3d4e5f6g7h8.us-east-1.elb.amazonaws.com

# Output:
# <!DOCTYPE html>
# <html>
# <head>
# <title>Welcome to nginx!</title>
# ...
```

---

## 5. Practical Examples

### Example 1: Adding Application Load Balancer Controller

```bash
# Install AWS Load Balancer Controller
kubectl apply -k "github.com/aws/eks-charts/stable/aws-load-balancer-controller//crds?ref=master"

helm repo add eks https://aws.github.io/eks-charts
helm repo update

helm install aws-load-balancer-controller eks/aws-load-balancer-controller \
  -n kube-system \
  --set clusterName=my-eks-cluster \
  --set serviceAccount.create=false \
  --set serviceAccount.name=aws-load-balancer-controller
```

### Example 2: Deploying Multi-Tier Application

**frontend-deployment.yaml:**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: frontend
spec:
  replicas: 3
  selector:
    matchLabels:
      app: frontend
  template:
    metadata:
      labels:
        app: frontend
    spec:
      containers:
      - name: frontend
        image: myapp/frontend:v1.0
        ports:
        - containerPort: 3000
        env:
        - name: BACKEND_URL
          value: "http://backend-service"
```

**backend-deployment.yaml:**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: backend
spec:
  replicas: 2
  selector:
    matchLabels:
      app: backend
  template:
    metadata:
      labels:
        app: backend
    spec:
      containers:
      - name: backend
        image: myapp/backend:v1.0
        ports:
        - containerPort: 8080
        env:
        - name: DB_HOST
          value: "database-service"
```

---

## 6. Deep Dive

### Cost Optimization

**EKS Costs:**
```
Control Plane: $0.10/hour = $73/month (fixed)
t3.medium nodes: $0.0416/hour each
NAT Gateway: $0.045/hour per AZ = $32.40/month per NAT

Example monthly cost (2 AZs, 2 t3.medium nodes):
- Control Plane: $73
- Nodes: 2 × $0.0416 × 730 hours = $60.74
- NAT Gateways: 2 × $32.40 = $64.80
- Data transfer: ~$20

Total: ~$218/month minimum
```

**Cost Reduction Strategies:**
```
1. Spot Instances for nodes (70% savings)
2. Single NAT Gateway (not recommended for prod)
3. Fargate instead of node groups (pay per pod)
4. Autoscaling to scale down during off-hours
5. Reserved Instances for predictable workloads
```

---

## 7. Trade-offs & Pitfalls

### Pitfall 1: Public nodes
```
Bad: Nodes in public subnets
Risk: Direct internet access, security vulnerability

Good: Nodes in private subnets with NAT
```

### Pitfall 2: No node autoscaling
```
Manual: Fixed node count
Problem: Wasted money or insufficient capacity

Auto: Cluster Autoscaler
Benefit: Scales based on pod demand
```

---

## 8. Mental Models & Analogies

**EKS = Apartment Building**
```
Control Plane = Building Management (AWS manages)
Worker Nodes = Apartments (You manage)
Pods = Residents (Your applications)
Load Balancer = Main Entrance (Routes visitors)
VPC = Gated Community (Private network)
```

---

## 9. Troubleshooting Guide

### Problem: Nodes not joining cluster
```bash
# Check node group status
aws eks describe-nodegroup --cluster-name my-eks-cluster --nodegroup-name my-node-group

# Check IAM roles
kubectl get nodes
# If empty, check IAM role permissions
```

### Problem: Pods can't pull images
```bash
# Check ECR permissions in node IAM role
aws iam list-attached-role-policies --role-name my-eks-cluster-node-role

# Should include:
# - AmazonEC2ContainerRegistryReadOnly
```

---

## 10. Frequently Asked Questions

**Q1: How long does EKS take to create?**
**A:** 15-25 minutes total.

**Q2: Can I use Fargate instead of node groups?**
**A:** Yes! Fargate = serverless nodes.

**Q3: How do I upgrade Kubernetes version?**
**A:** Update `kubernetes_version` variable and `terraform apply`.

**Q4: What's the minimum node size?**
**A:** 1 node, but 2+ recommended for high availability.

**Q5: How do I add more nodes?**
**A:** Increase `node_desired_size` in variables.

---

## 11. Key Takeaways

✅ **EKS** = Managed Kubernetes on AWS
✅ **Private subnets** = Security best practice for nodes
✅ **IAM roles** = Essential for cluster and nodes
✅ **kubectl** = Manage cluster after creation
✅ **LoadBalancer** = Exposes apps to internet
✅ **47 resources** = Created by this project
✅ **15-25 minutes** = Deployment time
✅ **$200-300/month** = Minimum cost
✅ **Production-ready** = This is real infrastructure
✅ **Terraform** = Makes it repeatable and manageable

---

## 12. Practice Exercises

### Exercise 1: Deploy Custom App
Create your own Docker image and deploy to EKS.

### Exercise 2: Add Monitoring
Install Prometheus and Grafana on cluster.

### Exercise 3: Implement Autoscaling
Add Cluster Autoscaler and Horizontal Pod Autoscaler.

### Exercise 4: Multi-Environment
Use workspaces for dev/prod EKS clusters.

### Exercise 5: Add CI/CD
Integrate with GitHub Actions for automated deployments.

---

## 13. Further Reading

- AWS EKS Documentation
- Kubernetes Official Documentation
- EKS Best Practices Guide
- terraform-aws-modules/eks

---

*🎉 Congratulations! You've deployed a production-grade EKS cluster!*
*This is a $20,000+ annual infrastructure managed entirely as code!*
