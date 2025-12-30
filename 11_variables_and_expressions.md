# Chapter 11: Variables & Expressions – Dynamic Infrastructure Code

## Prerequisites
- Understanding of HCL syntax (Chapter 8)
- Knowledge of block types (Chapter 9)
- Terraform workflow experience (Chapter 10)
- Provider knowledge (Chapter 11)
- Estimated reading time: 50-60 minutes

## 1. Introduction

### Why This Topic Matters

Variables and expressions are what make Terraform code reusable and dynamic. Without them, you'd hardcode every value and duplicate code everywhere. With them, you write infrastructure once and customize it for any environment.

**The Reality:**
```
Without variables: Copy-paste code for dev, staging, prod (nightmare to maintain)
With variables: One codebase, parameterized for all environments (DRY principle)
```

**The Transformation:**
- **Before:** 100 lines for dev, another 100 for staging, 100 for prod = 300 lines
- **After:** 100 lines total, configured via variables = 3x less code

### What You'll Learn

- Input variables (parameterize configurations)
- Output values (export data)
- Local values (intermediate calculations)
- Variable types (string, number, bool, list, map, object)
- Variable validation and constraints
- String interpolation and templates
- Expressions and operators
- Conditional expressions
- For expressions and loops
- Dynamic blocks
- Functions (50+ built-in functions)
- Sensitive data handling
- Variable precedence and override

### The Problem Being Solved

**Scenario: Multi-Environment Infrastructure**

**Without Variables (Hardcoded Hell):**
```hcl
# dev.tf
resource "aws_instance" "dev" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  tags = { Environment = "dev" }
}

# staging.tf
resource "aws_instance" "staging" {
  ami           = "ami-12345"
  instance_type = "t2.small"
  tags = { Environment = "staging" }
}

# prod.tf
resource "aws_instance" "prod" {
  ami           = "ami-12345"
  instance_type = "t2.large"
  tags = { Environment = "production" }
}

# Result: 3x code duplication, hard to maintain
```

**With Variables (Clean and DRY):**
```hcl
# variables.tf
variable "environment" {
  type = string
}

variable "instance_sizes" {
  type = map(string)
  default = {
    dev     = "t2.micro"
    staging = "t2.small"
    prod    = "t2.large"
  }
}

# main.tf
resource "aws_instance" "app" {
  ami           = "ami-12345"
  instance_type = var.instance_sizes[var.environment]
  tags = { Environment = var.environment }
}

# Usage:
# terraform apply -var="environment=dev"     → t2.micro
# terraform apply -var="environment=prod"    → t2.large

# Result: One configuration, infinite flexibility
```

---

## 2. Concept Overview

### The Three Types of Values

```
1. Input Variables (var.*)
   └─ User-provided inputs
   └─ Parameterize configurations
   └─ Example: var.region, var.instance_type

2. Local Values (local.*)
   └─ Computed intermediate values
   └─ Simplify complex expressions
   └─ Example: local.common_tags

3. Output Values (outputs)
   └─ Export values after apply
   └─ Display results, share with other modules
   └─ Example: output "instance_ip"
```

### Variable Flow

```
┌─────────────────────────────────────────┐
│ Input Sources (Priority Order)         │
│ 1. Command line (-var)                 │
│ 2. terraform.tfvars file               │
│ 3. *.auto.tfvars files                 │
│ 4. Environment variables (TF_VAR_*)    │
│ 5. Default value in variable block     │
│ 6. Interactive prompt (if no default)  │
└─────────────────────────────────────────┘
            ↓
┌─────────────────────────────────────────┐
│ Variable Processing                     │
│ - Validation checks                     │
│ - Type conversion                       │
│ - Default application                   │
└─────────────────────────────────────────┘
            ↓
┌─────────────────────────────────────────┐
│ Used in Configuration                   │
│ - Resources (var.instance_type)         │
│ - Locals (local.name)                   │
│ - Outputs (var.region)                  │
└─────────────────────────────────────────┘
            ↓
┌─────────────────────────────────────────┐
│ Outputs After Apply                     │
│ - Display values                        │
│ - Export for other modules              │
└─────────────────────────────────────────┘
```

---

## 3. Core Theory

### Input Variables

**Declaration syntax:**
```hcl
variable "name" {
  type        = <TYPE>
  description = "Description"
  default     = <VALUE>
  sensitive   = true/false
  nullable    = true/false
  
  validation {
    condition     = <BOOLEAN_EXPRESSION>
    error_message = "Error message"
  }
}
```

**Complete example:**
```hcl
variable "instance_type" {
  type        = string
  description = "EC2 instance type for the application server"
  default     = "t2.micro"
  
  validation {
    condition     = contains(["t2.micro", "t2.small", "t2.medium"], var.instance_type)
    error_message = "Instance type must be t2.micro, t2.small, or t2.medium."
  }
}

variable "environment" {
  type        = string
  description = "Environment name (dev, staging, prod)"
  
  validation {
    condition     = can(regex("^(dev|staging|prod)$", var.environment))
    error_message = "Environment must be dev, staging, or prod."
  }
}

variable "enable_monitoring" {
  type        = bool
  description = "Enable detailed monitoring"
  default     = false
}

variable "availability_zones" {
  type        = list(string)
  description = "List of availability zones"
  default     = ["us-east-1a", "us-east-1b"]
}

variable "tags" {
  type        = map(string)
  description = "Resource tags"
  default = {
    ManagedBy = "Terraform"
  }
}

variable "db_config" {
  type = object({
    username     = string
    port         = number
    multi_az     = bool
    backup_days  = number
  })
  description = "Database configuration"
  default = {
    username    = "admin"
    port        = 5432
    multi_az    = false
    backup_days = 7
  }
}

variable "db_password" {
  type        = string
  description = "Database password"
  sensitive   = true  # Won't show in logs
}
```

### Variable Types

**Primitive Types:**
```hcl
# String
variable "region" {
  type    = string
  default = "us-east-1"
}

# Number
variable "instance_count" {
  type    = number
  default = 3
}

# Bool
variable "enable_vpn" {
  type    = bool
  default = true
}
```

**Collection Types:**
```hcl
# List (ordered, same type)
variable "availability_zones" {
  type    = list(string)
  default = ["us-east-1a", "us-east-1b", "us-east-1c"]
}

# Set (unordered, unique, same type)
variable "allowed_ips" {
  type    = set(string)
  default = ["10.0.1.0/24", "10.0.2.0/24"]
}

# Map (key-value pairs)
variable "instance_types" {
  type = map(string)
  default = {
    dev     = "t2.micro"
    staging = "t2.small"
    prod    = "t2.large"
  }
}
```

**Structural Types:**
```hcl
# Object (fixed schema)
variable "server_config" {
  type = object({
    name          = string
    instance_type = string
    disk_size     = number
    monitoring    = bool
  })
  default = {
    name          = "app-server"
    instance_type = "t2.micro"
    disk_size     = 20
    monitoring    = false
  }
}

# Tuple (fixed-length, mixed types)
variable "mixed_values" {
  type    = tuple([string, number, bool])
  default = ["app", 8080, true]
}

# Complex nested structures
variable "vpc_config" {
  type = object({
    cidr_block = string
    subnets = list(object({
      cidr       = string
      az         = string
      public     = bool
    }))
    enable_nat = bool
  })
}
```

### Providing Variable Values

**Method 1: Command Line**
```bash
terraform apply -var="environment=prod" -var="instance_count=5"
```

**Method 2: terraform.tfvars**
```hcl
# terraform.tfvars (automatically loaded)
environment    = "production"
instance_count = 5
instance_type  = "t2.large"
enable_monitoring = true

availability_zones = ["us-east-1a", "us-east-1b"]

tags = {
  Project     = "WebApp"
  CostCenter  = "Engineering"
  Environment = "production"
}

db_config = {
  username    = "dbadmin"
  port        = 5432
  multi_az    = true
  backup_days = 30
}
```

**Method 3: Custom .tfvars file**
```bash
# dev.tfvars
environment = "dev"
instance_type = "t2.micro"

# prod.tfvars
environment = "prod"
instance_type = "t2.large"

# Usage:
terraform apply -var-file="dev.tfvars"
terraform apply -var-file="prod.tfvars"
```

**Method 4: Environment Variables**
```bash
export TF_VAR_environment="prod"
export TF_VAR_instance_count="5"
export TF_VAR_db_password="super-secret"

terraform apply  # Automatically uses TF_VAR_* variables
```

**Method 5: Auto-loaded .tfvars**
```
Terraform automatically loads (in order):
1. terraform.tfvars
2. terraform.tfvars.json
3. *.auto.tfvars
4. *.auto.tfvars.json

# Example files:
terraform.tfvars       ← Loaded
dev.auto.tfvars        ← Loaded
prod.auto.tfvars       ← Loaded
custom.tfvars          ← NOT loaded (must specify with -var-file)
```

**Variable Precedence (highest to lowest):**
```
1. -var command line flag
2. -var-file command line flag
3. *.auto.tfvars (alphabetical order)
4. terraform.tfvars
5. Environment variables (TF_VAR_name)
6. Default value in variable block
```

### Output Values

**Syntax:**
```hcl
output "name" {
  value       = <EXPRESSION>
  description = "Description"
  sensitive   = true/false
  depends_on  = [<RESOURCE>]
}
```

**Examples:**
```hcl
# Simple output
output "instance_id" {
  description = "ID of the EC2 instance"
  value       = aws_instance.web.id
}

# Multiple values
output "instance_ips" {
  description = "All instance public IPs"
  value       = aws_instance.web[*].public_ip
}

# Computed output
output "connection_string" {
  description = "Database connection string"
  value = "postgresql://${aws_db_instance.main.username}:${var.db_password}@${aws_db_instance.main.endpoint}/mydb"
  sensitive = true  # Don't display in console
}

# Object output
output "vpc_info" {
  description = "VPC information"
  value = {
    id         = aws_vpc.main.id
    cidr       = aws_vpc.main.cidr_block
    subnet_ids = aws_subnet.public[*].id
  }
}

# Conditional output
output "load_balancer_dns" {
  description = "Load balancer DNS name"
  value       = var.enable_lb ? aws_lb.main[0].dns_name : "No load balancer"
}
```

**Using Outputs:**
```bash
# View all outputs
terraform output

# View specific output
terraform output instance_id

# Raw output (no quotes)
terraform output -raw instance_id

# JSON format
terraform output -json

# Use in scripts
INSTANCE_IP=$(terraform output -raw instance_public_ip)
ssh ubuntu@$INSTANCE_IP

# Use in other modules
module "network" {
  source = "./modules/network"
}

resource "aws_instance" "web" {
  subnet_id = module.network.public_subnet_id  # Reference module output
}
```

### Local Values

**Purpose:** Simplify complex expressions, avoid repetition

**Syntax:**
```hcl
locals {
  name1 = expression1
  name2 = expression2
}
```

**Examples:**
```hcl
locals {
  # Computed name
  instance_name = "${var.environment}-${var.app_name}-server"
  
  # Common tags
  common_tags = {
    Environment = var.environment
    ManagedBy   = "Terraform"
    Project     = var.project_name
    CostCenter  = "Engineering"
  }
  
  # Conditional values
  instance_type = var.environment == "prod" ? "t2.large" : "t2.micro"
  backup_enabled = var.environment == "prod" ? true : false
  
  # List transformations
  subnet_cidrs = [for i in range(var.subnet_count) : cidrsubnet(var.vpc_cidr, 8, i)]
  
  # String manipulation
  bucket_name = lower(replace(var.app_name, "_", "-"))
  
  # Timestamp
  created_at = timestamp()
  
  # Complex object
  db_config = {
    endpoint = "${aws_db_instance.main.endpoint}"
    port     = aws_db_instance.main.port
    name     = aws_db_instance.main.name
    url      = "postgresql://${aws_db_instance.main.username}@${aws_db_instance.main.endpoint}:${aws_db_instance.main.port}/${aws_db_instance.main.name}"
  }
  
  # Conditional resource counts
  instance_count = var.environment == "prod" ? var.prod_instance_count : var.dev_instance_count
}

# Use locals
resource "aws_instance" "web" {
  ami           = var.ami_id
  instance_type = local.instance_type  # Reference local
  
  tags = merge(
    local.common_tags,  # Spread common tags
    {
      Name = local.instance_name
    }
  )
}
```

---

## 4. Step-by-Step Walkthrough

### Complete Example: Multi-Environment Setup

**Directory structure:**
```
project/
├── main.tf
├── variables.tf
├── outputs.tf
├── terraform.tfvars
├── dev.tfvars
└── prod.tfvars
```

**variables.tf:**
```hcl
variable "environment" {
  type        = string
  description = "Environment name"
  
  validation {
    condition     = contains(["dev", "staging", "prod"], var.environment)
    error_message = "Environment must be dev, staging, or prod."
  }
}

variable "app_name" {
  type        = string
  description = "Application name"
  default     = "webapp"
}

variable "aws_region" {
  type        = string
  description = "AWS region"
  default     = "us-east-1"
}

variable "instance_config" {
  type = map(object({
    instance_type   = string
    instance_count  = number
    enable_backup   = bool
  }))
  description = "Instance configuration per environment"
  default = {
    dev = {
      instance_type  = "t2.micro"
      instance_count = 1
      enable_backup  = false
    }
    staging = {
      instance_type  = "t2.small"
      instance_count = 2
      enable_backup  = true
    }
    prod = {
      instance_type  = "t2.large"
      instance_count = 5
      enable_backup  = true
    }
  }
}

variable "allowed_cidr_blocks" {
  type        = list(string)
  description = "CIDR blocks allowed to access the application"
  default     = ["0.0.0.0/0"]
}

variable "tags" {
  type        = map(string)
  description = "Additional tags"
  default     = {}
}
```

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
  region = var.aws_region
}

# Data source for AMI
data "aws_ami" "ubuntu" {
  most_recent = true
  owners      = ["099720109477"]
  
  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-jammy-22.04-amd64-server-*"]
  }
}

# Locals for computed values
locals {
  # Get config for current environment
  config = var.instance_config[var.environment]
  
  # Computed names
  name_prefix = "${var.app_name}-${var.environment}"
  
  # Common tags
  common_tags = merge(
    {
      Environment = var.environment
      Application = var.app_name
      ManagedBy   = "Terraform"
    },
    var.tags
  )
  
  # Backup schedule
  backup_schedule = local.config.enable_backup ? "cron(0 2 * * ? *)" : null
}

# VPC
resource "aws_vpc" "main" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  
  tags = merge(local.common_tags, {
    Name = "${local.name_prefix}-vpc"
  })
}

# Subnet
resource "aws_subnet" "public" {
  count                   = local.config.instance_count
  vpc_id                  = aws_vpc.main.id
  cidr_block              = "10.0.${count.index + 1}.0/24"
  map_public_ip_on_launch = true
  
  tags = merge(local.common_tags, {
    Name = "${local.name_prefix}-subnet-${count.index + 1}"
  })
}

# Security Group
resource "aws_security_group" "web" {
  name        = "${local.name_prefix}-web-sg"
  description = "Security group for ${var.app_name} web servers"
  vpc_id      = aws_vpc.main.id
  
  dynamic "ingress" {
    for_each = [80, 443]
    content {
      from_port   = ingress.value
      to_port     = ingress.value
      protocol    = "tcp"
      cidr_blocks = var.allowed_cidr_blocks
    }
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  tags = merge(local.common_tags, {
    Name = "${local.name_prefix}-sg"
  })
}

# EC2 Instances
resource "aws_instance" "web" {
  count         = local.config.instance_count
  ami           = data.aws_ami.ubuntu.id
  instance_type = local.config.instance_type
  subnet_id     = aws_subnet.public[count.index % length(aws_subnet.public)].id
  
  vpc_security_group_ids = [aws_security_group.web.id]
  
  tags = merge(local.common_tags, {
    Name  = "${local.name_prefix}-web-${count.index + 1}"
    Index = count.index
  })
}
```

**outputs.tf:**
```hcl
output "vpc_id" {
  description = "ID of the VPC"
  value       = aws_vpc.main.id
}

output "subnet_ids" {
  description = "IDs of all subnets"
  value       = aws_subnet.public[*].id
}

output "instance_ids" {
  description = "IDs of all instances"
  value       = aws_instance.web[*].id
}

output "instance_public_ips" {
  description = "Public IPs of all instances"
  value       = aws_instance.web[*].public_ip
}

output "security_group_id" {
  description = "ID of the security group"
  value       = aws_security_group.web.id
}

output "instance_details" {
  description = "Detailed instance information"
  value = [
    for instance in aws_instance.web : {
      id         = instance.id
      public_ip  = instance.public_ip
      private_ip = instance.private_ip
      az         = instance.availability_zone
    }
  ]
}

output "environment_summary" {
  description = "Environment configuration summary"
  value = {
    environment    = var.environment
    instance_type  = local.config.instance_type
    instance_count = local.config.instance_count
    backup_enabled = local.config.enable_backup
    region         = var.aws_region
  }
}
```

**dev.tfvars:**
```hcl
environment = "dev"
app_name    = "myapp"
aws_region  = "us-east-1"

allowed_cidr_blocks = ["10.0.0.0/8"]

tags = {
  CostCenter = "Engineering"
  Owner      = "DevTeam"
}
```

**prod.tfvars:**
```hcl
environment = "prod"
app_name    = "myapp"
aws_region  = "us-east-1"

allowed_cidr_blocks = ["0.0.0.0/0"]

tags = {
  CostCenter = "Production"
  Owner      = "OpsTeam"
  Compliance = "PCI-DSS"
}
```

**Usage:**
```bash
# Development environment
terraform init
terraform plan -var-file="dev.tfvars"
terraform apply -var-file="dev.tfvars"
# Creates 1 t2.micro instance, no backups

# Production environment
terraform plan -var-file="prod.tfvars"
terraform apply -var-file="prod.tfvars"
# Creates 5 t2.large instances, with backups

# View outputs
terraform output
terraform output instance_public_ips
```

---

## 5. Practical Examples

### Example 1: Conditional Expressions

```hcl
variable "environment" {
  type = string
}

locals {
  # Ternary operator: condition ? true_value : false_value
  instance_type = var.environment == "prod" ? "t2.large" : "t2.micro"
  
  # Nested conditionals
  backup_retention = var.environment == "prod" ? 30 : (
    var.environment == "staging" ? 7 : 1
  )
  
  # Boolean conditionals
  enable_monitoring = var.environment == "prod" ? true : false
  
  # With count (conditional resource creation)
  eip_count = var.environment == "prod" ? 1 : 0
}

resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = local.instance_type
  monitoring    = local.enable_monitoring
}

# Create Elastic IP only in production
resource "aws_eip" "web" {
  count    = local.eip_count
  instance = aws_instance.web.id
}
```

### Example 2: For Expressions

```hcl
variable "users" {
  type    = list(string)
  default = ["alice", "bob", "charlie"]
}

variable "servers" {
  type = list(object({
    name = string
    ip   = string
  }))
  default = [
    { name = "web1", ip = "10.0.1.10" },
    { name = "web2", ip = "10.0.1.20" },
    { name = "db1", ip = "10.0.2.10" }
  ]
}

locals {
  # List transformation
  user_emails = [for user in var.users : "${user}@example.com"]
  # Result: ["alice@example.com", "bob@example.com", "charlie@example.com"]
  
  # With filtering
  admin_users = [for user in var.users : user if user != "bob"]
  # Result: ["alice", "charlie"]
  
  # List to map
  user_map = { for user in var.users : user => "${user}@example.com" }
  # Result: { alice = "alice@example.com", bob = "bob@example.com", ... }
  
  # Extract field from objects
  server_names = [for server in var.servers : server.name]
  # Result: ["web1", "web2", "db1"]
  
  # Conditional transformation
  uppercase_names = [for name in var.users : upper(name) if length(name) > 3]
  # Result: ["ALICE", "CHARLIE"]
  
  # Map transformation
  server_map = {
    for server in var.servers :
    server.name => server.ip
  }
  # Result: { web1 = "10.0.1.10", web2 = "10.0.1.20", db1 = "10.0.2.10" }
  
  # Flattening nested lists
  all_ips = flatten([
    for server in var.servers : [
      server.ip,
      "${server.ip}/32"
    ]
  ])
}

output "user_emails" {
  value = local.user_emails
}

output "server_map" {
  value = local.server_map
}
```

### Example 3: Dynamic Blocks

```hcl
variable "ingress_rules" {
  type = list(object({
    port        = number
    protocol    = string
    cidr_blocks = list(string)
    description = string
  }))
  default = [
    {
      port        = 80
      protocol    = "tcp"
      cidr_blocks = ["0.0.0.0/0"]
      description = "HTTP"
    },
    {
      port        = 443
      protocol    = "tcp"
      cidr_blocks = ["0.0.0.0/0"]
      description = "HTTPS"
    },
    {
      port        = 22
      protocol    = "tcp"
      cidr_blocks = ["10.0.0.0/8"]
      description = "SSH"
    }
  ]
}

resource "aws_security_group" "web" {
  name        = "web-sg"
  description = "Web server security group"
  
  # Dynamic block for ingress rules
  dynamic "ingress" {
    for_each = var.ingress_rules
    content {
      from_port   = ingress.value.port
      to_port     = ingress.value.port
      protocol    = ingress.value.protocol
      cidr_blocks = ingress.value.cidr_blocks
      description = ingress.value.description
    }
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

# Nested dynamic blocks
variable "load_balancer_config" {
  type = object({
    listeners = list(object({
      port     = number
      protocol = string
      rules = list(object({
        priority = number
        path     = string
      }))
    }))
  })
}

resource "aws_lb_listener" "main" {
  for_each = { for idx, listener in var.load_balancer_config.listeners : idx => listener }
  
  load_balancer_arn = aws_lb.main.arn
  port              = each.value.port
  protocol          = each.value.protocol
  
  default_action {
    type             = "forward"
    target_group_arn = aws_lb_target_group.main.arn
  }
  
  # Nested dynamic for rules
  dynamic "rule" {
    for_each = each.value.rules
    content {
      priority = rule.value.priority
      
      condition {
        path_pattern {
          values = [rule.value.path]
        }
      }
    }
  }
}
```

### Example 4: String Interpolation and Templates

```hcl
variable "environment" {
  default = "production"
}

variable "app_name" {
  default = "webapp"
}

variable "port" {
  default = 8080
}

locals {
  # Simple interpolation
  server_name = "${var.app_name}-${var.environment}"
  
  # With functions
  uppercase_name = "${upper(var.app_name)}-${var.environment}"
  
  # Complex interpolation
  connection_url = "https://${var.app_name}.${var.environment}.example.com:${var.port}"
  
  # Multi-line template
  user_data = <<-EOT
    #!/bin/bash
    echo "Starting ${var.app_name} in ${var.environment} mode"
    export APP_NAME="${var.app_name}"
    export ENVIRONMENT="${var.environment}"
    export PORT="${var.port}"
    /usr/local/bin/start-app
  EOT
  
  # Conditional in template
  config_file = <<-EOT
    app_name: ${var.app_name}
    environment: ${var.environment}
    debug: ${var.environment == "dev" ? "true" : "false"}
    log_level: ${var.environment == "prod" ? "error" : "debug"}
  EOT
  
  # Using templatefile function
  rendered_config = templatefile("${path.module}/config.tpl", {
    app_name    = var.app_name
    environment = var.environment
    port        = var.port
  })
}

# config.tpl file content:
# app:
#   name: ${app_name}
#   environment: ${environment}
#   port: ${port}
#   debug: ${environment == "dev" ? true : false}
```

### Example 5: Validation Rules

```hcl
variable "instance_type" {
  type        = string
  description = "EC2 instance type"
  
  validation {
    condition     = can(regex("^t[23]\\.(micro|small|medium|large)$", var.instance_type))
    error_message = "Instance type must be t2 or t3 family: micro, small, medium, or large."
  }
}

variable "environment" {
  type = string
  
  validation {
    condition     = contains(["dev", "staging", "prod"], var.environment)
    error_message = "Environment must be one of: dev, staging, prod."
  }
}

variable "vpc_cidr" {
  type = string
  
  validation {
    condition     = can(cidrhost(var.vpc_cidr, 0))
    error_message = "VPC CIDR must be a valid IPv4 CIDR block."
  }
}

variable "port" {
  type = number
  
  validation {
    condition     = var.port >= 1 && var.port <= 65535
    error_message = "Port must be between 1 and 65535."
  }
}

variable "email" {
  type = string
  
  validation {
    condition     = can(regex("^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\\.[a-zA-Z]{2,}$", var.email))
    error_message = "Email must be a valid email address."
  }
}

variable "tags" {
  type = map(string)
  
  validation {
    condition     = contains(keys(var.tags), "Environment")
    error_message = "Tags must include 'Environment' key."
  }
}
```

---

## 6. Deep Dive

### Built-in Functions

Terraform has 100+ built-in functions. Here are the most commonly used:

**String Functions:**
```hcl
locals {
  # Case conversion
  upper_name   = upper("hello")              # "HELLO"
  lower_name   = lower("HELLO")              # "hello"
  title_name   = title("hello world")        # "Hello World"
  
  # String manipulation
  trimmed      = trimspace("  hello  ")      # "hello"
  replaced     = replace("hello", "l", "L")  # "heLLo"
  substr       = substr("hello", 0, 4)       # "hell"
  
  # Formatting
  formatted    = format("Server-%03d", 5)    # "Server-005"
  joined       = join(",", ["a", "b", "c"])  # "a,b,c"
  split_result = split(",", "a,b,c")         # ["a", "b", "c"]
  
  # Regex
  regex_match  = regex("[a-z]+", "hello123") # "hello"
  regex_all    = regexall("[0-9]+", "a1b2c3") # ["1", "2", "3"]
}
```

**Numeric Functions:**
```hcl
locals {
  min_val      = min(5, 10, 3, 7)           # 3
  max_val      = max(5, 10, 3, 7)           # 10
  absolute     = abs(-42)                    # 42
  ceiling      = ceil(4.3)                   # 5
  floor_val    = floor(4.7)                  # 4
  log_val      = log(8, 2)                   # 3
  pow_val      = pow(2, 3)                   # 8
}
```

**Collection Functions:**
```hcl
variable "list" {
  default = ["a", "b", "c"]
}

variable "map" {
  default = { key1 = "val1", key2 = "val2" }
}

locals {
  # List operations
  length_val   = length(var.list)            # 3
  element_val  = element(var.list, 1)        # "b"
  contains_val = contains(var.list, "b")     # true
  index_val    = index(var.list, "b")        # 1
  
  # Sorting
  sorted       = sort(["c", "a", "b"])       # ["a", "b", "c"]
  reversed     = reverse(var.list)           # ["c", "b", "a"]
  
  # Set operations
  distinct     = distinct(["a", "b", "a"])   # ["a", "b"]
  
  # Map operations
  keys_list    = keys(var.map)               # ["key1", "key2"]
  values_list  = values(var.map)             # ["val1", "val2"]
  lookup_val   = lookup(var.map, "key1", "default") # "val1"
  
  # Merging
  merged_map   = merge({ a = 1 }, { b = 2 }) # { a = 1, b = 2 }
  
  # Slicing
  slice_result = slice(["a", "b", "c", "d"], 1, 3) # ["b", "c"]
}
```

**IP Network Functions:**
```hcl
locals {
  # CIDR manipulation
  subnet1      = cidrsubnet("10.0.0.0/16", 8, 1)     # "10.0.1.0/24"
  subnet2      = cidrsubnet("10.0.0.0/16", 8, 2)     # "10.0.2.0/24"
  host_ip      = cidrhost("10.0.1.0/24", 5)          # "10.0.1.5"
  netmask      = cidrnetmask("10.0.1.0/24")          # "255.255.255.0"
  
  # Generate multiple subnets
  subnets = [for i in range(3) : cidrsubnet("10.0.0.0/16", 8, i)]
  # ["10.0.0.0/24", "10.0.1.0/24", "10.0.2.0/24"]
}
```

**Type Conversion Functions:**
```hcl
locals {
  # To string
  str_val      = tostring(42)                # "42"
  
  # To number
  num_val      = tonumber("42")              # 42
  
  # To bool
  bool_val     = tobool("true")              # true
  
  # To list
  list_val     = tolist(["a", "b"])          # ["a", "b"]
  
  # To set
  set_val      = toset(["a", "b", "a"])      # ["a", "b"]
  
  # To map
  map_val      = tomap({ a = 1, b = 2 })     # { a = 1, b = 2 }
}
```

**Filesystem Functions:**
```hcl
locals {
  # Read files
  file_content = file("${path.module}/config.txt")
  json_data    = jsondecode(file("${path.module}/data.json"))
  yaml_data    = yamldecode(file("${path.module}/data.yaml"))
  
  # Paths
  module_path  = path.module    # Current module directory
  root_path    = path.root      # Root module directory
  cwd_path     = path.cwd       # Current working directory
  
  # Basename/dirname
  filename     = basename("/path/to/file.txt")    # "file.txt"
  dirname      = dirname("/path/to/file.txt")     # "/path/to"
}
```

**Date/Time Functions:**
```hcl
locals {
  current_time  = timestamp()                 # "2025-12-30T10:30:00Z"
  formatted     = formatdate("YYYY-MM-DD", timestamp()) # "2025-12-30"
  time_add      = timeadd(timestamp(), "24h") # 24 hours from now
}
```

**Encoding Functions:**
```hcl
locals {
  # Base64
  encoded      = base64encode("hello")        # "aGVsbG8="
  decoded      = base64decode("aGVsbG8=")     # "hello"
  
  # JSON
  json_string  = jsonencode({ key = "value" }) # "{\"key\":\"value\"}"
  json_object  = jsondecode("{\"key\":\"value\"}") # { key = "value" }
  
  # YAML
  yaml_string  = yamlencode({ key = "value" })
  yaml_object  = yamldecode("key: value")
}
```

### Sensitive Data Handling

```hcl
variable "db_password" {
  type      = string
  sensitive = true  # Won't show in plan/apply output
}

output "password" {
  value     = var.db_password
  sensitive = true  # Won't display unless specifically requested
}

# In logs/console:
# db_password = (sensitive value)

# To view:
terraform output password        # (sensitive value)
terraform output -json password  # Shows actual value
```

---

## 7. Trade-offs & Pitfalls

### Common Mistakes

**Mistake 1: Not using variables**
```hcl
# Bad: Hardcoded values
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
}

# Good: Parameterized
variable "ami_id" { type = string }
variable "instance_type" { type = string }

resource "aws_instance" "web" {
  ami           = var.ami_id
  instance_type = var.instance_type
}
```

**Mistake 2: Circular references**
```hcl
# This will fail!
variable "name" {
  default = local.computed_name  # Can't reference local in variable
}

locals {
  computed_name = var.name  # Circular!
}

# Fix: Use locals only
locals {
  base_name     = "myapp"
  computed_name = "${local.base_name}-server"
}
```

**Mistake 3: Sensitive data in plaintext**
```hcl
# Wrong: Password in tfvars (committed to git!)
# terraform.tfvars
db_password = "super-secret-password"

# Right: Use environment variable
export TF_VAR_db_password="super-secret-password"
```

**Mistake 4: Overly complex expressions**
```hcl
# Bad: Hard to read
instance_type = var.env == "prod" ? "t2.large" : var.env == "staging" ? "t2.medium" : var.env == "dev" ? "t2.small" : "t2.micro"

# Good: Use map
variable "instance_types" {
  type = map(string)
  default = {
    prod    = "t2.large"
    staging = "t2.medium"
    dev     = "t2.small"
  }
}

locals {
  instance_type = lookup(var.instance_types, var.env, "t2.micro")
}
```

---

## 8. Mental Models & Analogies

### Analogy: Variables as Recipe Ingredients

**Recipe (Terraform Config):**
```
Cake Recipe (main.tf):
- Mix {{flour}} cups of flour
- Add {{sugar}} cups of sugar  
- Bake at {{temperature}}°F
```

**Ingredient List (Variables):**
```
Variables (variables.tf):
flour = 2
sugar = 1
temperature = 350
```

**Different Cakes (Environments):**
```
Small cake (dev.tfvars):
flour = 1
sugar = 0.5
temperature = 325

Large cake (prod.tfvars):
flour = 4
sugar = 2
temperature = 375
```

**Result:** One recipe, multiple cakes!

---

## 9. Troubleshooting Guide

### Problem: "No value for required variable"

**Error:**
```
Error: No value for required variable
│ 
│   on variables.tf line 1:
│    1: variable "environment" {
│ 
│ The root module input variable "environment" is not set, and has no
│ default value. Use a -var or -var-file command line argument to provide a
│ value for this variable.
```

**Solutions:**
```bash
# Option 1: Command line
terraform apply -var="environment=prod"

# Option 2: tfvars file
echo 'environment = "prod"' > terraform.tfvars
terraform apply

# Option 3: Environment variable
export TF_VAR_environment="prod"
terraform apply

# Option 4: Add default
variable "environment" {
  type    = string
  default = "dev"  # Add default
}
```

### Problem: "Invalid value for variable"

**Error:**
```
Error: Invalid value for variable
│ 
│   on variables.tf line 5:
│    5:   validation {
│ 
│ Instance type must be t2.micro, t2.small, or t2.medium.
```

**Solution:** Provide valid value matching validation rule.

---

## 10. Frequently Asked Questions

**Q1: Can variables reference other variables?**
**A:** No, but locals can reference variables.

**Q2: Can I have different variable values per environment?**
**A:** Yes, use separate .tfvars files (dev.tfvars, prod.tfvars).

**Q3: Should I commit terraform.tfvars to git?**
**A:** Only if it doesn't contain secrets. Otherwise use .gitignore.

**Q4: Can outputs reference other outputs?**
**A:** Yes, outputs can reference other outputs.

**Q5: What's the difference between variable and local?**
**A:** Variable = user input, Local = computed value.

**Q6: Can I use variables in terraform block?**
**A:** No, terraform block only accepts literal values.

**Q7: How do I pass complex objects as variables?**
**A:** Use object type: `type = object({ ... })`

**Q8: Can I make variables optional?**
**A:** Yes, provide a default value.

**Q9: How do I handle secrets?**
**A:** Use sensitive = true, environment variables, or external secret managers.

**Q10: Can I validate variable format?**
**A:** Yes, use validation blocks with regex or other conditions.

---

## 11. Key Takeaways

✅ **Variables** = Inputs to parameterize code
✅ **Locals** = Computed values to simplify expressions
✅ **Outputs** = Export values after apply
✅ **Type system** = string, number, bool, list, map, object
✅ **Validation** = Enforce constraints
✅ **For expressions** = Transform collections
✅ **Dynamic blocks** = Generate repeated blocks
✅ **Functions** = 100+ built-in functions
✅ **Sensitive data** = Use sensitive = true
✅ **.tfvars files** = Environment-specific values

---

## 12. Practice Exercises

### Exercise 1: Basic Variables
Create variables for region, instance_type, and environment. Use in EC2 resource.

### Exercise 2: Complex Object Variable
Define server_config variable with nested object structure.

### Exercise 3: For Expression
Transform list of usernames to email addresses.

### Exercise 4: Dynamic Block
Create security group with dynamic ingress rules from variable.

### Exercise 5: Multi-Environment
Create dev.tfvars and prod.tfvars with different configurations.

---

## 13. Further Reading

- Terraform Variables Documentation
- HCL Functions Reference
- Input Variables Best Practices
- Sensitive Data Management

---

*Variables & Expressions Mastered!*
*Your Terraform code is now dynamic and reusable!*
