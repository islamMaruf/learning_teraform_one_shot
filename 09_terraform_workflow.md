# Chapter 9: Terraform Workflow – Write, Plan, Apply

## Prerequisites
- Understanding of block types (Chapter 9)
- HCL syntax knowledge (Chapter 8)
- Terraform installed and configured (Chapter 7)
- AWS account with credentials configured
- Estimated reading time: 30-35 minutes

## 1. Introduction

### Why This Topic Matters

The Terraform workflow is the heartbeat of infrastructure as code. It's not just about writing configuration—it's about safely reviewing, planning, and applying changes. Understanding this workflow prevents disasters and builds confidence.

**The Reality:**
```
Amateur: terraform apply (hope for the best)
Professional: Write → Format → Validate → Plan → Review → Apply → Verify
```

**The Stakes:**
- **Wrong:** Delete production database by accident
- **Right:** Preview all changes before applying

### What You'll Learn

- The core Terraform workflow (Write-Plan-Apply)
- Essential Terraform commands
- How to safely make infrastructure changes
- Rollback and disaster recovery
- Best practices for team workflows
- Common pitfalls and how to avoid them
- Real-world scenarios and solutions

### The Problem Being Solved

**Scenario: Making Infrastructure Changes**

**Without Workflow:**
```bash
# Cowboy approach
vim main.tf  # Make changes
terraform apply  # YOLO!
# Oh no, I just deleted production!
```

**With Proper Workflow:**
```bash
# Professional approach
vim main.tf                    # Write changes
terraform fmt                  # Format code
terraform validate             # Check syntax
terraform plan                 # Preview changes
# Review output carefully
terraform apply                # Apply after approval
# Verify changes worked
terraform show                 # Inspect current state
```

---

## 2. Concept Overview

### The Core Workflow (3 Steps)

```
┌─────────────────────────────────────────────┐
│ STEP 1: WRITE                               │
│ Create or modify .tf files                  │
│ Define desired infrastructure state         │
└─────────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────────┐
│ STEP 2: PLAN                                │
│ terraform plan                              │
│ Preview what will change                    │
│ Review additions, modifications, deletions  │
└─────────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────────┐
│ STEP 3: APPLY                               │
│ terraform apply                             │
│ Execute changes                             │
│ Update state file                           │
└─────────────────────────────────────────────┘
```

### The Complete Professional Workflow

```
1. INIT         → terraform init
   ↓             (Download providers, initialize backend)
   
2. WRITE        → Edit .tf files
   ↓             (Define infrastructure)
   
3. FORMAT       → terraform fmt
   ↓             (Auto-format code)
   
4. VALIDATE     → terraform validate
   ↓             (Check syntax errors)
   
5. PLAN         → terraform plan
   ↓             (Preview changes)
   
6. REVIEW       → Human review
   ↓             (Verify plan output)
   
7. APPLY        → terraform apply
   ↓             (Execute changes)
   
8. VERIFY       → Manual verification
   ↓             (Confirm in AWS console)
   
9. COMMIT       → git commit & push
                 (Version control)
```

### Key Terraform Commands

| Command | Purpose | When to Use |
|---------|---------|-------------|
| `terraform init` | Initialize working directory | First time, after adding providers |
| `terraform fmt` | Format code | Before commit |
| `terraform validate` | Check syntax | After writing code |
| `terraform plan` | Preview changes | Before apply |
| `terraform apply` | Execute changes | After reviewing plan |
| `terraform destroy` | Delete all resources | Cleanup, testing |
| `terraform show` | Inspect current state | Check what exists |
| `terraform output` | Display output values | Get resource info |
| `terraform state` | Manage state | Advanced operations |
| `terraform refresh` | Update state | Sync with reality |
| `terraform import` | Import existing resources | Bring unmanaged resources |
| `terraform taint` | Mark for recreation | Force resource rebuild |

---

## 3. Core Theory

### Command 1: terraform init

**Purpose:** Initialize Terraform working directory

**What it does:**
1. Downloads provider plugins
2. Initializes backend configuration
3. Creates `.terraform` directory
4. Generates lock file

**When to run:**
- First time in a new directory
- After adding new providers
- After changing backend configuration
- After cloning a repo

**Example:**
```bash
terraform init

# Output:
# Initializing the backend...
# Initializing provider plugins...
# - Finding hashicorp/aws versions matching "~> 5.0"...
# - Installing hashicorp/aws v5.31.0...
# Terraform has been successfully initialized!
```

**Options:**
```bash
terraform init -upgrade          # Upgrade providers to latest
terraform init -reconfigure      # Reconfigure backend
terraform init -migrate-state    # Migrate state to new backend
terraform init -backend=false    # Skip backend initialization
```

### Command 2: terraform fmt

**Purpose:** Format code to canonical style

**What it does:**
- Fixes indentation
- Aligns arguments
- Sorts arguments alphabetically (in blocks)
- Makes code consistent

**Example:**
```bash
# Before formatting
resource "aws_instance" "web"{
ami="ami-12345"
  instance_type     ="t2.micro"
    tags={
Name="WebServer"
    }
}

# Run formatter
terraform fmt

# After formatting
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  tags = {
    Name = "WebServer"
  }
}
```

**Options:**
```bash
terraform fmt                    # Format current directory
terraform fmt -recursive         # Format all subdirectories
terraform fmt -check             # Check if formatting needed (CI/CD)
terraform fmt -diff              # Show differences
```

### Command 3: terraform validate

**Purpose:** Validate configuration syntax

**What it checks:**
- Syntax errors
- Invalid resource types
- Invalid argument names
- Missing required arguments
- Type mismatches

**Example:**
```bash
terraform validate

# Success:
# Success! The configuration is valid.

# Error example:
# Error: Unsupported argument
# │ 
# │   on main.tf line 10, in resource "aws_instance" "web":
# │   10:   ami_id = "ami-12345"
# │ 
# │ An argument named "ami_id" is not expected here. Did you mean "ami"?
```

**When to run:**
- After writing/modifying code
- Before committing to git
- In CI/CD pipelines

### Command 4: terraform plan

**Purpose:** Preview infrastructure changes

**What it shows:**
- Resources to be created (+)
- Resources to be modified (~)
- Resources to be destroyed (-)
- Unchanged resources (no symbol)

**Example output:**
```bash
terraform plan

# Terraform will perform the following actions:
#
# # aws_instance.web will be created
# + resource "aws_instance" "web" {
#     + ami           = "ami-12345"
#     + instance_type = "t2.micro"
#     + id            = (known after apply)
#     + public_ip     = (known after apply)
#   }
#
# # aws_s3_bucket.logs will be modified
# ~ resource "aws_s3_bucket" "logs" {
#     ~ tags = {
#         + Environment = "production"
#       }
#   }
#
# # aws_instance.old will be destroyed
# - resource "aws_instance" "old" {
#     - ami           = "ami-67890"
#     - instance_type = "t2.micro"
#   }
#
# Plan: 1 to add, 1 to change, 1 to destroy.
```

**Key symbols:**
- `+` = Create
- `-` = Destroy
- `~` = Modify in-place
- `-/+` = Destroy then recreate
- `<=` = Read during apply

**Options:**
```bash
terraform plan -out=plan.tfplan   # Save plan to file
terraform plan -destroy           # Preview destroy operation
terraform plan -target=resource   # Plan for specific resource
terraform plan -var="env=prod"    # Override variables
```

### Command 5: terraform apply

**Purpose:** Execute planned changes

**What it does:**
1. Runs plan again (unless using saved plan)
2. Shows preview
3. Asks for confirmation
4. Creates/modifies/destroys resources
5. Updates state file

**Interactive apply:**
```bash
terraform apply

# Shows plan output...
# Do you want to perform these actions?
#   Terraform will perform the actions described above.
#   Only 'yes' will be accepted to approve.
#
# Enter a value: yes

# aws_instance.web: Creating...
# aws_instance.web: Still creating... [10s elapsed]
# aws_instance.web: Creation complete after 35s [id=i-0123456789abcdef]
#
# Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```

**Options:**
```bash
terraform apply -auto-approve     # Skip confirmation (dangerous!)
terraform apply plan.tfplan       # Apply saved plan
terraform apply -target=resource  # Apply only specific resource
terraform apply -var="env=prod"   # Override variables
terraform apply -parallelism=20   # Concurrent operations (default 10)
```

### Command 6: terraform destroy

**Purpose:** Destroy all managed infrastructure

**What it does:**
- Deletes ALL resources defined in configuration
- Updates state to empty
- Irreversible (unless backed up)

**Example:**
```bash
terraform destroy

# Shows destruction plan...
# Do you really want to destroy all resources?
#   Terraform will destroy all your managed infrastructure.
#   There is no undo. Only 'yes' will be accepted to confirm.
#
# Enter a value: yes

# aws_instance.web: Destroying... [id=i-0123456789abcdef]
# aws_instance.web: Still destroying... [10s elapsed]
# aws_instance.web: Destruction complete after 35s
#
# Destroy complete! Resources: 1 destroyed.
```

**Options:**
```bash
terraform destroy -auto-approve   # Skip confirmation
terraform destroy -target=resource # Destroy specific resource
```

### Command 7: terraform show

**Purpose:** Inspect current state or saved plan

**Examples:**
```bash
# Show current state
terraform show

# Output:
# # aws_instance.web:
# resource "aws_instance" "web" {
#     ami           = "ami-12345"
#     id            = "i-0123456789abcdef"
#     instance_type = "t2.micro"
#     public_ip     = "54.123.45.67"
# }

# Show saved plan
terraform show plan.tfplan

# JSON output (for automation)
terraform show -json
```

### Command 8: terraform output

**Purpose:** Extract output values

**Examples:**
```bash
# Show all outputs
terraform output

# Output:
# instance_id = "i-0123456789abcdef"
# instance_ip = "54.123.45.67"

# Show specific output
terraform output instance_ip
# 54.123.45.67

# Raw output (no quotes, for scripts)
terraform output -raw instance_ip
# 54.123.45.67

# JSON format
terraform output -json
# {
#   "instance_id": { "value": "i-0123456789abcdef" },
#   "instance_ip": { "value": "54.123.45.67" }
# }
```

---

## 4. Step-by-Step Walkthrough

### Complete Workflow Example

**Scenario:** Create a web server with S3 bucket

**Step 1: Initialize directory**
```bash
mkdir terraform-workflow-demo
cd terraform-workflow-demo
```

**Step 2: Write configuration**
```bash
cat > main.tf << 'EOF'
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

variable "aws_region" {
  type    = string
  default = "us-east-1"
}

variable "environment" {
  type    = string
  default = "dev"
}

resource "aws_instance" "web" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = var.environment == "prod" ? "t2.small" : "t2.micro"
  
  tags = {
    Name        = "${var.environment}-web-server"
    Environment = var.environment
  }
}

resource "aws_s3_bucket" "logs" {
  bucket = "my-app-logs-${var.environment}-${random_id.bucket.hex}"
  
  tags = {
    Name        = "App Logs"
    Environment = var.environment
  }
}

resource "random_id" "bucket" {
  byte_length = 4
}

output "instance_id" {
  description = "ID of the EC2 instance"
  value       = aws_instance.web.id
}

output "instance_public_ip" {
  description = "Public IP of the instance"
  value       = aws_instance.web.public_ip
}

output "bucket_name" {
  description = "Name of the S3 bucket"
  value       = aws_s3_bucket.logs.id
}
EOF
```

**Step 3: Initialize**
```bash
terraform init

# Output:
# Initializing the backend...
# Initializing provider plugins...
# - Finding hashicorp/aws versions matching "~> 5.0"...
# - Installing hashicorp/aws v5.31.0...
# - Installing hashicorp/random v3.6.0...
# Terraform has been successfully initialized!
```

**Step 4: Format**
```bash
terraform fmt

# Output:
# main.tf  (if changes were made)
```

**Step 5: Validate**
```bash
terraform validate

# Output:
# Success! The configuration is valid.
```

**Step 6: Plan**
```bash
terraform plan

# Review output carefully:
# Plan: 3 to add, 0 to change, 0 to destroy.

# Optionally save plan:
terraform plan -out=tfplan
```

**Step 7: Apply**
```bash
terraform apply

# Review plan output again
# Type 'yes' to confirm

# Wait for completion...
# Apply complete! Resources: 3 added, 0 changed, 0 destroyed.
#
# Outputs:
# bucket_name = "my-app-logs-dev-a1b2c3d4"
# instance_id = "i-0123456789abcdef"
# instance_public_ip = "54.123.45.67"
```

**Step 8: Verify**
```bash
# Check outputs
terraform output

# Show current state
terraform show

# Verify in AWS console (optional)
aws ec2 describe-instances --instance-ids $(terraform output -raw instance_id)
```

**Step 9: Make changes**
```bash
# Modify configuration
cat >> main.tf << 'EOF'

resource "aws_eip" "web" {
  instance = aws_instance.web.id
  
  tags = {
    Name = "${var.environment}-web-eip"
  }
}

output "elastic_ip" {
  description = "Elastic IP address"
  value       = aws_eip.web.public_ip
}
EOF
```

**Step 10: Plan changes**
```bash
terraform plan

# Output shows:
# Plan: 1 to add, 0 to change, 0 to destroy.
```

**Step 11: Apply changes**
```bash
terraform apply

# Type 'yes'
# Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```

**Step 12: Clean up**
```bash
terraform destroy

# Review destruction plan
# Type 'yes' to confirm
# Destroy complete! Resources: 4 destroyed.
```

---

## 5. Practical Examples

### Example 1: Targeted Operations

**Create only specific resource:**
```bash
# Plan for specific resource
terraform plan -target=aws_instance.web

# Apply only that resource
terraform apply -target=aws_instance.web

# Useful for:
# - Testing individual resources
# - Fixing specific failures
# - Partial deployments
```

**Warning:** Breaks dependency tracking, use carefully!

### Example 2: Saved Plans (Production Best Practice)

```bash
# Step 1: Create and save plan
terraform plan -out=production.tfplan

# Step 2: Review plan file (human review)
# Team reviews the plan output

# Step 3: Apply exact plan (no surprises)
terraform apply production.tfplan
# No confirmation needed, plan is pre-approved
```

### Example 3: Variable Overrides

```bash
# Override single variable
terraform apply -var="environment=production"

# Override multiple variables
terraform apply \
  -var="environment=prod" \
  -var="instance_type=t2.large" \
  -var="region=us-west-2"

# Use variable file
terraform apply -var-file="production.tfvars"
```

### Example 4: Dry Run Destroy

```bash
# Preview what would be destroyed
terraform plan -destroy

# Review output
# Nothing is actually destroyed yet

# If satisfied, then destroy
terraform destroy
```

### Example 5: Refresh State

```bash
# Update state to match reality (manual changes)
terraform refresh

# Now state reflects actual infrastructure
# Useful after manual console changes
```

### Example 6: Workspace Workflow

```bash
# Create development workspace
terraform workspace new dev
terraform apply

# Create production workspace
terraform workspace new prod
terraform apply -var="environment=prod"

# Switch between workspaces
terraform workspace select dev
terraform plan

terraform workspace select prod
terraform plan

# Each workspace has separate state!
```

---

## 6. Deep Dive

### State File Management

**What is terraform.tfstate?**
```
Purpose: Tracks current infrastructure
Format: JSON file
Contains: Resource IDs, attributes, metadata
Critical: Loss = lose track of infrastructure
```

**State file location:**
```bash
# Local backend (default)
./terraform.tfstate

# Remote backend (S3 example)
s3://bucket/path/terraform.tfstate
```

**State commands:**
```bash
# List resources in state
terraform state list

# Show specific resource
terraform state show aws_instance.web

# Remove resource from state (doesn't delete resource)
terraform state rm aws_instance.web

# Move resource (rename)
terraform state mv aws_instance.web aws_instance.web_server

# Pull remote state
terraform state pull > state.json

# Push local state
terraform state push state.json
```

### Plan Files

**Benefits:**
- Exact reproduction of planned changes
- No drift between plan and apply
- Audit trail
- Multi-stage approval workflows

**Structure:**
```bash
# Create plan
terraform plan -out=plan.tfplan

# Inspect plan (human-readable)
terraform show plan.tfplan

# Inspect plan (JSON)
terraform show -json plan.tfplan > plan.json

# Apply plan
terraform apply plan.tfplan
```

### Parallel Operations

**Terraform parallelizes by default:**
```bash
# Default: 10 concurrent operations
terraform apply

# Increase parallelism (faster, more load)
terraform apply -parallelism=20

# Decrease parallelism (slower, safer)
terraform apply -parallelism=5
```

**Resource creation order:**
```
Independent resources → Parallel
Dependent resources  → Sequential

Example:
VPC creation         → First (nothing depends on)
2 Subnets           → Parallel (both depend on VPC)
2 Instances         → Parallel (each depends on subnet)
```

---

## 7. Trade-offs & Pitfalls

### Common Mistakes

**Mistake 1: Skipping plan**
```bash
# Dangerous!
terraform apply -auto-approve

# Always review plan first!
terraform plan
terraform apply
```

**Mistake 2: Not saving plan in production**
```bash
# Bad (can drift between plan and apply)
terraform plan
# ... 10 minutes later ...
terraform apply  # Might apply different changes!

# Good (exact plan is applied)
terraform plan -out=prod.tfplan
# Review, approve
terraform apply prod.tfplan
```

**Mistake 3: Manual changes without refresh**
```bash
# You manually changed something in AWS console
# Terraform doesn't know yet

terraform apply  # Might conflict!

# Should do:
terraform refresh  # Sync state with reality
terraform plan     # See drift
terraform apply    # Fix drift or acknowledge changes
```

**Mistake 4: Destroying without backup**
```bash
# Risky!
terraform destroy

# Safer:
terraform state pull > backup.tfstate  # Backup state
terraform plan -destroy                # Preview
terraform destroy                      # Execute
```

**Mistake 5: Not using version control**
```bash
# Wrong: Keep only on local machine
vim main.tf
terraform apply

# Right: Version control everything
git add main.tf
git commit -m "Add web server"
git push
terraform apply
```

---

## 8. Mental Models & Analogies

### Analogy: Construction Project

**Write (Design Phase)**
- Architect draws blueprints
- Terraform: Write .tf files

**Plan (Bidding Phase)**
- Contractor estimates costs and timeline
- Terraform: `terraform plan` shows what will happen

**Apply (Construction Phase)**
- Workers build according to plan
- Terraform: `terraform apply` creates infrastructure

**Destroy (Demolition)**
- Tear down building
- Terraform: `terraform destroy` removes everything

---

## 9. Troubleshooting Guide

### Problem: "Error acquiring state lock"

**Cause:** Another terraform process is running

**Solution:**
```bash
# Wait for other process to finish
# Or force unlock (dangerous!)
terraform force-unlock <LOCK_ID>
```

### Problem: "Error: Unsupported argument"

**Cause:** Typo in argument name

**Solution:**
```bash
# Run validate to find exact location
terraform validate

# Fix typo in .tf file
# Re-validate
terraform validate
```

### Problem: "Resource already exists"

**Cause:** Resource created outside Terraform

**Solution:**
```bash
# Import existing resource
terraform import aws_instance.web i-0123456789abcdef

# Now Terraform manages it
```

### Problem: "Plan doesn't match apply"

**Cause:** Infrastructure changed between plan and apply

**Solution:**
```bash
# Use saved plans
terraform plan -out=plan.tfplan
terraform apply plan.tfplan  # Exact same changes
```

---

## 10. Frequently Asked Questions

**Q1: Do I need to run terraform init every time?**
**A:** No, only after adding providers or changing backend.

**Q2: Can I skip terraform plan?**
**A:** Technically yes, but never do it! Always review changes.

**Q3: What happens if terraform apply fails halfway?**
**A:** State is updated for completed resources. Fix error and rerun.

**Q4: Can I undo terraform apply?**
**A:** Not directly. You must modify config to reverse changes, then apply again.

**Q5: Is terraform destroy permanent?**
**A:** Yes! Always backup state before destroying.

**Q6: Can multiple people run terraform apply?**
**A:** Not safely on same directory. Use remote state with locking.

**Q7: How do I see what's currently deployed?**
**A:** `terraform show` or `terraform state list`

**Q8: Can I apply only part of the configuration?**
**A:** Yes, with `-target`, but breaks dependency tracking.

**Q9: What's the difference between plan and apply?**
**A:** Plan previews, apply executes. Apply runs plan first.

**Q10: Should I commit terraform.tfstate?**
**A:** NO! Use remote backend instead. State may contain secrets.

---

## 11. Key Takeaways

✅ **Write-Plan-Apply** – Core three-step workflow
✅ **Always run plan** – Preview changes before applying
✅ **terraform init** – First command in new directory
✅ **terraform fmt** – Format code consistently
✅ **terraform validate** – Catch syntax errors
✅ **Save plans in production** – Use `-out` flag
✅ **Never skip plan review** – Prevent disasters
✅ **State is critical** – Backup and protect
✅ **Use version control** – Git for .tf files, remote backend for state

---

## 12. Practice Exercises

### Exercise 1: Complete Workflow
```
1. Create new directory
2. Write configuration for VPC + subnet
3. Run complete workflow (init, fmt, validate, plan, apply)
4. Verify resources in AWS console
5. Destroy everything
```

### Exercise 2: Saved Plans
```
1. Create configuration
2. Generate saved plan with -out
3. Inspect saved plan
4. Apply saved plan
5. Verify no prompts for approval
```

### Exercise 3: Targeted Apply
```
1. Create configuration with 3 resources
2. Apply only one resource with -target
3. Apply remaining resources
4. Observe dependency handling
```

### Exercise 4: State Management
```
1. Create infrastructure
2. List state resources
3. Show specific resource details
4. Pull state to JSON file
5. Inspect JSON structure
```

### Exercise 5: Drift Detection
```
1. Create EC2 instance with Terraform
2. Manually change tags in AWS console
3. Run terraform plan
4. Observe drift detection
5. Decide: revert or update config
```

---

## 13. Further Reading

- Terraform CLI Documentation
- State Management Best Practices
- Terraform Cloud Workflows
- GitOps with Terraform

---

## Conclusion

The Terraform workflow is your safety net. **Write-Plan-Apply** isn't just a suggestion—it's a disaster prevention system. Always preview changes, never skip plan, and treat infrastructure changes with the same rigor as code deployments.

**Remember:**
- Plan shows intent
- Apply executes intent
- State tracks reality
- Workflow prevents chaos

**Next Chapter:** Deep dive into Terraform providers and AWS provider specifics.

---

*Workflow Mastered!*
*Infrastructure changes are now safe and predictable*
