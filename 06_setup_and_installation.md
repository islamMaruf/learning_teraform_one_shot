# Chapter 6: Setup & Installation – Getting Terraform Running

## Prerequisites
- Basic command line knowledge
- AWS account (free tier is sufficient)
- Computer with internet connection (Linux, Mac, or Windows)
- Understanding of Chapters 1-5
- Estimated time: 45-60 minutes (including AWS EC2 setup)

## 1. Introduction

### Why This Topic Matters

You can't use Terraform until it's installed. This seems obvious, but **how** you install and configure Terraform impacts your entire workflow. A proper setup prevents 90% of beginner issues.

**The Reality:**
- Wrong installation = mysterious errors later
- Skipping configuration = wasted time debugging
- No understanding of dependencies = stuck on first project

**The Goal:**
By the end of this chapter, you'll have Terraform running on both:
1. Your local machine (development)
2. An AWS EC2 instance (simulating a build server)

### What You'll Learn

- Installing Terraform on Linux, Mac, and Windows
- Verifying your installation
- Setting up AWS CLI and credentials
- Configuring Terraform for AWS
- Creating an EC2 instance and installing Terraform on it
- Understanding the complete Terraform environment
- Troubleshooting common installation issues

### The Problem Being Solved

**Before Terraform Installation:**
```
You: I need 5 EC2 instances
Process: Click, click, click... (20 minutes)
Result: Manual work, error-prone
```

**After Terraform Installation:**
```
You: terraform apply
Process: Automated (30 seconds)
Result: 5 EC2 instances, identical, documented in code
```

---

## 2. Concept Overview

### What is Terraform Installation?

Installing Terraform means placing the Terraform executable binary on your system so you can run `terraform` commands from your terminal.

**Simple Definition:**
Terraform is a single binary file (like a .exe on Windows or an executable on Linux). Installing it means downloading this file and putting it in a location where your system can find it.

### The Components You Need

```
Complete Terraform Development Environment:

1. Terraform CLI (The Tool Itself)
   └─ The terraform binary executable

2. Cloud Provider CLI (AWS CLI)
   └─ Tool to interact with AWS from command line

3. Cloud Provider Credentials
   └─ Access keys so Terraform can authenticate

4. Text Editor or IDE
   └─ VS Code, Vim, Sublime (to write .tf files)

5. (Optional) Git
   └─ Version control for your infrastructure code
```

### Installation Methods Comparison

| Method | Pros | Cons | Best For |
|--------|------|------|----------|
| **Package Manager** | Easy, auto-updates | May not have latest version | Most users |
| **Binary Download** | Latest version, control | Manual updates | Specific versions |
| **Compile from Source** | Full customization | Complex, time-consuming | Advanced users |
| **tfenv** | Multiple versions | Extra tool to manage | Teams with version needs |

### Key Terminology

**Binary:**
- Pre-compiled executable file
- No installation required, just run it
- Example: `terraform` is a single binary

**PATH:**
- Environment variable listing directories
- System checks PATH to find commands
- Adding Terraform to PATH lets you run it from anywhere

**Provider:**
- Plugin that Terraform uses to interact with services
- AWS Provider, Azure Provider, etc.
- Auto-downloaded when you run `terraform init`

**Terraform Init:**
- First command you run in a new project
- Downloads required providers
- Sets up backend configuration

---

## 3. Core Theory

### How Terraform Works on Your System

```
┌─────────────────────────────────────────────┐
│ Your Computer                               │
│                                             │
│  ┌──────────────────────────────────────┐  │
│  │ Terminal/Command Prompt              │  │
│  │  $ terraform plan                    │  │
│  └──────────────────────────────────────┘  │
│              ↓                              │
│  ┌──────────────────────────────────────┐  │
│  │ Terraform Binary (/usr/bin/terraform)│  │
│  │ - Reads .tf configuration files      │  │
│  │ - Talks to AWS APIs                  │  │
│  │ - Manages state                      │  │
│  └──────────────────────────────────────┘  │
│              ↓                              │
│  ┌──────────────────────────────────────┐  │
│  │ Provider Plugin (AWS)                │  │
│  │ ~/.terraform.d/plugins/              │  │
│  │ - Downloaded by 'terraform init'     │  │
│  │ - Translates Terraform → AWS API     │  │
│  └──────────────────────────────────────┘  │
└─────────────────────────────────────────────┘
              ↓ HTTPS API Calls
┌─────────────────────────────────────────────┐
│ AWS Cloud                                   │
│  - Creates EC2 instances                    │
│  - Creates VPCs                             │
│  - etc.                                     │
└─────────────────────────────────────────────┘
```

### Version Compatibility

**Terraform Versions:**
- Terraform uses semantic versioning (1.5.7)
- Major version changes (1.x → 2.x) may break compatibility
- Minor versions (1.5 → 1.6) add features
- Patch versions (1.5.7 → 1.5.8) are bug fixes

**Provider Versions:**
- AWS provider versioned separately
- Must specify compatible versions
- Lock versions in production

**Example version constraints:**
```hcl
terraform {
  required_version = ">= 1.5.0"  # Terraform itself

  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"  # AWS provider
    }
  }
}
```

---

## 4. Step-by-Step Walkthrough

### Part 1: Installing Terraform on Your Local Machine

#### Option A: Linux (Ubuntu/Debian)

**Step 1: Update package index**
```bash
sudo apt-get update
```

**Step 2: Install dependencies**
```bash
sudo apt-get install -y gnupg software-properties-common
```

**Step 3: Add HashiCorp GPG key**
```bash
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
```

**Step 4: Add HashiCorp repository**
```bash
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```

**Step 5: Install Terraform**
```bash
sudo apt-get update
sudo apt-get install terraform
```

**Step 6: Verify installation**
```bash
terraform version
# Output: Terraform v1.6.0 (or similar)
```

**Alternative: Manual Binary Installation (Faster)**
```bash
# 1. Download latest version
wget https://releases.hashicorp.com/terraform/1.6.6/terraform_1.6.6_linux_amd64.zip

# 2. Unzip
unzip terraform_1.6.6_linux_amd64.zip

# 3. Move to PATH
sudo mv terraform /usr/local/bin/

# 4. Verify
terraform version
```

#### Option B: macOS

**Method 1: Using Homebrew (Recommended)**
```bash
# Install Homebrew if not already installed
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Terraform
brew tap hashicorp/tap
brew install hashicorp/tap/terraform

# Verify
terraform version
```

**Method 2: Manual Binary**
```bash
# Download
curl -LO https://releases.hashicorp.com/terraform/1.6.6/terraform_1.6.6_darwin_amd64.zip

# Unzip
unzip terraform_1.6.6_darwin_amd64.zip

# Move to PATH
sudo mv terraform /usr/local/bin/

# Verify
terraform version
```

#### Option C: Windows

**Method 1: Using Chocolatey**
```powershell
# Install Chocolatey first (if not installed)
# Run PowerShell as Administrator
Set-ExecutionPolicy Bypass -Scope Process -Force; 
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; 
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

# Install Terraform
choco install terraform

# Verify
terraform version
```

**Method 2: Manual Installation**
```powershell
# 1. Download from: https://releases.hashicorp.com/terraform/
#    Choose: terraform_1.6.6_windows_amd64.zip

# 2. Unzip to C:\terraform

# 3. Add to PATH:
#    - Right-click "This PC" → Properties
#    - Advanced system settings
#    - Environment Variables
#    - Edit "Path"
#    - Add: C:\terraform
#    - Click OK

# 4. Open new PowerShell/CMD and verify:
terraform version
```

### Part 2: Installing AWS CLI

**Why?** Terraform uses AWS credentials configured by AWS CLI.

#### Linux/macOS:
```bash
# Download installer
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

# Unzip
unzip awscliv2.zip

# Install
sudo ./aws/install

# Verify
aws --version
# Output: aws-cli/2.x.x ...
```

#### Windows:
```powershell
# Download and run MSI installer from:
# https://awscli.amazonaws.com/AWSCLIV2.msi

# Or using Chocolatey:
choco install awscli

# Verify:
aws --version
```

### Part 3: Configuring AWS Credentials

**Step 1: Create AWS Access Keys**
```
1. Log into AWS Console
2. Go to IAM → Users → Your User
3. Security Credentials tab
4. Create Access Key
5. Download/copy:
   - Access Key ID
   - Secret Access Key
```

**Step 2: Configure AWS CLI**
```bash
aws configure

# Prompts:
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-east-1
Default output format [None]: json
```

**Step 3: Verify Connection**
```bash
aws sts get-caller-identity

# Output should show your AWS account info:
# {
#     "UserId": "AIDAI...",
#     "Account": "123456789012",
#     "Arn": "arn:aws:iam::123456789012:user/yourname"
# }
```

**Where Credentials Are Stored:**
```
Linux/Mac: ~/.aws/credentials
Windows: C:\Users\YourName\.aws\credentials

File contents:
[default]
aws_access_key_id = AKIAIOSFODNN7EXAMPLE
aws_secret_access_key = wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
```

### Part 4: Your First Terraform Configuration

**Step 1: Create project directory**
```bash
mkdir terraform-test
cd terraform-test
```

**Step 2: Create main.tf**
```bash
cat > main.tf << 'EOF'
terraform {
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

resource "aws_instance" "test" {
  ami           = "ami-0c55b159cbfafe1f0"  # Amazon Linux 2
  instance_type = "t2.micro"
  
  tags = {
    Name = "TerraformTest"
  }
}
EOF
```

**Step 3: Initialize Terraform**
```bash
terraform init

# Output:
# Initializing provider plugins...
# - Finding hashicorp/aws versions matching "~> 5.0"...
# - Installing hashicorp/aws v5.31.0...
# Terraform has been successfully initialized!
```

**Step 4: Validate configuration**
```bash
terraform validate

# Output: Success! The configuration is valid.
```

**Step 5: Plan (don't apply yet)**
```bash
terraform plan

# Output shows what will be created:
# + resource "aws_instance" "test" {
#     + ami           = "ami-0c55b159cbfafe1f0"
#     + instance_type = "t2.micro"
#     ...
# Plan: 1 to add, 0 to change, 0 to destroy.
```

**Step 6: Apply (actually create)**
```bash
terraform apply

# Type 'yes' when prompted
# Wait 30-60 seconds...
# Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```

**Step 7: Verify in AWS Console**
```
Go to EC2 Dashboard → Instances
You should see "TerraformTest" instance running!
```

**Step 8: Clean up**
```bash
terraform destroy

# Type 'yes' to confirm
# Wait 30 seconds...
# Destroy complete! Resources: 1 destroyed.
```

🎉 **Congratulations!** You've successfully installed Terraform and created your first infrastructure!

---

### Part 5: Installing Terraform on AWS EC2 Instance

**Why?** In real-world scenarios, Terraform often runs on build servers, not just local machines.

**Step 1: Create EC2 instance manually (or use Terraform!)**

**Option A: Using AWS Console**
```
1. Go to EC2 Dashboard
2. Launch Instance
3. Choose: Ubuntu Server 22.04 LTS
4. Instance type: t2.micro (free tier)
5. Key pair: Create new or use existing
6. Security group: Allow SSH (port 22)
7. Launch instance
```

**Option B: Using Terraform (meta!)**
```hcl
# ec2-terraform-server.tf
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "terraform_server" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  key_name      = "your-key-pair"  # Change this
  
  user_data = <<-EOF
              #!/bin/bash
              # Install Terraform on boot
              sudo apt-get update
              sudo apt-get install -y wget unzip
              wget https://releases.hashicorp.com/terraform/1.6.6/terraform_1.6.6_linux_amd64.zip
              unzip terraform_1.6.6_linux_amd64.zip
              sudo mv terraform /usr/local/bin/
              terraform version
              EOF
  
  tags = {
    Name = "TerraformServer"
  }
}

output "instance_ip" {
  value = aws_instance.terraform_server.public_ip
}
```

```bash
terraform init
terraform apply
# Note the output IP address
```

**Step 2: SSH into the instance**
```bash
# Get public IP from AWS console or Terraform output
ssh -i your-key.pem ubuntu@<PUBLIC_IP>
```

**Step 3: Install Terraform on EC2**
```bash
# Update package manager
sudo apt-get update

# Install dependencies
sudo apt-get install -y wget unzip

# Download Terraform
wget https://releases.hashicorp.com/terraform/1.6.6/terraform_1.6.6_linux_amd64.zip

# Unzip
unzip terraform_1.6.6_linux_amd64.zip

# Move to PATH
sudo mv terraform /usr/local/bin/

# Verify
terraform version
# Output: Terraform v1.6.6
```

**Step 4: Install AWS CLI on EC2**
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

# Verify
aws --version
```

**Step 5: Configure AWS credentials on EC2**

**Option A: Using IAM Role (Recommended for Production)**
```
1. In AWS Console: IAM → Roles → Create Role
2. Select: AWS service → EC2
3. Attach policy: AdministratorAccess (for testing; restrict in production)
4. Name: EC2-Terraform-Role
5. Attach role to EC2 instance:
   - Select instance
   - Actions → Security → Modify IAM role
   - Select EC2-Terraform-Role
   
No credentials file needed! EC2 automatically gets permissions.
```

**Option B: Using Access Keys (For Testing Only)**
```bash
aws configure
# Enter your access keys (same as local machine setup)
```

**Step 6: Test Terraform on EC2**
```bash
# Create test directory
mkdir terraform-on-ec2
cd terraform-on-ec2

# Create simple config
cat > main.tf << 'EOF'
provider "aws" {
  region = "us-east-1"
}

resource "aws_s3_bucket" "test" {
  bucket = "terraform-test-bucket-$(date +%s)"
  
  tags = {
    Name = "TestBucket"
    Environment = "Dev"
  }
}
EOF

# Initialize
terraform init

# Plan
terraform plan

# Apply
terraform apply -auto-approve

# Verify bucket created
aws s3 ls | grep terraform-test

# Clean up
terraform destroy -auto-approve
```

**Success!** Terraform is now running on EC2!

---

## 5. Practical Examples

### Example 1: Version Manager (tfenv)

**Why?** Different projects need different Terraform versions.

**Install tfenv:**
```bash
# Clone tfenv
git clone https://github.com/tfutils/tfenv.git ~/.tfenv

# Add to PATH
echo 'export PATH="$HOME/.tfenv/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# Install specific version
tfenv install 1.5.7
tfenv install 1.6.6

# Use specific version
tfenv use 1.5.7
terraform version  # Shows 1.5.7

# Switch versions
tfenv use 1.6.6
terraform version  # Shows 1.6.6

# Auto-detect from .terraform-version file
echo "1.5.7" > .terraform-version
tfenv install min-required
tfenv use min-required
```

### Example 2: IDE Setup (VS Code)

**Install VS Code Extensions:**
```
1. Open VS Code
2. Extensions (Ctrl+Shift+X)
3. Search and install:
   - HashiCorp Terraform
   - Terraform Autocomplete
   - Terraform Doc Snippets

Features you get:
- Syntax highlighting
- Auto-completion
- Error checking
- Format on save
```

**Configure auto-format:**
```json
// .vscode/settings.json
{
  "[terraform]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "hashicorp.terraform"
  }
}
```

### Example 3: Shell Completion

**Enable Terraform auto-completion:**

**Bash:**
```bash
terraform -install-autocomplete
source ~/.bashrc
```

**Zsh:**
```bash
terraform -install-autocomplete
source ~/.zshrc
```

**Result:**
```bash
terraform pl<TAB>  # Completes to: terraform plan
terraform a<TAB>   # Shows: apply, apply-complete
```

---

## 6. Deep Dive

### Terraform Directory Structure

**After `terraform init`:**
```
your-project/
├── .terraform/               # Hidden directory
│   ├── providers/           # Downloaded provider binaries
│   │   └── registry.terraform.io/
│   │       └── hashicorp/
│   │           └── aws/
│   │               └── 5.31.0/
│   │                   └── linux_amd64/
│   │                       └── terraform-provider-aws_v5.31.0_x5
│   └── terraform.tfstate    # (if using local backend)
├── .terraform.lock.hcl      # Provider version lock file
├── main.tf                  # Your configuration
├── terraform.tfstate        # Current state
└── terraform.tfstate.backup # Previous state backup
```

### Provider Plugin Cache

**Problem:** Downloading providers repeatedly wastes bandwidth and time.

**Solution:** Configure plugin cache
```bash
# Create cache directory
mkdir -p ~/.terraform.d/plugin-cache

# Configure Terraform
cat > ~/.terraformrc << 'EOF'
plugin_cache_dir = "$HOME/.terraform.d/plugin-cache"
EOF

# Now providers are cached globally
```

**Result:**
- First `terraform init`: Downloads provider
- Subsequent inits: Uses cached provider (faster!)

### Security Best Practices

**1. Never commit credentials:**
```bash
# .gitignore
.terraform/
*.tfstate
*.tfstate.backup
*.tfvars  # May contain secrets
```

**2. Use environment variables instead of hardcoding:**
```bash
# Instead of in code:
# access_key = "AKIAIOSFODNN7..."

# Use:
export AWS_ACCESS_KEY_ID="AKIAIOSFODNN7..."
export AWS_SECRET_ACCESS_KEY="wJalr..."
```

**3. Restrict IAM permissions (principle of least privilege):**
```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": [
      "ec2:*",
      "s3:*"
    ],
    "Resource": "*"
  }]
}
```

---

## 7. Trade-offs & Pitfalls

### Common Installation Mistakes

**Mistake 1: Old Terraform version**
```bash
# Check version
terraform version

# If < 1.0, you're using outdated version
# Uninstall and reinstall using methods above
```

**Mistake 2: Wrong PATH**
```bash
# Terraform installed but command not found?
# Check PATH:
echo $PATH

# Find where Terraform is:
which terraform  # Should show: /usr/local/bin/terraform

# If not in PATH, add it:
export PATH=$PATH:/usr/local/bin
```

**Mistake 3: No AWS credentials**
```bash
# Test credentials:
aws sts get-caller-identity

# If error, reconfigure:
aws configure
```

**Mistake 4: Wrong AMI ID**
```
Error: creating EC2 Instance: InvalidAMIID.NotFound
Cause: AMI IDs are region-specific
Solution: Use correct AMI for your region
```

---

## 8. Mental Models & Analogies

### Analogy: Terraform is Like a Chef's Knife

**Installation = Getting the Knife:**
- You need the right knife (Terraform binary)
- It must be sharp (latest version)
- You need to know where it is (in PATH)

**Configuration = Ingredients:**
- AWS credentials = Access to the kitchen
- main.tf files = Recipe

**terraform init = Mise en place:**
- Preparing your workspace
- Getting all tools ready

**terraform apply = Cooking:**
- Following the recipe
- Creating the dish (infrastructure)

---

## 9. Troubleshooting Guide

### Problem: "terraform: command not found"

**Diagnosis:**
```bash
# Check if installed:
ls -l /usr/local/bin/terraform

# Check PATH:
echo $PATH | grep /usr/local/bin
```

**Solution:**
```bash
# Add to PATH:
export PATH=$PATH:/usr/local/bin

# Make permanent (add to ~/.bashrc or ~/.zshrc):
echo 'export PATH=$PATH:/usr/local/bin' >> ~/.bashrc
source ~/.bashrc
```

### Problem: "Error configuring the backend 's3'"

**Diagnosis:**
```bash
# Check AWS credentials:
aws sts get-caller-identity
```

**Solution:**
```bash
# Reconfigure AWS:
aws configure

# Or use environment variables:
export AWS_ACCESS_KEY_ID="..."
export AWS_SECRET_ACCESS_KEY="..."
```

### Problem: "Plugin reinitialization required"

**Diagnosis:**
```
Error: Provider configuration has changed
```

**Solution:**
```bash
terraform init -upgrade
```

---

## 10. Frequently Asked Questions

**Q1: Do I need Terraform installed on every machine?**
**A:** Yes, wherever you want to run Terraform commands. However, you can use remote execution with Terraform Cloud.

**Q2: Can I install multiple Terraform versions?**
**A:** Yes, use `tfenv` (version manager) to switch between versions easily.

**Q3: Is Terraform installation the same for Windows/Mac/Linux?**
**A:** Conceptually yes (download binary, add to PATH), but exact steps differ.

**Q4: Do I need to install providers manually?**
**A:** No, `terraform init` automatically downloads required providers.

**Q5: Where should I run Terraform from?**
**A:** Locally for development. CI/CD server (Jenkins, GitHub Actions) for production.

**Q6: How do I update Terraform?**
**A:** Download new version and replace the old binary, or use package manager update.

**Q7: Can I run Terraform without AWS CLI?**
**A:** Yes, but you'll need to configure AWS credentials differently (environment variables or in provider block).

**Q8: Is Terraform installation reversible?**
**A:** Yes, just delete the binary and remove from PATH. No system changes are made.

**Q9: Do I need administrator/root access to install Terraform?**
**A:** Not required if you install in user directory, but helpful for system-wide installation.

**Q10: How much disk space does Terraform need?**
**A:** ~50-100MB for binary, plus space for providers (varies, typically 100-500MB).

---

## 11. Key Takeaways

✅ **Terraform is a single binary** – easy to install
✅ **Requires AWS CLI and credentials** for AWS provider
✅ **terraform init** downloads providers automatically
✅ **Version management important** for team collaboration
✅ **Can run locally or on servers** (EC2, Jenkins, etc.)
✅ **Security matters** – never commit credentials
✅ **Test installation with simple example** before complex projects
✅ **PATH configuration is critical** – command must be findable

---

## 12. Practice Exercises

### Exercise 1: Basic Installation Verification
```bash
# Task: Verify your installation
terraform version
aws --version
aws sts get-caller-identity

# Expected: All commands work without errors
```

### Exercise 2: Create and Destroy Infrastructure
```bash
# Task: Create an S3 bucket with Terraform, then destroy it
# 1. Write main.tf with S3 bucket resource
# 2. terraform init
# 3. terraform apply
# 4. Verify in AWS console
# 5. terraform destroy
```

**Solution:**
```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_s3_bucket" "test" {
  bucket = "my-terraform-test-bucket-12345"
  tags = {
    Name = "TestBucket"
  }
}
```

### Exercise 3: EC2 Server Setup
```bash
# Task: Set up Terraform on a new EC2 instance
# 1. Launch t2.micro Ubuntu instance
# 2. SSH into it
# 3. Install Terraform
# 4. Install AWS CLI
# 5. Configure credentials
# 6. Run a test terraform apply

# Time limit: 30 minutes
```

### Exercise 4: Version Management
```bash
# Task: Install and switch between Terraform versions
# 1. Install tfenv
# 2. Install Terraform 1.5.7 and 1.6.6
# 3. Switch to 1.5.7
# 4. Verify version
# 5. Switch to 1.6.6
# 6. Verify version
```

### Exercise 5: Multi-Region Test
```bash
# Task: Create resources in two AWS regions
# 1. Create main.tf with two providers (us-east-1 and us-west-2)
# 2. Create S3 bucket in each region
# 3. Apply
# 4. Verify in AWS console
# 5. Destroy
```

**Solution:**
```hcl
provider "aws" {
  alias  = "east"
  region = "us-east-1"
}

provider "aws" {
  alias  = "west"
  region = "us-west-2"
}

resource "aws_s3_bucket" "east" {
  provider = aws.east
  bucket   = "east-bucket-12345"
}

resource "aws_s3_bucket" "west" {
  provider = aws.west
  bucket   = "west-bucket-12345"
}
```

---

## 13. Further Reading

- **Official Installation Guide:** https://developer.hashicorp.com/terraform/downloads
- **AWS CLI Installation:** https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
- **tfenv GitHub:** https://github.com/tfutils/tfenv
- **Terraform Registry:** https://registry.terraform.io/
- **VS Code Terraform Extension:** HashiCorp Terraform extension documentation

---

## Conclusion

Installation is the foundation of your Terraform journey. A proper setup prevents 90% of beginner frustrations. You now have:

✅ Terraform installed locally
✅ AWS CLI configured
✅ First infrastructure created and destroyed
✅ Understanding of Terraform on servers (EC2)
✅ Knowledge of troubleshooting installation issues

**Next Steps:**
- Chapter 8: Learn HCL syntax in depth
- Chapter 9: Understand different block types
- Start a small personal project to practice

**Pro Tip:** Keep your Terraform version updated, but **lock versions in production code** to prevent surprises!

---

*Installation Complete ✓*
*Time to build real infrastructure!*
