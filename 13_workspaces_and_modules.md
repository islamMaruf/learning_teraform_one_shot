# Chapter 13: Workspaces & Modules – Scaling Terraform for Production

## Prerequisites
- State management understanding (Chapter 13)
- Variables and expressions knowledge (Chapter 12)
- Terraform workflow mastery (Chapter 10)
- Estimated reading time: 55-60 minutes

## 1. Introduction

### Why This Topic Matters

Workspaces and modules are how you scale Terraform from "toy projects" to "production-grade infrastructure management." Workspaces let you manage multiple environments with the same code. Modules let you create reusable, composable infrastructure components. Together, they're the difference between amateur and professional Terraform usage.

**The Reality:**
```
Amateur: Copy-paste code for each environment, no reusability
Professional: One module, used across all environments and projects
```

**The Transformation:**
- **Before:** 10 projects × 3 environments = 30 separate codebases
- **After:** 1 module + workspaces = infinite reusability

### What You'll Learn

- What workspaces are and when to use them
- Workspace commands and workflow
- Module fundamentals and structure
- Creating custom modules
- Using public modules from Terraform Registry
- Module composition patterns
- Input variables and outputs for modules
- Module versioning and best practices
- Workspace vs multiple state files
- Real-world module examples
- Publishing modules to registry

### The Problem Being Solved

**Scenario 1: Multiple Environments (Workspaces)**

**Without Workspaces:**
```bash
# Separate directories for each environment
project/
├── dev/
│   ├── main.tf (500 lines)
│   └── terraform.tfstate
├── staging/
│   ├── main.tf (500 lines, 95% duplicate)
│   └── terraform.tfstate
└── prod/
    ├── main.tf (500 lines, 95% duplicate)
    └── terraform.tfstate

# Result: Code duplication, maintenance nightmare
```

**With Workspaces:**
```bash
project/
├── main.tf (500 lines, ONE copy)
└── terraform.tfstate.d/
    ├── dev/
    │   └── terraform.tfstate
    ├── staging/
    │   └── terraform.tfstate
    └── prod/
        └── terraform.tfstate

# Commands:
terraform workspace select dev
terraform apply  # Uses dev state

terraform workspace select prod
terraform apply  # Uses prod state

# Result: DRY principle, single codebase
```

**Scenario 2: Reusable Components (Modules)**

**Without Modules:**
```hcl
# Every project duplicates VPC creation code
# project1/main.tf (200 lines of VPC code)
# project2/main.tf (200 lines of VPC code)
# project3/main.tf (200 lines of VPC code)

# Result: Copy-paste hell, inconsistencies
```

**With Modules:**
```hcl
# Create once, use everywhere
# modules/vpc/main.tf (200 lines)

# project1/main.tf
module "vpc" {
  source = "../modules/vpc"
  cidr   = "10.0.0.0/16"
}

# project2/main.tf
module "vpc" {
  source = "../modules/vpc"
  cidr   = "10.1.0.0/16"
}

# Result: Reusability, consistency, maintainability
```

---

## 2. Concept Overview

### Workspaces Explained

**Simple Definition:**
Workspaces allow you to manage multiple instances of the same infrastructure configuration with separate state files.

**Key Concept:**
```
Same code + Different workspace = Different infrastructure

Example:
- Code: Creates VPC + EC2
- dev workspace: Creates dev VPC + dev EC2
- prod workspace: Creates prod VPC + prod EC2
```

**Default Workspace:**
```
Every Terraform project starts with "default" workspace
Can't delete default workspace
Typically used for development or unused
```

### Modules Explained

**Simple Definition:**
A module is a container for multiple resources that are used together. It's a reusable Terraform configuration package.

**Types of Modules:**

```
1. Root Module
   └─ Your main Terraform configuration
   └─ Where you run terraform apply

2. Child Modules
   └─ Reusable components called by root module
   └─ Example: VPC module, EC2 module

3. Published Modules
   └─ Public modules on Terraform Registry
   └─ Example: terraform-aws-modules/vpc/aws
```

**Module Analogy:**
```
Module = Function in programming

# Function definition
def create_server(name, size):
    server = Server(name=name, size=size)
    return server

# Function call
server1 = create_server("web", "large")
server2 = create_server("db", "xlarge")

# Terraform equivalent
module "web_server" {
  source = "./modules/server"
  name   = "web"
  size   = "large"
}

module "db_server" {
  source = "./modules/server"
  name   = "db"
  size   = "xlarge"
}
```

---

## 3. Core Theory

### Workspaces

**Workspace Commands:**
```bash
# List workspaces
terraform workspace list

# Create new workspace
terraform workspace new dev

# Select workspace
terraform workspace select dev

# Show current workspace
terraform workspace show

# Delete workspace (must be empty)
terraform workspace delete old-env
```

**Workspace State Structure:**
```
# Local backend
project/
├── terraform.tfstate.d/
│   ├── dev/
│   │   └── terraform.tfstate
│   ├── staging/
│   │   └── terraform.tfstate
│   └── prod/
│       └── terraform.tfstate
└── main.tf

# S3 backend
s3://bucket/
├── env:/dev/project/terraform.tfstate
├── env:/staging/project/terraform.tfstate
└── env:/prod/project/terraform.tfstate
```

**Using Workspace Name in Code:**
```hcl
# Access current workspace name
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Name        = "${terraform.workspace}-web-server"
    Environment = terraform.workspace
  }
}

# Conditional based on workspace
locals {
  instance_type = terraform.workspace == "prod" ? "t2.large" : "t2.micro"
  instance_count = terraform.workspace == "prod" ? 5 : 2
}

resource "aws_instance" "app" {
  count         = local.instance_count
  instance_type = local.instance_type
  ami           = "ami-12345"
  
  tags = {
    Name = "${terraform.workspace}-app-${count.index + 1}"
  }
}
```

**Workspace Workflow:**
```bash
# Create workspaces
terraform workspace new dev
terraform workspace new staging
terraform workspace new prod

# Deploy to dev
terraform workspace select dev
terraform apply

# Deploy to staging
terraform workspace select staging
terraform apply

# Deploy to prod
terraform workspace select prod
terraform apply

# Each has separate state!
```

### Modules

**Module Structure:**
```
modules/
└── vpc/
    ├── main.tf       # Resources
    ├── variables.tf  # Input variables
    ├── outputs.tf    # Output values
    └── README.md     # Documentation
```

**Basic Module Example:**

**modules/vpc/variables.tf:**
```hcl
variable "vpc_cidr" {
  type        = string
  description = "CIDR block for VPC"
}

variable "environment" {
  type        = string
  description = "Environment name"
}

variable "availability_zones" {
  type        = list(string)
  description = "List of availability zones"
}
```

**modules/vpc/main.tf:**
```hcl
resource "aws_vpc" "main" {
  cidr_block           = var.vpc_cidr
  enable_dns_hostnames = true
  enable_dns_support   = true
  
  tags = {
    Name        = "${var.environment}-vpc"
    Environment = var.environment
  }
}

resource "aws_subnet" "public" {
  count             = length(var.availability_zones)
  vpc_id            = aws_vpc.main.id
  cidr_block        = cidrsubnet(var.vpc_cidr, 8, count.index)
  availability_zone = var.availability_zones[count.index]
  
  map_public_ip_on_launch = true
  
  tags = {
    Name        = "${var.environment}-public-subnet-${count.index + 1}"
    Environment = var.environment
  }
}

resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id
  
  tags = {
    Name        = "${var.environment}-igw"
    Environment = var.environment
  }
}
```

**modules/vpc/outputs.tf:**
```hcl
output "vpc_id" {
  description = "ID of the VPC"
  value       = aws_vpc.main.id
}

output "vpc_cidr" {
  description = "CIDR block of the VPC"
  value       = aws_vpc.main.cidr_block
}

output "public_subnet_ids" {
  description = "IDs of public subnets"
  value       = aws_subnet.public[*].id
}

output "internet_gateway_id" {
  description = "ID of the internet gateway"
  value       = aws_internet_gateway.main.id
}
```

**Using the Module:**

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
}

provider "aws" {
  region = "us-east-1"
}

# Call VPC module
module "vpc" {
  source = "./modules/vpc"
  
  vpc_cidr           = "10.0.0.0/16"
  environment        = "production"
  availability_zones = ["us-east-1a", "us-east-1b"]
}

# Use module outputs
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  subnet_id     = module.vpc.public_subnet_ids[0]  # Access module output
  
  tags = {
    Name = "web-server"
  }
}

# Output from root module
output "vpc_id" {
  value = module.vpc.vpc_id
}
```

**Initialize and Apply:**
```bash
terraform init    # Downloads module
terraform plan
terraform apply
```

---

## 4. Step-by-Step Walkthrough

### Complete Workspace Example

**Step 1: Create Configuration**
```hcl
# main.tf
terraform {
  required_version = ">= 1.5.0"
  backend "s3" {
    bucket         = "my-terraform-state"
    key            = "project/terraform.tfstate"
    region         = "us-east-1"
    dynamodb_table = "terraform-locks"
  }
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}

# Environment-specific configurations
locals {
  configs = {
    dev = {
      instance_type  = "t2.micro"
      instance_count = 1
      environment    = "development"
    }
    staging = {
      instance_type  = "t2.small"
      instance_count = 2
      environment    = "staging"
    }
    prod = {
      instance_type  = "t2.large"
      instance_count = 5
      environment    = "production"
    }
  }
  
  # Get config for current workspace
  config = local.configs[terraform.workspace]
}

resource "aws_instance" "app" {
  count         = local.config.instance_count
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = local.config.instance_type
  
  tags = {
    Name        = "${terraform.workspace}-app-${count.index + 1}"
    Environment = local.config.environment
    Workspace   = terraform.workspace
  }
}

output "instance_ids" {
  value = aws_instance.app[*].id
}

output "workspace" {
  value = terraform.workspace
}
```

**Step 2: Create and Deploy Workspaces**
```bash
# Initialize
terraform init

# Create dev workspace
terraform workspace new dev
terraform workspace select dev
terraform apply
# Creates 1 t2.micro instance

# Create staging workspace
terraform workspace new staging
terraform workspace select staging
terraform apply
# Creates 2 t2.small instances

# Create prod workspace
terraform workspace new prod
terraform workspace select prod
terraform apply
# Creates 5 t2.large instances

# List all workspaces
terraform workspace list
# Output:
#   default
#   dev
#   staging
# * prod  (current)

# View state per workspace
terraform workspace select dev
terraform output
# Shows dev resources

terraform workspace select prod
terraform output
# Shows prod resources (completely separate!)
```

### Complete Module Example

**Step 1: Create Module Structure**
```bash
mkdir -p modules/web-server
touch modules/web-server/{main.tf,variables.tf,outputs.tf}
```

**Step 2: Define Module**

**modules/web-server/variables.tf:**
```hcl
variable "name" {
  type        = string
  description = "Name prefix for resources"
}

variable "instance_type" {
  type        = string
  description = "EC2 instance type"
  default     = "t2.micro"
}

variable "ami_id" {
  type        = string
  description = "AMI ID for instances"
}

variable "instance_count" {
  type        = number
  description = "Number of instances"
  default     = 1
}

variable "subnet_ids" {
  type        = list(string)
  description = "List of subnet IDs"
}

variable "vpc_id" {
  type        = string
  description = "VPC ID"
}

variable "allowed_cidr_blocks" {
  type        = list(string)
  description = "CIDR blocks allowed to access"
  default     = ["0.0.0.0/0"]
}

variable "tags" {
  type        = map(string)
  description = "Additional tags"
  default     = {}
}
```

**modules/web-server/main.tf:**
```hcl
# Security Group
resource "aws_security_group" "web" {
  name        = "${var.name}-web-sg"
  description = "Security group for ${var.name} web servers"
  vpc_id      = var.vpc_id
  
  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = var.allowed_cidr_blocks
  }
  
  ingress {
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"
    cidr_blocks = var.allowed_cidr_blocks
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  tags = merge(
    {
      Name = "${var.name}-web-sg"
    },
    var.tags
  )
}

# EC2 Instances
resource "aws_instance" "web" {
  count         = var.instance_count
  ami           = var.ami_id
  instance_type = var.instance_type
  subnet_id     = var.subnet_ids[count.index % length(var.subnet_ids)]
  
  vpc_security_group_ids = [aws_security_group.web.id]
  
  user_data = <<-EOF
              #!/bin/bash
              yum update -y
              yum install -y httpd
              systemctl start httpd
              systemctl enable httpd
              echo "<h1>Server ${count.index + 1}</h1>" > /var/www/html/index.html
              EOF
  
  tags = merge(
    {
      Name = "${var.name}-web-${count.index + 1}"
    },
    var.tags
  )
}

# Elastic IPs (optional, only for production)
resource "aws_eip" "web" {
  count    = var.instance_count
  instance = aws_instance.web[count.index].id
  domain   = "vpc"
  
  tags = merge(
    {
      Name = "${var.name}-eip-${count.index + 1}"
    },
    var.tags
  )
}
```

**modules/web-server/outputs.tf:**
```hcl
output "instance_ids" {
  description = "IDs of EC2 instances"
  value       = aws_instance.web[*].id
}

output "private_ips" {
  description = "Private IPs of instances"
  value       = aws_instance.web[*].private_ip
}

output "public_ips" {
  description = "Public IPs (Elastic IPs)"
  value       = aws_eip.web[*].public_ip
}

output "security_group_id" {
  description = "ID of security group"
  value       = aws_security_group.web.id
}

output "instance_details" {
  description = "Detailed instance information"
  value = [
    for i, instance in aws_instance.web : {
      id         = instance.id
      private_ip = instance.private_ip
      public_ip  = aws_eip.web[i].public_ip
      az         = instance.availability_zone
    }
  ]
}
```

**Step 3: Use Module in Root Configuration**

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
}

provider "aws" {
  region = "us-east-1"
}

# Data sources
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

data "aws_vpc" "default" {
  default = true
}

data "aws_subnets" "default" {
  filter {
    name   = "vpc-id"
    values = [data.aws_vpc.default.id]
  }
}

# Call web-server module
module "web_servers" {
  source = "./modules/web-server"
  
  name           = "myapp"
  instance_type  = "t2.small"
  ami_id         = data.aws_ami.amazon_linux.id
  instance_count = 3
  
  vpc_id     = data.aws_vpc.default.id
  subnet_ids = data.aws_subnets.default.ids
  
  allowed_cidr_blocks = ["0.0.0.0/0"]
  
  tags = {
    Environment = "production"
    Project     = "WebApp"
  }
}

# Outputs
output "web_server_ips" {
  description = "Public IPs of web servers"
  value       = module.web_servers.public_ips
}

output "web_server_details" {
  description = "Detailed web server information"
  value       = module.web_servers.instance_details
}
```

**Step 4: Deploy**
```bash
terraform init
terraform plan
terraform apply

# Output:
# web_server_ips = [
#   "54.123.45.67",
#   "54.123.45.68",
#   "54.123.45.69",
# ]
```

---

## 5. Practical Examples

### Example 1: Using Public Modules from Terraform Registry

```hcl
# Use AWS VPC module from Terraform Registry
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "5.1.0"
  
  name = "my-vpc"
  cidr = "10.0.0.0/16"
  
  azs             = ["us-east-1a", "us-east-1b", "us-east-1c"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24", "10.0.103.0/24"]
  
  enable_nat_gateway = true
  enable_vpn_gateway = false
  
  tags = {
    Environment = "production"
    Terraform   = "true"
  }
}

# Use EC2 module
module "ec2_cluster" {
  source  = "terraform-aws-modules/ec2-instance/aws"
  version = "5.5.0"
  
  name           = "my-cluster"
  instance_count = 3
  
  ami                    = "ami-0c55b159cbfafe1f0"
  instance_type          = "t2.micro"
  subnet_ids             = module.vpc.public_subnets
  vpc_security_group_ids = [module.security_group.security_group_id]
  
  tags = {
    Environment = "production"
  }
}

# Use Security Group module
module "security_group" {
  source  = "terraform-aws-modules/security-group/aws"
  version = "5.1.0"
  
  name        = "web-server-sg"
  description = "Security group for web servers"
  vpc_id      = module.vpc.vpc_id
  
  ingress_with_cidr_blocks = [
    {
      from_port   = 80
      to_port     = 80
      protocol    = "tcp"
      cidr_blocks = "0.0.0.0/0"
    },
    {
      from_port   = 443
      to_port     = 443
      protocol    = "tcp"
      cidr_blocks = "0.0.0.0/0"
    }
  ]
  
  egress_with_cidr_blocks = [
    {
      from_port   = 0
      to_port     = 0
      protocol    = "-1"
      cidr_blocks = "0.0.0.0/0"
    }
  ]
}
```

### Example 2: Module Composition

```hcl
# Compose multiple modules for complete application stack

# Network Layer
module "network" {
  source = "./modules/network"
  
  vpc_cidr    = "10.0.0.0/16"
  environment = "production"
  azs         = ["us-east-1a", "us-east-1b"]
}

# Database Layer
module "database" {
  source = "./modules/database"
  
  vpc_id            = module.network.vpc_id
  subnet_ids        = module.network.private_subnet_ids
  instance_class    = "db.t3.micro"
  allocated_storage = 20
  
  depends_on = [module.network]
}

# Application Layer
module "application" {
  source = "./modules/application"
  
  vpc_id         = module.network.vpc_id
  subnet_ids     = module.network.public_subnet_ids
  instance_type  = "t2.small"
  instance_count = 3
  
  db_endpoint = module.database.endpoint
  
  depends_on = [module.database]
}

# Load Balancer Layer
module "load_balancer" {
  source = "./modules/load-balancer"
  
  vpc_id          = module.network.vpc_id
  subnet_ids      = module.network.public_subnet_ids
  target_ids      = module.application.instance_ids
  certificate_arn = aws_acm_certificate.main.arn
  
  depends_on = [module.application]
}

# Outputs
output "application_url" {
  value = "https://${module.load_balancer.dns_name}"
}
```

### Example 3: Workspace-Aware Module Usage

```hcl
# Use workspaces to control module behavior

locals {
  workspace_configs = {
    dev = {
      vpc_cidr       = "10.0.0.0/16"
      instance_type  = "t2.micro"
      instance_count = 1
      db_size        = "db.t3.micro"
    }
    prod = {
      vpc_cidr       = "10.1.0.0/16"
      instance_type  = "t2.large"
      instance_count = 5
      db_size        = "db.r5.xlarge"
    }
  }
  
  config = local.workspace_configs[terraform.workspace]
}

module "infrastructure" {
  source = "./modules/full-stack"
  
  environment    = terraform.workspace
  vpc_cidr       = local.config.vpc_cidr
  instance_type  = local.config.instance_type
  instance_count = local.config.instance_count
  db_size        = local.config.db_size
}
```

---

## 6. Deep Dive

### Module Versioning

**Git Tags:**
```hcl
# Reference specific version
module "vpc" {
  source = "git::https://github.com/company/terraform-modules.git//vpc?ref=v1.2.3"
}

# Reference branch
module "vpc" {
  source = "git::https://github.com/company/terraform-modules.git//vpc?ref=main"
}

# Reference commit
module "vpc" {
  source = "git::https://github.com/company/terraform-modules.git//vpc?ref=abc123def"
}
```

**Terraform Registry Versions:**
```hcl
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "5.1.0"      # Exact version
  # version = "~> 5.1"   # Pessimistic constraint
  # version = ">= 5.0"   # Minimum version
}
```

### Module Data Flow

```
Root Module (main.tf)
    ↓ Pass variables
Child Module (module.vpc)
    ↓ Create resources
    ↓ Generate outputs
Root Module
    ↓ Use module outputs
Create dependent resources
```

**Example:**
```hcl
# Root passes variables to module
module "vpc" {
  source   = "./modules/vpc"
  vpc_cidr = "10.0.0.0/16"  # Input to module
}

# Module creates resources and outputs values
# (inside module)
output "vpc_id" {
  value = aws_vpc.main.id
}

# Root uses module outputs
resource "aws_instance" "web" {
  subnet_id = module.vpc.public_subnet_ids[0]  # Use module output
}
```

---

## 7. Trade-offs & Pitfalls

### Workspace Pitfalls

**Pitfall 1: Using workspaces for completely different infrastructure**
```
Bad: Using workspaces for separate projects
- Workspace "projectA"
- Workspace "projectB"

Better: Separate directories/repos for separate projects

Good use of workspaces:
- dev, staging, prod (same infrastructure, different sizes)
```

**Pitfall 2: Hardcoding workspace names**
```hcl
# Bad
resource "aws_instance" "web" {
  instance_type = terraform.workspace == "production" ? "t2.large" : "t2.micro"
}

# Better: Use lookup with config map
locals {
  configs = {
    dev  = { instance_type = "t2.micro" }
    prod = { instance_type = "t2.large" }
  }
  config = local.configs[terraform.workspace]
}
```

### Module Pitfalls

**Pitfall 1: Too many nested modules**
```
Bad: 5+ levels of nesting
module A → module B → module C → module D → module E

Result: Hard to debug, complex dependencies

Better: 2-3 levels maximum
```

**Pitfall 2: Module outputs everything**
```hcl
# Bad: Exposing internal implementation
output "internal_subnet_1" { }
output "internal_route_table_xyz" { }
output "internal_sg_rule_7" { }

# Good: Expose only what's needed
output "vpc_id" { }
output "public_subnet_ids" { }
output "private_subnet_ids" { }
```

**Pitfall 3: No module versioning**
```hcl
# Bad: Always uses latest (unstable)
module "vpc" {
  source = "git::https://github.com/company/modules.git//vpc"
}

# Good: Pin to version
module "vpc" {
  source = "git::https://github.com/company/modules.git//vpc?ref=v1.2.3"
}
```

---

## 8. Mental Models & Analogies

### Workspaces = Hotel Rooms

```
Same hotel (code), different rooms (workspaces)
- Room 101 (dev): Small, basic
- Room 201 (staging): Medium
- Room 301 (prod): Penthouse suite

Same layout, different sizes and amenities
```

### Modules = Lego Kits

```
Create once: VPC Lego kit
Use many times:
- Build 1: House with VPC kit
- Build 2: Office with same VPC kit
- Build 3: Store with same VPC kit

Same components, different combinations
```

---

## 9. Troubleshooting Guide

### Problem: "Workspace already exists"

```bash
terraform workspace new prod
# Error: Workspace "prod" already exists

# Solution:
terraform workspace select prod  # Just select it
```

### Problem: "Module not found"

```
Error: Module not installed
│ 
│   on main.tf line 10:
│   10: module "vpc" {
│ 
│ This module is not yet installed.

# Solution:
terraform init  # Downloads modules
```

### Problem: "Module source changed"

```bash
# Changed module source
terraform init

# If still issues:
rm -rf .terraform/modules
terraform init
```

---

## 10. Frequently Asked Questions

**Q1: Workspaces vs separate directories?**
**A:** Workspaces for same infrastructure, different environments. Separate directories for different projects.

**Q2: Can modules call other modules?**
**A:** Yes! Modules can be nested.

**Q3: How do I share modules across teams?**
**A:** Git repository or Terraform Registry (private or public).

**Q4: Should I use workspaces in production?**
**A:** Yes, but some prefer separate state files per environment for safety.

**Q5: Can I delete a workspace with resources?**
**A:** No, must destroy resources first.

**Q6: How many modules is too many?**
**A:** If debugging becomes hard (>3 levels deep), too many.

**Q7: Can module variables have no defaults?**
**A:** Yes, they become required inputs.

**Q8: Should I version private modules?**
**A:** Yes, always use Git tags for stability.

**Q9: Can workspaces share resources?**
**A:** No, each workspace has separate state.

**Q10: How do I test modules?**
**A:** Create test configurations, use tools like Terratest.

---

## 11. Key Takeaways

✅ **Workspaces** = Same code, multiple environments
✅ **Modules** = Reusable infrastructure components
✅ **terraform.workspace** = Current workspace name in code
✅ **Module outputs** = How modules expose values
✅ **Version modules** = Use Git tags or Registry versions
✅ **Composition** = Combine modules for complex stacks
✅ **Keep modules simple** = Single responsibility
✅ **Public modules** = Terraform Registry has 1000s
✅ **Separate concerns** = Network, app, data modules
✅ **Document modules** = README with examples

---

## 12. Practice Exercises

### Exercise 1: Workspace Workflow
Create dev, staging, prod workspaces. Deploy same config to all three.

### Exercise 2: Custom Module
Create VPC module with variables. Use in root module.

### Exercise 3: Module Composition
Create network + app + database modules. Compose together.

### Exercise 4: Public Module
Use terraform-aws-modules/vpc. Deploy multi-AZ VPC.

### Exercise 5: Nested Modules
Create module that calls other modules (2 levels).

---

## 13. Further Reading

- Terraform Module Documentation
- Terraform Registry
- Module Development Best Practices
- Workspace Documentation

---

*Workspaces & Modules Mastered!*
*You can now build production-grade, reusable infrastructure!*
