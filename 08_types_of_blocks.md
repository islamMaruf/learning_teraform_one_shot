# Chapter 8: Types of Blocks – The Building Blocks of Terraform

## Prerequisites
- Understanding of HCL syntax (Chapter 8)
- Terraform installed and configured
- Basic AWS knowledge
- Estimated reading time: 45-50 minutes

## 1. Introduction

### Why This Topic Matters

Terraform configurations are built from different types of blocks. Each block type serves a specific purpose: some configure providers, others define resources, some declare variables, and others output values. Understanding block types is like understanding the different parts of a house blueprint—you need to know what each component does.

**The Reality:**
```
Beginner: "I'll just put everything in one file and hope it works"
Expert: "I organize blocks by purpose, making code maintainable and clear"
```

**The Transformation:**
- **Before:** Copying random blocks without understanding their purpose
- **After:** Knowing exactly which block type to use for each scenario

### What You'll Learn

- The 8 main block types in Terraform
- When to use each block type
- Block anatomy and structure
- Best practices for organizing blocks
- Real-world examples for each type
- Common mistakes and how to avoid them
- Block dependencies and relationships

### The Problem Being Solved

**Scenario: Building Infrastructure**

**Without Understanding Blocks:**
```hcl
# Everything mixed together, confusing
# Is this setting up AWS or creating a resource?
# Where do I put this configuration?
# Which block can reference which?

# Result: Trial and error, hours wasted
```

**With Understanding Blocks:**
```hcl
# terraform block: Tool configuration
terraform {
  required_version = ">= 1.0"
}

# provider block: Cloud provider setup
provider "aws" {
  region = "us-east-1"
}

# variable block: Input values
variable "instance_type" {
  type = string
}

# resource block: Infrastructure component
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = var.instance_type
}

# output block: Values to display
output "instance_ip" {
  value = aws_instance.web.public_ip
}

# Result: Clear structure, easy to understand
```

---

## 2. Concept Overview

### The 8 Block Types

```
1. terraform    → Configure Terraform itself
2. provider     → Configure cloud/service providers
3. resource     → Create infrastructure components
4. data         → Query existing infrastructure
5. variable     → Define input parameters
6. output       → Export values
7. locals       → Define local computed values
8. module       → Reusable configuration packages
```

### Block Hierarchy

```
Terraform Configuration File
│
├─ terraform block (settings)
│   └─ Sets Terraform version, backend config
│
├─ provider blocks (cloud configuration)
│   └─ AWS, Azure, GCP credentials & settings
│
├─ variable blocks (inputs)
│   └─ Parameterize your configuration
│
├─ locals blocks (computed values)
│   └─ Intermediate calculations
│
├─ data blocks (queries)
│   └─ Fetch existing infrastructure info
│
├─ resource blocks (infrastructure)
│   └─ CREATE/UPDATE/DELETE infrastructure
│
├─ module blocks (reusable components)
│   └─ Call external configuration modules
│
└─ output blocks (results)
    └─ Display or export values
```

### Block Relationships

```
┌─────────────────────────────────────┐
│ terraform block                     │
│ (configures Terraform behavior)     │
└─────────────────────────────────────┘
            ↓
┌─────────────────────────────────────┐
│ provider block                      │
│ (authenticates with cloud)          │
└─────────────────────────────────────┘
            ↓
┌─────────────────────────────────────┐
│ variable block                      │
│ (receives input) ────────┐          │
└──────────────────────────┼──────────┘
            ↓              │
┌───────────────────────────┼─────────┐
│ data block                │         │
│ (queries existing) ───────┼────┐    │
└───────────────────────────┼────┼────┘
            ↓              │    │
┌───────────────────────────┼────┼────┐
│ resource block            │    │    │
│ (creates infrastructure)←─┘    │    │
└────────────────────────────────┼────┘
            ↓                    │
┌────────────────────────────────┼────┐
│ output block                   │    │
│ (displays results)←────────────┘    │
└─────────────────────────────────────┘
```

---

## 3. Core Theory

### Block Type 1: Terraform Block

**Purpose:** Configure Terraform's behavior itself

**Syntax:**
```hcl
terraform {
  # Terraform settings go here
}
```

**Common Use Cases:**
```hcl
terraform {
  # 1. Specify required Terraform version
  required_version = ">= 1.5.0"
  
  # 2. Specify required provider versions
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "~> 3.0"
    }
  }
  
  # 3. Configure backend (where state is stored)
  backend "s3" {
    bucket = "my-terraform-state"
    key    = "prod/terraform.tfstate"
    region = "us-east-1"
  }
  
  # 4. Experimental features (rarely used)
  experiments = [module_variable_optional_attrs]
}
```

**Key Points:**
- Only one `terraform` block per configuration
- Should be in root module
- Sets global Terraform behavior

### Block Type 2: Provider Block

**Purpose:** Configure cloud/service providers

**Syntax:**
```hcl
provider "<PROVIDER_NAME>" {
  # Provider-specific configuration
}
```

**Examples:**

**AWS Provider:**
```hcl
provider "aws" {
  region     = "us-east-1"
  access_key = "AKIAIOSFODNN7EXAMPLE"  # Don't hardcode!
  secret_key = "wJalrXUt..."           # Use env vars instead
  
  # Better: Use environment variables
  # AWS_ACCESS_KEY_ID
  # AWS_SECRET_ACCESS_KEY
  
  # Optional: Assume role
  assume_role {
    role_arn = "arn:aws:iam::123456789:role/TerraformRole"
  }
  
  # Optional: Default tags for all resources
  default_tags {
    tags = {
      Environment = "production"
      ManagedBy   = "Terraform"
    }
  }
}
```

**Multiple Provider Instances (Aliases):**
```hcl
# Default provider (us-east-1)
provider "aws" {
  region = "us-east-1"
}

# Additional provider for different region
provider "aws" {
  alias  = "west"
  region = "us-west-2"
}

# Usage in resource
resource "aws_instance" "east" {
  # Uses default provider (us-east-1)
  ami           = "ami-12345"
  instance_type = "t2.micro"
}

resource "aws_instance" "west" {
  # Uses aliased provider (us-west-2)
  provider      = aws.west
  ami           = "ami-67890"
  instance_type = "t2.micro"
}
```

**Multiple Providers (Different Services):**
```hcl
provider "aws" {
  region = "us-east-1"
}

provider "github" {
  token = var.github_token
}

provider "datadog" {
  api_key = var.datadog_api_key
  app_key = var.datadog_app_key
}

# Now you can manage AWS, GitHub, and Datadog together!
```

### Block Type 3: Resource Block

**Purpose:** Define infrastructure components to create

**Syntax:**
```hcl
resource "<RESOURCE_TYPE>" "<LOCAL_NAME>" {
  # Resource-specific arguments
}
```

**Anatomy:**
```hcl
resource "aws_instance" "web" {
  #       ↑              ↑
  #       |              |
  #    Resource      Local name
  #      Type      (your choice)
  
  # Required arguments
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  # Optional arguments
  key_name      = "my-key"
  monitoring    = true
  
  # Nested blocks
  tags = {
    Name = "WebServer"
  }
  
  # Meta-arguments (special Terraform arguments)
  count      = 3              # Create 3 instances
  depends_on = [aws_vpc.main] # Explicit dependency
  
  # Lifecycle customization
  lifecycle {
    create_before_destroy = true
    prevent_destroy       = true
  }
}
```

**Meta-Arguments (Work with ANY Resource):**

```hcl
# 1. count - Create multiple similar resources
resource "aws_instance" "server" {
  count         = 3
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Name = "server-${count.index}"  # server-0, server-1, server-2
  }
}

# Access: aws_instance.server[0], aws_instance.server[1], etc.

# 2. for_each - Create resources from map or set
resource "aws_instance" "server" {
  for_each = {
    web = "t2.micro"
    app = "t2.small"
    db  = "t2.medium"
  }
  
  ami           = "ami-12345"
  instance_type = each.value
  
  tags = {
    Name = "${each.key}-server"  # web-server, app-server, db-server
  }
}

# Access: aws_instance.server["web"], aws_instance.server["app"], etc.

# 3. depends_on - Explicit dependencies
resource "aws_eip" "ip" {
  instance   = aws_instance.web.id
  depends_on = [aws_internet_gateway.gw]  # Wait for IGW first
}

# 4. lifecycle - Resource behavior customization
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  lifecycle {
    create_before_destroy = true  # Create new before destroying old
    prevent_destroy       = true  # Prevent accidental deletion
    ignore_changes        = [tags] # Ignore manual tag changes
  }
}

# 5. provider - Use specific provider
resource "aws_instance" "west" {
  provider = aws.west  # Use aliased provider
  ami      = "ami-12345"
  instance_type = "t2.micro"
}
```

### Block Type 4: Data Block

**Purpose:** Query existing infrastructure (read-only)

**Syntax:**
```hcl
data "<DATA_SOURCE_TYPE>" "<LOCAL_NAME>" {
  # Query filters
}
```

**Key Difference:**
- `resource` = CREATE/UPDATE/DELETE
- `data` = READ ONLY (query existing)

**Examples:**

**Query Latest AMI:**
```hcl
data "aws_ami" "ubuntu" {
  most_recent = true
  owners      = ["099720109477"]  # Canonical (Ubuntu)
  
  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-jammy-22.04-amd64-server-*"]
  }
}

# Use in resource
resource "aws_instance" "web" {
  ami           = data.aws_ami.ubuntu.id  # Use queried AMI ID
  instance_type = "t2.micro"
}
```

**Query Existing VPC:**
```hcl
data "aws_vpc" "existing" {
  filter {
    name   = "tag:Name"
    values = ["production-vpc"]
  }
}

# Use existing VPC ID
resource "aws_subnet" "new" {
  vpc_id     = data.aws_vpc.existing.id
  cidr_block = "10.0.1.0/24"
}
```

**Query Availability Zones:**
```hcl
data "aws_availability_zones" "available" {
  state = "available"
}

# Create subnets in all available AZs
resource "aws_subnet" "public" {
  count             = length(data.aws_availability_zones.available.names)
  vpc_id            = aws_vpc.main.id
  cidr_block        = "10.0.${count.index + 1}.0/24"
  availability_zone = data.aws_availability_zones.available.names[count.index]
}
```

### Block Type 5: Variable Block

**Purpose:** Define input parameters

**Syntax:**
```hcl
variable "<NAME>" {
  type        = <TYPE>
  description = "<DESCRIPTION>"
  default     = <DEFAULT_VALUE>
  sensitive   = true/false
  validation {
    # Validation rules
  }
}
```

**Full Example:**
```hcl
variable "instance_type" {
  type        = string
  description = "EC2 instance type"
  default     = "t2.micro"
  
  validation {
    condition     = contains(["t2.micro", "t2.small", "t2.medium"], var.instance_type)
    error_message = "Instance type must be t2.micro, t2.small, or t2.medium"
  }
}

variable "environment" {
  type        = string
  description = "Environment name"
  # No default = required input
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
    Project = "MyApp"
  }
}

variable "db_password" {
  type        = string
  description = "Database password"
  sensitive   = true  # Won't show in logs
}
```

**Providing Variable Values:**

**Method 1: Command line**
```bash
terraform apply -var="environment=prod" -var="instance_type=t2.small"
```

**Method 2: terraform.tfvars file**
```hcl
# terraform.tfvars
environment    = "production"
instance_type  = "t2.small"
enable_monitoring = true
```

**Method 3: Environment variables**
```bash
export TF_VAR_environment="prod"
export TF_VAR_instance_type="t2.small"
terraform apply
```

**Method 4: Interactive prompt**
```bash
terraform apply
# Terraform will prompt for required variables without defaults
```

### Block Type 6: Output Block

**Purpose:** Export values after infrastructure creation

**Syntax:**
```hcl
output "<NAME>" {
  value       = <EXPRESSION>
  description = "<DESCRIPTION>"
  sensitive   = true/false
}
```

**Examples:**
```hcl
output "instance_id" {
  description = "ID of the EC2 instance"
  value       = aws_instance.web.id
}

output "instance_public_ip" {
  description = "Public IP address"
  value       = aws_instance.web.public_ip
}

output "all_instance_ips" {
  description = "All instance IPs"
  value       = aws_instance.web[*].public_ip  # List of all IPs
}

output "db_password" {
  description = "Database password"
  value       = random_password.db.result
  sensitive   = true  # Won't display in console
}

output "connection_string" {
  description = "Database connection string"
  value = "postgresql://${aws_db_instance.main.username}:${random_password.db.result}@${aws_db_instance.main.endpoint}/mydb"
  sensitive = true
}
```

**Using Outputs:**
```bash
# View all outputs
terraform output

# View specific output
terraform output instance_public_ip

# JSON format
terraform output -json

# Use in scripts
INSTANCE_IP=$(terraform output -raw instance_public_ip)
ssh ubuntu@$INSTANCE_IP
```

### Block Type 7: Locals Block

**Purpose:** Define local computed values (intermediate calculations)

**Syntax:**
```hcl
locals {
  <NAME> = <EXPRESSION>
}
```

**When to Use:**
- Avoid repeating complex expressions
- Compute values used multiple times
- Make code more readable

**Examples:**
```hcl
locals {
  # Computed name
  instance_name = "${var.environment}-${var.app_name}-server"
  
  # Common tags used everywhere
  common_tags = {
    Environment = var.environment
    ManagedBy   = "Terraform"
    Project     = var.project_name
  }
  
  # Conditional values
  instance_type = var.environment == "production" ? "t2.large" : "t2.micro"
  
  # Complex calculations
  subnet_cidrs = [for i in range(3) : cidrsubnet(var.vpc_cidr, 8, i)]
  
  # String manipulation
  bucket_name = lower(replace(var.app_name, "_", "-"))
}

# Use locals in resources
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = local.instance_type  # Use local value
  
  tags = merge(
    local.common_tags,  # Spread common tags
    {
      Name = local.instance_name
    }
  )
}

resource "aws_s3_bucket" "data" {
  bucket = local.bucket_name
  tags   = local.common_tags
}
```

**Variables vs Locals:**
```
Variables:
- Input from user
- Can have defaults
- Can be overridden
- Example: environment name

Locals:
- Computed within configuration
- Not user-settable
- Simplify expressions
- Example: derived instance name
```

### Block Type 8: Module Block

**Purpose:** Call reusable configuration packages

**Syntax:**
```hcl
module "<NAME>" {
  source = "<MODULE_SOURCE>"
  
  # Input variables for the module
  <INPUT_NAME> = <VALUE>
}
```

**Examples:**

**Local Module:**
```hcl
module "vpc" {
  source = "./modules/vpc"  # Path to local module
  
  # Pass variables to module
  vpc_cidr     = "10.0.0.0/16"
  environment  = var.environment
  project_name = "myapp"
}

# Access module outputs
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  subnet_id     = module.vpc.public_subnet_ids[0]  # Use module output
}
```

**Terraform Registry Module:**
```hcl
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "5.1.0"
  
  name = "my-vpc"
  cidr = "10.0.0.0/16"
  
  azs             = ["us-east-1a", "us-east-1b"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24"]
  
  enable_nat_gateway = true
  enable_vpn_gateway = false
  
  tags = {
    Environment = "dev"
  }
}
```

**GitHub Module:**
```hcl
module "consul" {
  source = "github.com/hashicorp/consul-aws?ref=v0.1.0"
  
  cluster_size = 3
  instance_type = "t2.micro"
}
```

---

## 4. Step-by-Step Walkthrough

### Complete Configuration Using All Block Types

**File: main.tf**
```hcl
# 1. TERRAFORM BLOCK - Configure Terraform
terraform {
  required_version = ">= 1.5.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
  
  backend "s3" {
    bucket = "my-terraform-state"
    key    = "dev/terraform.tfstate"
    region = "us-east-1"
  }
}

# 2. PROVIDER BLOCK - Configure AWS
provider "aws" {
  region = var.aws_region
  
  default_tags {
    tags = {
      ManagedBy = "Terraform"
      Project   = "WebApp"
    }
  }
}

# 3. VARIABLE BLOCKS - Define inputs
variable "aws_region" {
  type        = string
  description = "AWS region"
  default     = "us-east-1"
}

variable "environment" {
  type        = string
  description = "Environment name"
  validation {
    condition     = contains(["dev", "staging", "prod"], var.environment)
    error_message = "Environment must be dev, staging, or prod"
  }
}

variable "instance_count" {
  type        = number
  description = "Number of instances"
  default     = 2
}

# 4. LOCALS BLOCK - Computed values
locals {
  instance_name = "${var.environment}-web-server"
  
  common_tags = {
    Environment = var.environment
    Terraform   = "true"
  }
  
  instance_type = var.environment == "prod" ? "t2.small" : "t2.micro"
}

# 5. DATA BLOCK - Query existing resources
data "aws_ami" "ubuntu" {
  most_recent = true
  owners      = ["099720109477"]
  
  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-jammy-22.04-amd64-server-*"]
  }
}

data "aws_availability_zones" "available" {
  state = "available"
}

# 6. RESOURCE BLOCKS - Create infrastructure
resource "aws_vpc" "main" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  
  tags = merge(local.common_tags, {
    Name = "${var.environment}-vpc"
  })
}

resource "aws_subnet" "public" {
  count                   = 2
  vpc_id                  = aws_vpc.main.id
  cidr_block              = "10.0.${count.index + 1}.0/24"
  availability_zone       = data.aws_availability_zones.available.names[count.index]
  map_public_ip_on_launch = true
  
  tags = merge(local.common_tags, {
    Name = "${var.environment}-public-subnet-${count.index + 1}"
  })
}

resource "aws_instance" "web" {
  count         = var.instance_count
  ami           = data.aws_ami.ubuntu.id
  instance_type = local.instance_type
  subnet_id     = aws_subnet.public[count.index % 2].id
  
  tags = merge(local.common_tags, {
    Name = "${local.instance_name}-${count.index + 1}"
  })
}

# 7. MODULE BLOCK - Use reusable module
module "security_group" {
  source = "./modules/security-group"
  
  vpc_id      = aws_vpc.main.id
  environment = var.environment
  
  ingress_rules = [
    {
      port        = 80
      cidr_blocks = ["0.0.0.0/0"]
    },
    {
      port        = 443
      cidr_blocks = ["0.0.0.0/0"]
    }
  ]
}

# 8. OUTPUT BLOCKS - Export values
output "vpc_id" {
  description = "ID of the VPC"
  value       = aws_vpc.main.id
}

output "instance_ids" {
  description = "IDs of all instances"
  value       = aws_instance.web[*].id
}

output "instance_ips" {
  description = "Public IPs of all instances"
  value       = aws_instance.web[*].public_ip
}

output "security_group_id" {
  description = "Security group ID from module"
  value       = module.security_group.sg_id
}
```

**Run it:**
```bash
# Initialize
terraform init

# Validate syntax
terraform validate

# Plan with variable
terraform plan -var="environment=dev"

# Apply
terraform apply -var="environment=dev"

# View outputs
terraform output
```

---

## 5. Practical Examples

### Example 1: Resource with All Meta-Arguments

```hcl
resource "aws_instance" "app" {
  # Regular arguments
  ami           = data.aws_ami.ubuntu.id
  instance_type = "t2.micro"
  
  # count meta-argument
  count = 3
  
  # depends_on meta-argument
  depends_on = [aws_internet_gateway.main]
  
  # provider meta-argument
  provider = aws.east
  
  # lifecycle meta-argument
  lifecycle {
    create_before_destroy = true
    prevent_destroy       = false
    ignore_changes        = [tags["Created"]]
  }
  
  tags = {
    Name    = "app-${count.index}"
    Created = timestamp()
  }
}
```

### Example 2: Data Source for Dynamic Configuration

```hcl
# Query current AWS account info
data "aws_caller_identity" "current" {}

# Query current region
data "aws_region" "current" {}

# Use in resources
resource "aws_s3_bucket" "logs" {
  bucket = "logs-${data.aws_caller_identity.current.account_id}-${data.aws_region.current.name}"
  # Result: logs-123456789012-us-east-1
  
  tags = {
    Account = data.aws_caller_identity.current.account_id
    Region  = data.aws_region.current.name
  }
}

# Output account info
output "account_id" {
  value = data.aws_caller_identity.current.account_id
}
```

### Example 3: Complex Locals

```hcl
locals {
  # Environment-specific configurations
  config = {
    dev = {
      instance_type = "t2.micro"
      instance_count = 1
      enable_backup = false
    }
    staging = {
      instance_type = "t2.small"
      instance_count = 2
      enable_backup = true
    }
    prod = {
      instance_type = "t2.large"
      instance_count = 5
      enable_backup = true
    }
  }
  
  # Get config for current environment
  env_config = local.config[var.environment]
  
  # Conditional subnet CIDRs
  subnet_cidrs = [for i in range(local.env_config.instance_count) : cidrsubnet(var.vpc_cidr, 8, i)]
  
  # Flattened list for multiple resources
  instance_subnet_pairs = flatten([
    for i in range(local.env_config.instance_count) : {
      instance_index = i
      subnet_cidr    = local.subnet_cidrs[i]
    }
  ])
}

resource "aws_instance" "app" {
  count         = local.env_config.instance_count
  instance_type = local.env_config.instance_type
  ami           = data.aws_ami.ubuntu.id
  
  tags = {
    Name = "app-${count.index}"
  }
}
```

---

## 6. Deep Dive

### Block Evaluation Order

**Terraform evaluates blocks in dependency order, not file order:**

```hcl
# File position doesn't matter!

# This resource is created FIRST (no dependencies)
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"
}

# This is created SECOND (depends on VPC)
resource "aws_subnet" "public" {
  vpc_id     = aws_vpc.main.id  # Dependency detected!
  cidr_block = "10.0.1.0/24"
}

# This is created THIRD (depends on subnet)
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  subnet_id     = aws_subnet.public.id  # Dependency detected!
}
```

**Dependency Graph:**
```
aws_vpc.main
    ↓
aws_subnet.public
    ↓
aws_instance.web
```

**View dependency graph:**
```bash
terraform graph | dot -Tpng > graph.png
```

### Implicit vs Explicit Dependencies

**Implicit (Automatic):**
```hcl
resource "aws_instance" "web" {
  subnet_id = aws_subnet.public.id  # Terraform detects dependency
}
```

**Explicit (Manual):**
```hcl
resource "aws_eip" "ip" {
  instance = aws_instance.web.id
  
  # Force dependency even if not directly referenced
  depends_on = [aws_internet_gateway.main]
}
```

---

## 7. Trade-offs & Pitfalls

### Common Mistakes

**Mistake 1: Hardcoding values instead of using variables**
```hcl
# Bad
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  tags = {
    Environment = "production"
  }
}

# Good
resource "aws_instance" "web" {
  ami           = var.ami_id
  instance_type = var.instance_type
  tags = {
    Environment = var.environment
  }
}
```

**Mistake 2: Mixing locals and variables**
```hcl
# Wrong: Can't reference var in locals definition at top level
locals {
  instance_name = var.environment  # This works
}

variable "derived_name" {
  default = local.instance_name  # ERROR: Can't reference local in variable
}
```

**Mistake 3: Circular dependencies**
```hcl
# This will fail!
resource "aws_instance" "a" {
  depends_on = [aws_instance.b]
}

resource "aws_instance" "b" {
  depends_on = [aws_instance.a]
}
# Error: Cycle detected
```

---

## 8. Mental Models & Analogies

### Analogy: Building a House

**terraform block** = Building permit (rules and regulations)
**provider block** = Contractor (who does the work)
**variable block** = Customer requirements (inputs)
**locals block** = Architect's calculations (derived values)
**data block** = Site survey (existing conditions)
**resource block** = Actual construction (building components)
**module block** = Prefab sections (reusable blueprints)
**output block** = Final inspection report (results)

---

## 9. Troubleshooting Guide

### Problem: "Error: Reference to undeclared resource"

**Diagnosis:**
```
Error: Reference to undeclared resource
│ 
│   on main.tf line 10, in resource "aws_subnet" "private":
│   10:   vpc_id = aws_vpc.app.id
│ 
│ A managed resource "aws_vpc" "app" has not been declared in the root module.
```

**Solution:**
```hcl
# Make sure the referenced resource exists
resource "aws_vpc" "app" {  # Must match exactly
  cidr_block = "10.0.0.0/16"
}
```

### Problem: "Error: Unsupported block type"

**Cause:** Typo in block type

**Solution:**
```hcl
# Wrong
ressource "aws_instance" "web" { }  # Typo

# Correct
resource "aws_instance" "web" { }
```

---

## 10. Frequently Asked Questions

**Q1: Can I have multiple terraform blocks?**
**A:** No, only one per configuration.

**Q2: Do I need a provider block for every resource?**
**A:** No, one provider block is enough for all resources of that type.

**Q3: What's the difference between variable and local?**
**A:** Variable = user input, Local = computed value.

**Q4: Can I access one module's output in another module?**
**A:** Yes: `module.module_name.output_name`

**Q5: Are data sources free (no cost)?**
**A:** Yes, they only query; they don't create resources.

**Q6: Can I use count and for_each together?**
**A:** No, choose one or the other.

**Q7: How do I know what arguments a resource needs?**
**A:** Check Terraform Registry documentation for that resource.

**Q8: Can outputs reference other outputs?**
**A:** Yes, outputs can reference other outputs.

**Q9: Do I need to declare variables in order?**
**A:** No, Terraform evaluates them as needed.

**Q10: Can I have multiple provider blocks for the same provider?**
**A:** Yes, using aliases for multi-region/multi-account setups.

---

## 11. Key Takeaways

✅ **8 block types** – Each serves a specific purpose
✅ **terraform block** – Configure Terraform itself
✅ **provider block** – Configure cloud providers
✅ **resource block** – Create infrastructure (main workhorses)
✅ **data block** – Query existing infrastructure
✅ **variable block** – Parameterize configurations
✅ **output block** – Export values
✅ **locals block** – Simplify complex expressions
✅ **module block** – Reuse configurations
✅ **Dependencies** – Terraform handles automatically (usually)

---

## 12. Practice Exercises

### Exercise 1: Create Complete Configuration
```
Task: Create a configuration with:
- 1 terraform block (version >= 1.5)
- 1 provider block (AWS, your region)
- 2 variable blocks (region, instance_type)
- 1 locals block (compute instance name)
- 1 data block (query Ubuntu AMI)
- 1 resource block (EC2 instance)
- 2 output blocks (instance ID and IP)
```

### Exercise 2: Multi-Region Setup
```
Task: Configure two providers (us-east-1 and us-west-2)
Create an S3 bucket in each region
Output both bucket names
```

### Exercise 3: Complex Locals
```
Task: Create locals that:
- Compute environment-specific instance types
- Generate subnet CIDRs dynamically
- Build common tags
```

---

## 13. Further Reading

- Terraform Block Types Documentation
- Resource Meta-Arguments Guide
- Module Development Documentation
- Terraform Registry (resource reference)

---

*Block Mastery Achieved!*
*Ready to build complete infrastructure*
