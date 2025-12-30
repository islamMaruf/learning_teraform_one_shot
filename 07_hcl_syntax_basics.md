# Chapter 7: HCL Syntax Basics – The Language of Terraform

## Prerequisites
- Terraform installed (Chapter 7)
- AWS CLI configured
- Basic programming familiarity helpful
- Text editor or VS Code
- Estimated reading time: 35-40 minutes

## 1. Introduction

### Why This Topic Matters

HCL (HashiCorp Configuration Language) is the language Terraform speaks. Understanding HCL syntax is like learning the grammar of infrastructure code. Without it, you're guessing. With it, you can write powerful, maintainable infrastructure configurations.

**The Reality:**
```
Poor HCL understanding = Copy-paste code, mysterious errors
Good HCL understanding = Write infrastructure from scratch confidently
```

**The Transformation:**
- **Before:** "I'll just copy this from Google and hope it works"
- **After:** "I understand exactly what each line does and can customize it"

### What You'll Learn

- HCL syntax fundamentals (blocks, arguments, expressions)
- Comments and formatting rules
- Data types (string, number, bool, list, map, object)
- Interpolation and string templates
- Expressions and operators
- Conditionals and loops
- Functions basics
- Best practices for readable HCL

### The Problem Being Solved

**Scenario: New to Terraform**

**Without HCL Knowledge:**
```hcl
# Copied from internet, no idea what it means
resource "aws_instance" "example" {
  ami = "${data.aws_ami.ubuntu.id}"  # Why the ${}?
  instance_type = var.instance_type  # What's 'var'?
  count = 3  # Can I use 'count' anywhere?
  
  tags = {  # Why curly braces here?
    Name = "Server-${count.index}"  # What's count.index?
  }
}
# Result: Cargo-cult programming, fragile changes
```

**With HCL Knowledge:**
```hcl
# I understand every symbol
resource "aws_instance" "example" {
  ami           = data.aws_ami.ubuntu.id  # Reference to data source
  instance_type = var.instance_type        # Variable reference
  count         = 3                        # Meta-argument for 3 instances
  
  tags = {                                 # Map data type
    Name = "Server-${count.index}"         # Interpolation: Server-0, Server-1, Server-2
  }
}
# Result: Confident modifications, predictable outcomes
```

---

## 2. Concept Overview

### What is HCL?

**HCL (HashiCorp Configuration Language)** is a declarative configuration language designed by HashiCorp for infrastructure as code. It's designed to be human-readable and machine-friendly.

**Simple Definition:**
HCL is like JSON, but made for humans. It's easier to read and write, with support for comments, variables, and expressions.

### HCL Design Goals

```
1. Human-Readable
   ↓
   Sysadmins and developers can read it easily

2. Machine-Parseable
   ↓
   Terraform can interpret it unambiguously

3. Expressive
   ↓
   Support complex infrastructure patterns

4. Declarative
   ↓
   Describe WHAT you want, not HOW to create it
```

### HCL vs JSON vs YAML

**Same Configuration in Different Formats:**

**HCL (Native Terraform):**
```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Name = "WebServer"
  }
}
```

**JSON (Also valid in Terraform):**
```json
{
  "resource": {
    "aws_instance": {
      "web": {
        "ami": "ami-12345",
        "instance_type": "t2.micro",
        "tags": {
          "Name": "WebServer"
        }
      }
    }
  }
}
```

**YAML (Not valid in Terraform, but for comparison):**
```yaml
resource:
  aws_instance:
    web:
      ami: ami-12345
      instance_type: t2.micro
      tags:
        Name: WebServer
```

**Winner:** HCL (cleanest, most readable)

### Key Terminology

**Block:**
- Fundamental unit in HCL
- Contains configuration
- Has type, labels, and body
- Example: `resource "aws_instance" "web" { ... }`

**Argument:**
- Assignment within a block
- Format: `name = value`
- Example: `ami = "ami-12345"`

**Expression:**
- Produces a value
- Can be literal, reference, or computed
- Example: `var.region`, `"us-east-1"`, `count.index + 1`

**Attribute:**
- Property of a resource
- Accessed via dot notation
- Example: `aws_instance.web.id`

---

## 3. Core Theory

### The Building Blocks of HCL

#### 1. Block Structure

**Anatomy of a Block:**
```hcl
<BLOCK TYPE> "<BLOCK LABEL>" "<BLOCK LABEL>" {
  # Block body
  <IDENTIFIER> = <EXPRESSION>  # Argument
}
```

**Example:**
```hcl
resource "aws_instance" "example" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
}
```

**Breakdown:**
- `resource` = Block type
- `"aws_instance"` = First label (resource type)
- `"example"` = Second label (resource name)
- `{ ... }` = Block body
- `ami = "ami-12345"` = Argument

#### 2. Block Types in Terraform

```hcl
# Terraform Settings Block
terraform {
  required_version = ">= 1.0"
}

# Provider Block
provider "aws" {
  region = "us-east-1"
}

# Resource Block
resource "aws_instance" "web" {
  ami = "ami-12345"
}

# Data Source Block
data "aws_ami" "ubuntu" {
  most_recent = true
}

# Variable Block
variable "instance_type" {
  type = string
}

# Output Block
output "instance_ip" {
  value = aws_instance.web.public_ip
}

# Locals Block
locals {
  common_tags = {
    Environment = "dev"
  }
}

# Module Block
module "vpc" {
  source = "./modules/vpc"
}
```

#### 3. Arguments and Attributes

**Argument (input you provide):**
```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"     # Argument: you set this
  instance_type = "t2.micro"      # Argument: you set this
}
```

**Attribute (output you read):**
```hcl
output "instance_id" {
  value = aws_instance.web.id           # Attribute: AWS provides this
}

output "public_ip" {
  value = aws_instance.web.public_ip    # Attribute: AWS provides this
}
```

### Data Types

#### Primitive Types

**1. String**
```hcl
variable "region" {
  type    = string
  default = "us-east-1"
}

# Usage
region = "us-west-2"
name   = "my-server"
```

**2. Number**
```hcl
variable "instance_count" {
  type    = number
  default = 3
}

# Usage
count         = 5
port          = 443
cpu_credits   = 1.5  # Can be decimal
```

**3. Bool**
```hcl
variable "enable_monitoring" {
  type    = bool
  default = true
}

# Usage
monitoring_enabled = true
encrypted          = false
```

#### Complex Types

**4. List**
```hcl
variable "availability_zones" {
  type    = list(string)
  default = ["us-east-1a", "us-east-1b"]
}

# Usage
zones = ["us-east-1a", "us-east-1b", "us-east-1c"]

# Access elements
first_zone  = var.availability_zones[0]  # "us-east-1a"
second_zone = var.availability_zones[1]  # "us-east-1b"
```

**5. Map**
```hcl
variable "tags" {
  type = map(string)
  default = {
    Environment = "dev"
    Project     = "website"
  }
}

# Usage
instance_tags = {
  Name        = "web-server"
  Environment = "production"
}

# Access values
env = var.tags["Environment"]  # "dev"
```

**6. Object**
```hcl
variable "server_config" {
  type = object({
    name          = string
    instance_type = string
    disk_size     = number
    monitoring    = bool
  })
  default = {
    name          = "default-server"
    instance_type = "t2.micro"
    disk_size     = 20
    monitoring    = true
  }
}

# Usage
config = {
  name          = "web-server"
  instance_type = "t2.small"
  disk_size     = 50
  monitoring    = false
}
```

**7. Tuple**
```hcl
variable "mixed_list" {
  type    = tuple([string, number, bool])
  default = ["web", 8080, true]
}

# Fixed-length, mixed-type list
```

### Comments

```hcl
# Single-line comment (most common)

// Alternative single-line comment

/*
  Multi-line comment
  Useful for documentation
  or temporarily disabling code
*/

resource "aws_instance" "web" {
  ami = "ami-12345"  # Inline comment
  
  # This is disabled:
  # instance_type = "t2.large"
  
  instance_type = "t2.micro"  # Actually used
}
```

---

## 4. Step-by-Step Walkthrough

### Example 1: Basic Syntax Practice

**Create a file: `syntax-basics.tf`**

```hcl
# Step 1: Define provider
provider "aws" {
  region = "us-east-1"  # Argument with string value
}

# Step 2: Define variables
variable "instance_type" {
  type        = string
  description = "EC2 instance type"
  default     = "t2.micro"
}

variable "environment" {
  type    = string
  default = "dev"
}

# Step 3: Define locals (computed values)
locals {
  instance_name = "${var.environment}-web-server"
  common_tags = {
    Environment = var.environment
    ManagedBy   = "Terraform"
  }
}

# Step 4: Create resource
resource "aws_instance" "web" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = var.instance_type  # Variable reference
  
  tags = merge(
    local.common_tags,  # Local reference
    {
      Name = local.instance_name
    }
  )
}

# Step 5: Define output
output "instance_id" {
  description = "ID of the EC2 instance"
  value       = aws_instance.web.id  # Attribute reference
}

output "public_ip" {
  description = "Public IP address"
  value       = aws_instance.web.public_ip
}
```

**Run it:**
```bash
terraform init
terraform validate  # Check syntax
terraform fmt       # Auto-format
terraform plan      # Preview
```

---

## 5. Practical Examples

### Example 1: String Interpolation

```hcl
variable "environment" {
  default = "production"
}

variable "app_name" {
  default = "webapp"
}

resource "aws_s3_bucket" "app" {
  # String interpolation with ${}
  bucket = "${var.app_name}-${var.environment}-data"
  # Result: "webapp-production-data"
  
  tags = {
    Name = "${upper(var.app_name)}-${var.environment}"
    # Result: "WEBAPP-production"
  }
}

# Modern syntax (Terraform >= 0.12)
resource "aws_instance" "web" {
  ami = "ami-12345"
  
  # Can omit ${} for simple references
  instance_type = var.instance_type
  
  # But need ${} in strings
  tags = {
    Name = "${var.environment}-server"  # Must use ${}
  }
}
```

### Example 2: Conditionals

```hcl
variable "environment" {
  default = "dev"
}

variable "enable_monitoring" {
  type    = bool
  default = false
}

resource "aws_instance" "web" {
  ami           = "ami-12345"
  
  # Conditional expression: condition ? true_val : false_val
  instance_type = var.environment == "production" ? "t2.large" : "t2.micro"
  # If production: t2.large, else: t2.micro
  
  # Conditional with boolean
  monitoring = var.enable_monitoring ? true : false
  
  tags = {
    Name = var.environment == "production" ? "prod-server" : "dev-server"
  }
}

# Conditional resource creation with count
resource "aws_eip" "web" {
  # Create EIP only in production
  count    = var.environment == "production" ? 1 : 0
  instance = aws_instance.web.id
}
```

### Example 3: Lists and Loops

```hcl
variable "availability_zones" {
  type    = list(string)
  default = ["us-east-1a", "us-east-1b", "us-east-1c"]
}

# Create multiple subnets with count
resource "aws_subnet" "public" {
  count             = length(var.availability_zones)
  vpc_id            = aws_vpc.main.id
  cidr_block        = "10.0.${count.index + 1}.0/24"
  availability_zone = var.availability_zones[count.index]
  
  tags = {
    Name = "public-subnet-${count.index + 1}"
  }
}

# Access created subnets
output "subnet_ids" {
  value = aws_subnet.public[*].id  # Splat expression
  # Result: ["subnet-abc123", "subnet-def456", "subnet-ghi789"]
}
```

### Example 4: Maps

```hcl
variable "instance_types" {
  type = map(string)
  default = {
    dev     = "t2.micro"
    staging = "t2.small"
    prod    = "t2.large"
  }
}

variable "environment" {
  default = "dev"
}

resource "aws_instance" "web" {
  ami = "ami-12345"
  
  # Look up value from map
  instance_type = var.instance_types[var.environment]
  # If environment = "prod", uses "t2.large"
  
  tags = {
    Environment = var.environment
  }
}

# Another example: AMIs per region
variable "ami_ids" {
  type = map(string)
  default = {
    us-east-1 = "ami-12345"
    us-west-2 = "ami-67890"
    eu-west-1 = "ami-abcde"
  }
}

variable "region" {
  default = "us-east-1"
}

provider "aws" {
  region = var.region
}

resource "aws_instance" "web" {
  ami           = var.ami_ids[var.region]  # Automatic region-specific AMI
  instance_type = "t2.micro"
}
```

### Example 5: For Expressions

```hcl
variable "users" {
  type    = list(string)
  default = ["alice", "bob", "charlie"]
}

# Create IAM users with for expression
locals {
  user_emails = [for user in var.users : "${user}@example.com"]
  # Result: ["alice@example.com", "bob@example.com", "charlie@example.com"]
  
  # For with condition (if)
  admin_users = [for user in var.users : user if user != "bob"]
  # Result: ["alice", "charlie"]
  
  # For with map output
  user_map = {for user in var.users : user => "${user}@example.com"}
  # Result: {
  #   alice   = "alice@example.com"
  #   bob     = "bob@example.com"
  #   charlie = "charlie@example.com"
  # }
}

output "emails" {
  value = local.user_emails
}
```

### Example 6: Dynamic Blocks

```hcl
variable "ingress_rules" {
  type = list(object({
    port        = number
    protocol    = string
    cidr_blocks = list(string)
  }))
  default = [
    {
      port        = 80
      protocol    = "tcp"
      cidr_blocks = ["0.0.0.0/0"]
    },
    {
      port        = 443
      protocol    = "tcp"
      cidr_blocks = ["0.0.0.0/0"]
    },
    {
      port        = 22
      protocol    = "tcp"
      cidr_blocks = ["10.0.0.0/8"]
    }
  ]
}

resource "aws_security_group" "web" {
  name        = "web-sg"
  description = "Security group for web servers"
  
  # Dynamic block for multiple ingress rules
  dynamic "ingress" {
    for_each = var.ingress_rules
    content {
      from_port   = ingress.value.port
      to_port     = ingress.value.port
      protocol    = ingress.value.protocol
      cidr_blocks = ingress.value.cidr_blocks
    }
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

---

## 6. Deep Dive

### Operator Precedence

```hcl
# Arithmetic operators (highest to lowest precedence)
result = 10 + 5 * 2      # 20 (multiplication first)
result = (10 + 5) * 2    # 30 (parentheses highest)

# Comparison operators
is_equal     = 5 == 5    # true
is_not_equal = 5 != 3    # true
greater      = 10 > 5    # true
less_equal   = 5 <= 5    # true

# Logical operators
and_result = true && false   # false
or_result  = true || false   # true
not_result = !true           # false

# String operators
concatenation = "${var.first}_${var.last}"  # Interpolation
```

### Built-in Functions (Preview)

```hcl
# String functions
upper_case   = upper("hello")              # "HELLO"
lower_case   = lower("HELLO")              # "hello"
title_case   = title("hello world")        # "Hello World"
trim_string  = trimspace("  hello  ")      # "hello"

# Numeric functions
minimum      = min(5, 10, 3)               # 3
maximum      = max(5, 10, 3)               # 10
absolute     = abs(-5)                     # 5
ceiling      = ceil(4.3)                   # 5
floor_value  = floor(4.7)                  # 4

# Collection functions
list_length  = length(["a", "b", "c"])     # 3
contains_val = contains(["a", "b"], "a")   # true
index_of     = index(["a", "b", "c"], "b") # 1

# Type conversion
to_string    = tostring(42)                # "42"
to_number    = tonumber("42")              # 42
to_bool      = tobool("true")              # true
```

### Expression Examples

```hcl
locals {
  # Arithmetic
  total_instances = 3 + 2                        # 5
  percentage      = (100 / 4) * 3                # 75
  
  # String concatenation
  full_name       = "${var.first_name} ${var.last_name}"
  
  # Conditional
  env_type        = var.is_prod ? "production" : "development"
  
  # Null coalescing
  region          = var.custom_region != null ? var.custom_region : "us-east-1"
  
  # List indexing
  first_az        = var.availability_zones[0]
  
  # Map lookup
  instance_size   = var.sizes[var.environment]
  
  # Splat expression (get all IDs)
  all_instance_ids = aws_instance.web[*].id
  
  # For expression
  uppercase_names  = [for name in var.names : upper(name)]
}
```

---

## 7. Trade-offs & Pitfalls

### Common Mistakes

**Mistake 1: Missing $ in interpolation**
```hcl
# Wrong:
name = "var.environment-server"
# Result: Literal string "var.environment-server"

# Correct:
name = "${var.environment}-server"
# Result: "dev-server"
```

**Mistake 2: Using = instead of ==**
```hcl
# Wrong:
instance_type = var.environment = "production" ? "large" : "small"
# Syntax error

# Correct:
instance_type = var.environment == "production" ? "large" : "small"
```

**Mistake 3: Forgetting quotes around resource names**
```hcl
# Wrong:
resource aws_instance web {  # Missing quotes
}

# Correct:
resource "aws_instance" "web" {
}
```

**Mistake 4: Accessing wrong index**
```hcl
variable "zones" {
  default = ["us-east-1a", "us-east-1b"]
}

# Wrong:
zone = var.zones[2]  # Index out of range (only 0 and 1 exist)

# Correct:
zone = var.zones[0]  # or var.zones[1]
```

---

## 8. Mental Models & Analogies

### Analogy: HCL is Like Lego Instructions

**Blocks = Lego Pieces**
- Each block is a component
- Fits together in specific ways
- Has inputs (arguments) and outputs (attributes)

**Arguments = Configuration**
- Customize each piece
- Required vs optional arguments

**References = Connecting Pieces**
- `aws_instance.web.id` = This piece connects to that piece

---

## 9. Troubleshooting Guide

### Problem: "Syntax error in configuration"

**Check:**
```bash
terraform validate

# Common causes:
# 1. Missing closing brace }
# 2. Typo in block type
# 3. Invalid character
```

**Solution:**
```bash
# Use formatter to catch issues:
terraform fmt -check
terraform fmt -recursive  # Fix formatting
```

---

## 10. Frequently Asked Questions

**Q1: Can I use JSON instead of HCL?**
**A:** Yes, Terraform accepts JSON, but HCL is more readable.

**Q2: Are indentation and spacing important?**
**A:** No (for functionality), but yes (for readability). Use `terraform fmt`.

**Q3: What's the difference between single quotes and double quotes?**
**A:** Terraform only accepts double quotes for strings. Single quotes are invalid.

**Q4: Can I split configuration across multiple files?**
**A:** Yes! Terraform reads all `.tf` files in a directory.

**Q5: How do I comment out multiple lines?**
**A:** Use `/* ... */` or add `#` to each line.

---

## 11. Key Takeaways

✅ **HCL is block-based** – Everything is a block with arguments
✅ **Data types matter** – String, number, bool, list, map, object
✅ **Interpolation with ${}** – Embed expressions in strings
✅ **Conditionals with ternary** – `condition ? true_val : false_val`
✅ **Lists accessed with []** – Zero-indexed
✅ **Maps accessed with []** or dot notation
✅ **Comments with #** – Most common
✅ **terraform fmt** – Auto-format your code

---

## 12. Practice Exercises

### Exercise 1: Variable Declaration
Create variables for environment, instance type, and region with defaults.

### Exercise 2: String Interpolation
Create a resource name combining environment and application name.

### Exercise 3: Conditional Instance
Create an instance with size based on environment (production = large, dev = micro).

### Exercise 4: List Iteration
Create 3 subnets in different availability zones using count.

### Exercise 5: Map Lookup
Create a map of AMI IDs per region and use lookup.

---

## 13. Further Reading

- Official HCL Syntax Documentation
- Terraform Language Reference
- HCL GitHub Repository

---

*HCL Mastery Unlocked!*
*Next: Understanding block types in depth*
