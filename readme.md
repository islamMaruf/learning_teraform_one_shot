# 🚀 Complete Terraform Tutorial - From Zero to Hero

<div align="center">

![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)
![Sections](https://img.shields.io/badge/Sections-55-blue?style=for-the-badge)

**A comprehensive, beginner-friendly guide to mastering Infrastructure as Code**

[Getting Started](#-quick-start) • [Course Structure](#-course-structure) • [Prerequisites](#-prerequisites) • [Resources](#-additional-resources)

</div>

---

## 📖 About This Tutorial

This is a **complete, hands-on Terraform course** covering everything from basic concepts to advanced production-ready patterns. With **55 detailed sections** organized into **11 progressive parts**, you'll learn Infrastructure as Code through practical examples and real-world projects.

### 🎯 What You'll Learn

- ✅ Infrastructure as Code fundamentals
- ✅ Terraform syntax and core concepts  
- ✅ AWS resource management (EC2, VPC, S3, RDS, EKS, ALB, etc.)
- ✅ State management and remote backends
- ✅ Modules, workspaces, and reusability
- ✅ 5 complete real-world projects
- ✅ Security and best practices
- ✅ CI/CD integration and operations
- ✅ Interview preparation and career guidance
- ✅ Terraform certification prep

### 🎓 Who This Is For

- **Beginners** with no prior Terraform experience
- **DevOps Engineers** looking to strengthen IaC skills
- **Cloud Engineers** transitioning to infrastructure automation
- **Developers** wanting to understand infrastructure
- **Anyone** preparing for Terraform Associate certification

---

## 🚦 Quick Start

### Prerequisites
- Basic command line knowledge
- AWS account (free tier works)
- Text editor (VS Code recommended)
- No prior Terraform experience needed!

### Installation
```bash
# Install Terraform (Linux/Mac)
wget https://releases.hashicorp.com/terraform/1.6.0/terraform_1.6.0_linux_amd64.zip
unzip terraform_1.6.0_linux_amd64.zip
sudo mv terraform /usr/local/bin/

# Verify installation
terraform version

# Install AWS CLI
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

# Configure AWS
aws configure
```

### Your First Terraform Project
```bash
# Start with Part 1
cd chapters/part-01-getting-started

# Follow the README for each section
```

---

## 📚 Course Structure

This tutorial is organized into **11 parts** with dedicated chapter READMEs for easy navigation.

### 🌱 Part 1: Getting Started
**[📂 Go to Part 1](./chapters/part-01-getting-started/README.md)**

Master the fundamentals of Infrastructure as Code and Terraform basics.

- Section 1: Introduction to Infrastructure as Code
- Section 2: What is Terraform?
- Section 3: Setting Up Your Environment
- Section 4: Your First Terraform Code
- Section 5: Understanding the Terraform Workflow

**Time:** ~4 hours • **Difficulty:** Beginner

---

### 🔧 Part 2: Core Concepts  
**[📂 Go to Part 2](./chapters/part-02-core-concepts/README.md)**

Deep dive into Terraform syntax, providers, variables, and functions.

- Section 6: The HCL Language Fundamentals
- Section 7: Working with Providers
- Section 8: Variables Deep Dive
- Section 9: Outputs and Data Sources
- Section 10: String Interpolation and Functions

**Time:** ~5 hours • **Difficulty:** Beginner

---

### ☁️ Part 3: AWS Basics
**[📂 Go to Part 3](./chapters/part-03-aws-basics/README.md)**

Learn AWS fundamentals and create your first cloud resources.

- Section 11: AWS Setup and Configuration
- Section 12: Creating Your First EC2 Instance
- Section 13: Networking Basics - VPC and Security Groups
- Section 14: Storage with S3 Buckets
- Section 15: Connecting Everything Together

**Time:** ~6 hours • **Difficulty:** Beginner-Intermediate

---

### 💾 Part 4: State Management
**[📂 Go to Part 4](./chapters/part-04-state-management/README.md)**

Master Terraform state files, remote backends, and state locking.

- Section 16: Understanding Terraform State
- Section 17: State Commands and Operations
- Section 18: Remote Backend with S3
- Section 19: State Locking with DynamoDB
- Section 20: Migrating Local State to Remote

**Time:** ~5 hours • **Difficulty:** Intermediate

---

### ⚙️ Part 5: Advanced Resource Management
**[📂 Go to Part 5](./chapters/part-05-advanced-resources/README.md)**

Learn advanced Terraform features like count, for_each, and lifecycle rules.

- Section 21: Meta-Arguments - Count
- Section 22: Meta-Arguments - For_Each
- Section 23: Conditional Expressions
- Section 24: Dependencies with Depends_On
- Section 25: Lifecycle Rules

**Time:** ~5 hours • **Difficulty:** Intermediate

---

### 🌍 Part 6: Multi-Environment Management
**[📂 Go to Part 6](./chapters/part-06-multi-environment/README.md)**

Manage multiple environments (dev, staging, prod) effectively.

- Section 26: Introduction to Workspaces
- Section 27: Creating and Switching Workspaces
- Section 28: Environment-Specific Configurations
- Section 29: Workspace Best Practices
- Section 30: Alternative - Directory-Based Environments

**Time:** ~4 hours • **Difficulty:** Intermediate

---

### 📦 Part 7: Modules
**[📂 Go to Part 7](./chapters/part-07-modules/README.md)**

Build reusable, maintainable infrastructure with Terraform modules.

- Section 31: What Are Modules?
- Section 32: Using Pre-Built Modules
- Section 33: Creating Your First Custom Module
- Section 34: Module Inputs and Outputs
- Section 35: Module Versioning and Registry

**Time:** ~6 hours • **Difficulty:** Intermediate-Advanced

---

### 🏗️ Part 8: Real-World Projects
**[📂 Go to Part 8](./chapters/part-08-real-world-projects/README.md)**

Build 5 complete production-ready projects from scratch.

- Section 36: Project 1 - Static Website (S3 + CloudFront)
- Section 37: Project 2 - Web App with ALB and ASG
- Section 38: Project 3 - Three-Tier Application
- Section 39: Project 4 - Multi-Region Infrastructure
- Section 40: Project 5 - Complete EKS Cluster

**Time:** ~12 hours • **Difficulty:** Advanced

---

### ✨ Part 9: Best Practices
**[📂 Go to Part 9](./chapters/part-09-best-practices/README.md)**

Learn professional standards for production Terraform code.

- Section 41: Code Organization and Structure
- Section 42: Naming Conventions
- Section 43: Security Best Practices
- Section 44: Version Control Strategies
- Section 45: Documentation Standards

**Time:** ~5 hours • **Difficulty:** Intermediate

---

### 🔧 Part 10: Operations
**[📂 Go to Part 10](./chapters/part-10-operations/README.md)**

Master Terraform operations, debugging, and CI/CD integration.

- Section 46: Complete Terraform Commands Reference
- Section 47: Debugging and Troubleshooting
- Section 48: Performance Optimization
- Section 49: Disaster Recovery
- Section 50: CI/CD Integration

**Time:** ~6 hours • **Difficulty:** Advanced

---

### 🎯 Part 11: Career Development
**[📂 Go to Part 11](./chapters/part-11-career-development/README.md)**

Prepare for interviews, certifications, and advance your career.

- Section 51: Interview Questions and Answers
- Section 52: Building Your Portfolio
- Section 53: Terraform Certifications
- Section 54: Advanced Topics and Resources
- Section 55: Learning Roadmap and Next Steps

**Time:** ~8 hours • **Difficulty:** All Levels

---

## 📊 Learning Path

```mermaid
graph TD
    A[Start Here] --> B[Part 1: Getting Started]
    B --> C[Part 2: Core Concepts]
    C --> D[Part 3: AWS Basics]
    D --> E[Part 4: State Management]
    E --> F[Part 5: Advanced Resources]
    F --> G{Choose Path}
    G --> H[Part 6: Multi-Environment]
    G --> I[Part 7: Modules]
    H --> J[Part 8: Real-World Projects]
    I --> J
    J --> K[Part 9: Best Practices]
    K --> L[Part 10: Operations]
    L --> M[Part 11: Career Development]
    M --> N[Terraform Expert! 🎉]
```

---

## ⏱️ Time Investment

| Level | Parts | Estimated Time | Skills Gained |
|-------|-------|----------------|---------------|
| **Beginner** | Parts 1-3 | 15 hours | Basic Terraform + AWS |
| **Intermediate** | Parts 4-7 | 20 hours | State, Modules, Environments |
| **Advanced** | Parts 8-10 | 23 hours | Production Projects + Ops |
| **Professional** | Part 11 | 8 hours | Career + Certification |
| **Total** | All 11 Parts | **~66 hours** | **Zero to Hero** |

*Recommended: 1-2 hours per day = Complete in 5-8 weeks*

---

## 🗂️ Repository Structure

```
teraform_learning/
├── README.md (this file)
├── chapters/
│   ├── part-01-getting-started/
│   │   ├── README.md (Sections 1-5)
│   │   └── examples/
│   ├── part-02-core-concepts/
│   │   ├── README.md (Sections 6-10)
│   │   └── examples/
│   ├── part-03-aws-basics/
│   │   ├── README.md (Sections 11-15)
│   │   └── examples/
│   ├── part-04-state-management/
│   │   ├── README.md (Sections 16-20)
│   │   └── examples/
│   ├── part-05-advanced-resources/
│   │   ├── README.md (Sections 21-25)
│   │   └── examples/
│   ├── part-06-multi-environment/
│   │   ├── README.md (Sections 26-30)
│   │   └── examples/
│   ├── part-07-modules/
│   │   ├── README.md (Sections 31-35)
│   │   └── examples/
│   ├── part-08-real-world-projects/
│   │   ├── README.md (Sections 36-40)
│   │   ├── project-01-static-website/
│   │   ├── project-02-web-app-alb/
│   │   ├── project-03-three-tier/
│   │   ├── project-04-multi-region/
│   │   └── project-05-eks-cluster/
│   ├── part-09-best-practices/
│   │   ├── README.md (Sections 41-45)
│   │   └── examples/
│   ├── part-10-operations/
│   │   ├── README.md (Sections 46-50)
│   │   └── examples/
│   └── part-11-career-development/
│       └── README.md (Sections 51-55)
└── resources/
    ├── cheatsheet.md
    ├── glossary.md
    └── faq.md
```

---

## 🎯 Prerequisites

### Required Knowledge
- ✅ Basic command line usage
- ✅ Understanding of cloud concepts (nice to have)
- ✅ Text editor experience

### Tools Needed
- [ ] Terraform 1.6+ 
- [ ] AWS CLI
- [ ] Code editor (VS Code recommended)
- [ ] Git (for version control)
- [ ] AWS account (free tier)

### Recommended But Optional
- Docker knowledge
- Basic networking concepts
- Linux/Unix familiarity

---

## 💡 How to Use This Tutorial

### For Complete Beginners
1. Start with Part 1 and go sequentially
2. Complete all exercises in each section
3. Build the practice projects
4. Don't skip the basics!

### For Experienced Users
1. Review the table of contents
2. Jump to sections you need
3. Focus on Parts 7-11 for advanced topics
4. Build the real-world projects (Part 8)

### For Certification Prep
1. Complete Parts 1-7 thoroughly
2. Focus heavily on Part 4 (State Management)
3. Study Part 11, Section 53 (Certifications)
4. Take practice exams

### Learning Tips
- 💻 **Code along** - Type every example yourself
- 🎯 **Do exercises** - Practice reinforces learning
- 🚀 **Build projects** - Apply what you learn
- 🤝 **Join community** - Learn with others
- 📝 **Take notes** - Create your own reference

---

## 📦 Projects You'll Build

### 1. Static Website Hosting
- S3 bucket configuration
- CloudFront CDN
- Route 53 DNS
- SSL certificates

### 2. Web Application with Load Balancer
- Application Load Balancer
- Auto Scaling Group
- Launch Templates
- Health checks

### 3. Three-Tier Architecture
- Web, Application, Database layers
- VPC with public/private subnets
- RDS database
- Security groups

### 4. Multi-Region Infrastructure
- Cross-region replication
- Route 53 failover
- Disaster recovery setup
- Health monitoring

### 5. Kubernetes Cluster (EKS)
- EKS cluster setup
- Node groups
- IRSA configuration
- Application deployment

---

## 🛠️ Additional Resources

### Official Documentation
- [Terraform Docs](https://www.terraform.io/docs)
- [AWS Provider Docs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
- [Terraform Registry](https://registry.terraform.io/)

### Learning Resources
- [HashiCorp Learn](https://learn.hashicorp.com/terraform)
- [Terraform Best Practices](https://www.terraform-best-practices.com/)
- [AWS Documentation](https://docs.aws.amazon.com/)

### Community
- [HashiCorp Discuss](https://discuss.hashicorp.com/c/terraform-core)
- [r/Terraform](https://www.reddit.com/r/Terraform/)
- [Terraform GitHub](https://github.com/hashicorp/terraform)

### Tools & Extensions
- [VS Code Terraform Extension](https://marketplace.visualstudio.com/items?itemName=HashiCorp.terraform)
- [TFLint](https://github.com/terraform-linters/tflint)
- [Terraform Docs](https://terraform-docs.io/)
- [Checkov](https://www.checkov.io/) (Security scanning)

---

## 🎓 Certification Information

**HashiCorp Certified: Terraform Associate**
- **Cost:** $70.50 USD
- **Duration:** 60 minutes
- **Questions:** 57
- **Validity:** 2 years
- **Covered in:** Part 11, Section 53

---

## 🤝 Contributing

Found a typo or want to improve the tutorial? Contributions are welcome!

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

---

## 📄 License

This tutorial is provided for educational purposes. Feel free to use, share, and modify.

---

## 🙏 Acknowledgments

This tutorial is based on comprehensive research and practical experience. Special thanks to:
- HashiCorp for creating Terraform
- The Terraform community
- AWS documentation
- All DevOps practitioners sharing knowledge

---

## 📮 Contact & Support

- **Questions?** Open an issue on GitHub
- **Discussion?** Join the community forums
- **Found this helpful?** ⭐ Star the repository!

---

<div align="center">

**Ready to start your Terraform journey?**

### [🚀 Begin with Part 1: Getting Started](./chapters/part-01-getting-started/README.md)

---

Made with ❤️ for the DevOps Community

![Terraform](https://img.shields.io/badge/-Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)
![Infrastructure as Code](https://img.shields.io/badge/-Infrastructure%20as%20Code-blue?style=flat-square)

</div>

---

# PART 1: GETTING STARTED

## Section 1: Introduction to Infrastructure as Code

### What You'll Learn
- What Infrastructure as Code (IaC) means
- Why IaC is important in modern DevOps
- Problems IaC solves
- How IaC changes the way we work

### The Traditional Problem

Imagine you're tasked with creating infrastructure for a new application:

**Manual Method (Old Way):**
```
Day 1: Log into AWS Console
       Create VPC (30 minutes)
       Create Subnets (20 minutes)
       Configure Security Groups (45 minutes)
       Launch EC2 instance (25 minutes)
       Total: 2 hours

Day 30: Boss: "We need the same setup for testing"
        You: Start over from scratch... 😓

Day 60: Boss: "What exactly did you create?"
        You: "Ummm... let me check..." 🤔

Day 90: New team member joins
        You: Explain verbally, hope they remember
```

**Problems with Manual Approach:**
1. ⏰ **Time-Consuming**: Repetitive clicking and waiting
2. 😱 **Error-Prone**: Easy to miss a step or misconfigure
3. 📝 **No Documentation**: Configuration lives in someone's head
4. 🔄 **Not Reproducible**: Can't easily recreate the same setup
5. 🐢 **Slow Scaling**: Creating 10 servers = 10x the time
6. 👥 **Team Bottleneck**: Only one person knows how to set it up

### The IaC Solution

**Infrastructure as Code Method:**
```
Day 1: Write Terraform code (1 hour)
       Run: terraform apply (5 minutes)
       ✅ Infrastructure created

Day 30: Boss: "We need testing environment"
        You: Run: terraform apply (5 minutes)
        ✅ Done!

Day 60: Boss: "What did you create?"
        You: "Here's the code - shows everything"

Day 90: New team member joins
        You: "Read this code, run terraform apply"
        ✅ Self-service!
```

**Benefits of IaC:**
1. ✅ **Version Controlled**: Track every change in Git
2. ✅ **Reproducible**: Same code = same infrastructure, always
3. ✅ **Fast**: Create 100 servers as easily as 1
4. ✅ **Self-Documenting**: Code IS the documentation
5. ✅ **Testable**: Test infrastructure before deploying
6. ✅ **Collaborative**: Team can review and improve together

### Real-World Analogy

**Manual Infrastructure = Cooking**
- Every meal cooked from memory
- Recipes in your head
- Hard to teach others
- Results vary each time

**Infrastructure as Code = Recipe Book**
- Written recipes anyone can follow
- Consistent results every time
- Easy to share and improve
- Can scale (cook for 2 or 200)

### When to Use IaC

**Perfect For:**
- ✅ Cloud infrastructure (AWS, Azure, GCP)
- ✅ Multi-environment setups (dev, test, prod)
- ✅ Team collaboration
- ✅ Disaster recovery
- ✅ Compliance and auditing

**Maybe Not For:**
- ❌ One-time experiments (might be overkill)
- ❌ Extremely simple setups (1-2 resources)
- ❌ Non-technical teams (learning curve)

### Exercise 1.1: Identify IaC Use Cases

**Question**: Which scenarios benefit most from IaC?

A. Creating a single test server for personal use
B. Deploying 50 identical web servers across 3 regions
C. Setting up dev, staging, and production environments
D. Learning AWS for the first time

**Answer**: B and C are perfect for IaC. A and D might be overkill.

### Key Takeaways

📌 **Remember:**
- IaC = Managing infrastructure through code
- Solves: reproducibility, documentation, scaling
- Benefits: version control, automation, collaboration
- Terraform is one of the most popular IaC tools

---

## Section 2: What is Terraform?

### What You'll Learn
- What Terraform is and isn't
- Terraform vs other tools
- How Terraform works
- Terraform ecosystem

### What is Terraform?

**Simple Definition:**
> Terraform is a tool that lets you write code to create and manage cloud infrastructure automatically.

**Technical Definition:**
> Terraform is an open-source Infrastructure as Code (IaC) tool created by HashiCorp that uses declarative configuration files to provision and manage infrastructure across multiple cloud providers.

### How Terraform Works

```
┌─────────────────────────────────────────────────┐
│  1. You Write Code (main.tf)                    │
│     "Create 3 EC2 instances with 8GB RAM"       │
└────────────────┬────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────┐
│  2. Terraform Reads Your Code                   │
│     Understands what you want                   │
└────────────────┬────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────┐
│  3. Terraform Plans                             │
│     "I'll create 3 instances like this..."      │
└────────────────┬────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────┐
│  4. Terraform Executes                          │
│     Talks to AWS API                            │
│     Creates actual infrastructure               │
└────────────────┬────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────┐
│  5. Terraform Tracks                            │
│     Saves state of what was created             │
│     Knows what exists                           │
└─────────────────────────────────────────────────┘
```

### Terraform vs Other Tools

#### Terraform vs Ansible

| Aspect | Terraform | Ansible |
|--------|-----------|---------|
| **Purpose** | Provision infrastructure | Configure infrastructure |
| **What it creates** | Servers, networks, databases | Installs software, updates configs |
| **Language** | HCL (declarative) | YAML (imperative) |
| **State tracking** | Yes (tracks infrastructure) | No (stateless) |
| **Best for** | Creating cloud resources | Configuring applications |

**Example Workflow:**
```
Terraform: Creates EC2 instance
    ↓
Ansible: Installs nginx, configures firewall
    ↓
Result: Fully configured web server
```

#### Terraform vs CloudFormation

| Aspect | Terraform | CloudFormation |
|--------|-----------|----------------|
| **Cloud Support** | AWS, Azure, GCP, 100+ | AWS only |
| **Language** | HCL (easy to read) | JSON/YAML (verbose) |
| **Community** | Large, many modules | AWS-specific |
| **Learning curve** | Moderate | Moderate-High |
| **Cost** | Free (open-source) | Free |

**Use Terraform if:** You need multi-cloud or prefer cleaner syntax  
**Use CloudFormation if:** You're AWS-only and want native integration

#### Terraform vs Pulumi

| Aspect | Terraform | Pulumi |
|--------|-----------|--------|
| **Language** | HCL (domain-specific) | Python, TypeScript, Go, C# |
| **Learning** | New language to learn | Use language you know |
| **Community** | Very large | Growing |
| **Maturity** | More mature (2014) | Newer (2018) |

### Key Terraform Features

#### 1. Multi-Cloud Support
```
Terraform can manage:
├── AWS (EC2, S3, RDS, etc.)
├── Azure (VMs, Storage, etc.)
├── Google Cloud (Compute, Storage, etc.)
├── Kubernetes
├── Docker
├── GitHub
└── 100+ other providers
```

#### 2. Declarative Language
You declare **what** you want, not **how** to create it:

```hcl
# You say: "I want this"
resource "aws_instance" "web" {
  instance_type = "t2.micro"
  ami           = "ami-12345"
}

# Terraform figures out HOW to create it
```

#### 3. Plan Before Apply
Terraform shows you changes before making them:

```bash
$ terraform plan
  + aws_instance.web will be created
  + aws_s3_bucket.data will be created
  - aws_instance.old will be destroyed

# Review changes, then apply
```

#### 4. State Management
Terraform remembers what it created:

```
terraform.tfstate file:
├── EC2 instance ID: i-1234567890
├── S3 bucket name: my-app-bucket
└── VPC ID: vpc-abcdef
```

### Terraform Workflow at a Glance

```
Write Code → Initialize → Plan → Review → Apply → Infrastructure Created
   ↓           ↓           ↓        ↓       ↓             ↓
main.tf    terraform   terraform  Check   terraform   AWS/Azure/GCP
           init        plan       output  apply       resources exist
```

### Exercise 2.1: Tool Selection

**Scenario**: You need to:
1. Create 10 EC2 instances on AWS
2. Install Docker on each
3. Deploy containers

**Which tools would you use?**

A. Terraform only
B. Ansible only
C. Terraform + Ansible
D. CloudFormation + Ansible

**Answer**: **C** - Use Terraform to create instances, Ansible to install Docker and deploy containers.

### Key Takeaways

📌 **Remember:**
- Terraform = Infrastructure provisioning tool
- Works with 100+ providers (multi-cloud)
- Declarative language (describe what you want)
- Has state tracking (remembers what exists)
- Different from Ansible (which configures software)

---

## Section 3: Setting Up Your Environment

### What You'll Learn
- Installing Terraform on your OS
- Setting up a code editor
- Configuring AWS credentials
- Creating your first project folder

### Prerequisites Checklist

Before starting, make sure you have:

- [ ] Computer (Windows, macOS, or Linux)
- [ ] Administrator/sudo access
- [ ] Internet connection
- [ ] AWS Account ([create free tier](https://aws.amazon.com/free/))
- [ ] Terminal/Command Line access

### Step 1: Install Terraform

#### **For Ubuntu/Debian Linux** 

```bash
# Update package list
sudo apt update

# Install required packages
sudo apt install -y gnupg software-properties-common curl

# Download HashiCorp GPG key
wget -O- https://apt.releases.hashicorp.com/gpg | \
    sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

# Add HashiCorp repository
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
    https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
    sudo tee /etc/apt/sources.list.d/hashicorp.list

# Update and install Terraform
sudo apt update
sudo apt install terraform

# Verify installation
terraform -version
```

**Expected Output:**
```
Terraform v1.6.0
on linux_amd64
```

#### **For macOS**

**Using Homebrew (Recommended):**

```bash
# Install Homebrew if not installed
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Add HashiCorp tap
brew tap hashicorp/tap

# Install Terraform
brew install hashicorp/tap/terraform

# Verify
terraform -version
```

**Manual Installation:**
1. Download from [terraform.io/downloads](https://www.terraform.io/downloads)
2. Extract the zip file
3. Move to `/usr/local/bin/`:
```bash
sudo mv terraform /usr/local/bin/
```

#### **For Windows**

**Method 1: Using Chocolatey (Recommended)**

```powershell
# Install Chocolatey if not installed
# Run PowerShell as Administrator
Set-ExecutionPolicy Bypass -Scope Process -Force
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

# Install Terraform
choco install terraform

# Verify
terraform -version
```

**Method 2: Manual Installation**
1. Download from [terraform.io/downloads](https://www.terraform.io/downloads)
2. Extract the ZIP file
3. Add to PATH:
   - Right-click "This PC" → Properties
   - Advanced System Settings → Environment Variables
   - Edit "Path" → Add Terraform directory
4. Open new terminal and verify:
```cmd
terraform -version
```

### Step 2: Install Code Editor

#### **Visual Studio Code (Recommended)**

**Why VS Code?**
- ✅ Free and open-source
- ✅ Excellent Terraform support
- ✅ Built-in terminal
- ✅ Git integration
- ✅ Available on all platforms

**Installation:**

1. Download from [code.visualstudio.com](https://code.visualstudio.com/)
2. Install for your OS
3. Open VS Code
4. Install Terraform extension:
   - Click Extensions icon (left sidebar)
   - Search "HashiCorp Terraform"
   - Click "Install"

**Essential Extensions:**
- **HashiCorp Terraform** - Syntax highlighting, completion
- **Terraform** - Additional language support
- **GitLens** (optional) - Enhanced Git features

#### **Alternative Editors**

- **Vim/Neovim**: For terminal users
  ```bash
  # Install Terraform plugin
  git clone https://github.com/hashivim/vim-terraform.git ~/.vim/pack/plugins/start/vim-terraform
  ```

- **IntelliJ IDEA**: With Terraform plugin
- **Sublime Text**: With Terraform package
- **Atom**: With language-terraform package

### Step 3: Install AWS CLI

**Why AWS CLI?**
- Easier authentication
- Manage AWS from terminal
- Required for some Terraform operations

#### **Ubuntu/Debian:**
```bash
sudo apt install awscli -y
aws --version
```

#### **macOS:**
```bash
brew install awscli
aws --version
```

#### **Windows:**
Download from [AWS CLI website](https://aws.amazon.com/cli/) and install.

### Step 4: Configure AWS Credentials

#### **Get AWS Access Keys**

1. Log into [AWS Console](https://console.aws.amazon.com/)
2. Click your name (top right) → Security Credentials
3. Scroll to "Access Keys"
4. Click "Create access key"
5. **Save both:**
   - Access Key ID (example: `AKIAIOSFODNN7EXAMPLE`)
   - Secret Access Key (example: `wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY`)

⚠️ **Warning**: Treat these like passwords! Never commit to Git.

#### **Configure AWS CLI**

```bash
aws configure
```

**You'll be prompted:**
```
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-east-2
Default output format [None]: json
```

**Verify Configuration:**
```bash
# Test AWS connection
aws sts get-caller-identity
```

**Expected Output:**
```json
{
    "UserId": "AIDAI...",
    "Account": "123456789012",
    "Arn": "arn:aws:iam::123456789012:user/yourname"
}
```

#### **Alternative: Use Environment Variables**

```bash
# Add to ~/.bashrc or ~/.zshrc
export AWS_ACCESS_KEY_ID="AKIAIOSFODNN7EXAMPLE"
export AWS_SECRET_ACCESS_KEY="wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY"
export AWS_DEFAULT_REGION="us-east-2"
```

### Step 5: Create Project Structure

```bash
# Create main project directory
mkdir -p ~/terraform-projects
cd ~/terraform-projects

# Create first project
mkdir my-first-terraform
cd my-first-terraform

# Create .gitignore file
cat > .gitignore << 'EOF'
# Local .terraform directories
**/.terraform/*

# .tfstate files
*.tfstate
*.tfstate.*

# Crash log files
crash.log
crash.*.log

# Exclude all .tfvars files
*.tfvars
*.tfvars.json

# Ignore CLI configuration files
.terraformrc
terraform.rc

# Ignore SSH keys
*.pem
*.key

# Ignore IDE files
.vscode/
.idea/
*.swp
*.swo
EOF

# Initialize Git (optional)
git init

# Open in VS Code
code .
```

### Step 6: Verify Everything

**Create a test file:**

```bash
# Create test.tf
cat > test.tf << 'EOF'
# Test Terraform configuration
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

# This won't create anything, just validates setup
resource "aws_default_vpc" "default" {}
EOF
```

**Test Terraform:**

```bash
# Initialize Terraform
terraform init

# Validate configuration
terraform validate

# Show plan (without creating anything)
terraform plan
```

**Expected Output:**
```
Initializing the backend...
Initializing provider plugins...
- Finding hashicorp/aws versions matching "~> 5.0"...
- Installing hashicorp/aws v5.31.0...
Success! Terraform has been successfully initialized!
```

**Cleanup test:**
```bash
rm test.tf
rm -rf .terraform
```

### Troubleshooting Common Issues

#### Issue 1: "Command not found: terraform"

**Solution:**
```bash
# Check if installed
which terraform

# If not found, check PATH
echo $PATH

# Reinstall Terraform
```

#### Issue 2: AWS credentials not working

**Solution:**
```bash
# Check credentials file
cat ~/.aws/credentials

# Test connection
aws sts get-caller-identity

# Reconfigure if needed
aws configure
```

#### Issue 3: Permission denied errors

**Solution:**
```bash
# On Linux/Mac, ensure execute permissions
chmod +x /usr/local/bin/terraform

# On Windows, run as Administrator
```

### Exercise 3.1: Environment Check

Complete this checklist:

- [ ] Terraform installed and `terraform -version` works
- [ ] VS Code installed with Terraform extension
- [ ] AWS CLI installed and configured
- [ ] Can run `aws sts get-caller-identity` successfully
- [ ] Created project directory
- [ ] Created .gitignore file
- [ ] Can run `terraform init` without errors

### Key Takeaways

📌 **Remember:**
- Terraform is installed globally on your system
- AWS CLI configuration stores credentials securely
- Always use .gitignore to avoid committing secrets
- VS Code with Terraform extension makes life easier
- Test your setup before writing real code

---

## Section 4: Your First Terraform Code

### What You'll Learn
- Writing your first Terraform configuration
- Understanding basic HCL syntax
- Creating a local file resource
- Running Terraform commands

### The Simplest Possible Example

Let's create a text file using Terraform. This teaches concepts without AWS costs.

#### Step 1: Create Project

```bash
# Create and enter project directory
mkdir terraform-hello-world
cd terraform-hello-world

# Open in VS Code
code .
```

#### Step 2: Write Your First Code

**Create file: `main.tf`**

```hcl
# My first Terraform configuration
# This creates a simple text file

resource "local_file" "hello" {
  filename = "hello.txt"
  content  = "Hello from Terraform! 🚀"
}
```

**Let's break this down line by line:**

```hcl
resource               # BLOCK: I want to create something
"local_file"          # PARAMETER 1: Type of resource (local file)
"hello"               # PARAMETER 2: Name I'm giving it (hello)
{                     # Opening brace
  filename = "hello.txt"        # ARGUMENT: Where to create file
  content  = "Hello from..."    # ARGUMENT: What to put in file
}                     # Closing brace
```

#### Step 3: Initialize Terraform

```bash
terraform init
```

**What happens?**
```
Initializing the backend...

Initializing provider plugins...
- Finding latest version of hashicorp/local...
- Installing hashicorp/local v2.4.0...
- Installed hashicorp/local v2.4.0

Terraform has been successfully initialized!
```

**What was created?**
- `.terraform/` directory - Contains provider plugins
- `.terraform.lock.hcl` - Locks provider versions

#### Step 4: Preview Changes

```bash
terraform plan
```

**Output explanation:**
```
Terraform will perform the following actions:

  # local_file.hello will be created
  + resource "local_file" "hello" {
      + content              = "Hello from Terraform! 🚀"
      + directory_permission = "0777"
      + file_permission      = "0777"
      + filename             = "hello.txt"
      + id                   = (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.
```

**Legend:**
- `+` means CREATE
- `-` means DELETE
- `~` means UPDATE

#### Step 5: Create the Resource

```bash
terraform apply
```

**You'll see:**
```
Plan: 1 to add, 0 to change, 0 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: 
```

**Type:** `yes` and press Enter

**Output:**
```
local_file.hello: Creating...
local_file.hello: Creation complete after 0s [id=c0e4...]

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```

#### Step 6: Verify It Worked

```bash
# Check if file was created
ls -la

# Read the file
cat hello.txt
```

**Expected:**
```
Hello from Terraform! 🚀
```

#### Step 7: Understand What Was Created

**New files in directory:**
```
terraform-hello-world/
├── .terraform/           # Provider plugins
├── .terraform.lock.hcl   # Version lock file
├── hello.txt             # ← Your created file!
├── main.tf               # Your configuration
└── terraform.tfstate     # ← State file (tracks what exists)
```

**Check the state file:**
```bash
cat terraform.tfstate
```

**You'll see JSON:**
```json
{
  "version": 4,
  "terraform_version": "1.6.0",
  "resources": [
    {
      "type": "local_file",
      "name": "hello",
      "instances": [
        {
          "attributes": {
            "content": "Hello from Terraform! 🚀",
            "filename": "hello.txt",
            "id": "c0e4..."
          }
        }
      ]
    }
  ]
}
```

### Understanding the Workflow

```
┌──────────────┐
│ 1. Write     │  You: Create main.tf
│    main.tf   │  
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ 2. terraform │  Terraform: Downloads local provider
│    init      │  Creates .terraform/ directory
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ 3. terraform │  Terraform: Shows what will be created
│    plan      │  "+  local_file.hello will be created"
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ 4. terraform │  You: Type "yes"
│    apply     │  Terraform: Creates hello.txt
└──────┬───────┘  Saves state in terraform.tfstate
       │
       ▼
┌──────────────┐
│ 5. Result    │  ✅ hello.txt exists
│              │  ✅ terraform.tfstate tracks it
└──────────────┘
```

### Experiment: Making Changes

#### Change 1: Update Content

**Edit `main.tf`:**
```hcl
resource "local_file" "hello" {
  filename = "hello.txt"
  content  = "Hello from Terraform! Updated! 🎉"  # Changed!
}
```

**Apply changes:**
```bash
terraform plan   # Shows update
terraform apply  # Type "yes"
```

**Output:**
```
  # local_file.hello must be replaced
-/+ resource "local_file" "hello" {
      ~ content  = "Hello from Terraform! 🚀" -> "Hello from Terraform! Updated! 🎉"
        # (other attributes unchanged)
    }

Plan: 1 to add, 0 to change, 1 to destroy.
```

Note: `-/+` means "replace" (delete and recreate)

#### Change 2: Add Another File

**Edit `main.tf`:**
```hcl
resource "local_file" "hello" {
  filename = "hello.txt"
  content  = "Hello from Terraform! 🚀"
}

# Add second file
resource "local_file" "world" {
  filename = "world.txt"
  content  = "Terraform is awesome! 🌍"
}
```

**Apply:**
```bash
terraform apply -auto-approve  # Skips confirmation
```

**Check result:**
```bash
ls *.txt
cat world.txt
```

### Cleaning Up

```bash
# Destroy everything Terraform created
terraform destroy
```

**Output:**
```
Plan: 0 to add, 0 to change, 2 to destroy.

Do you really want to destroy all resources?
  Enter a value: 
```

**Type:** `yes`

**Result:**
```
local_file.world: Destroying...
local_file.hello: Destroying...
local_file.world: Destruction complete
local_file.hello: Destruction complete

Destroy complete! Resources: 2 destroyed.
```

**Verify:**
```bash
ls *.txt  # Files are gone!
```

### Exercise 4.1: Create Your Own File

**Task**: Create a file called `myinfo.txt` with your name and favorite programming language.

**Solution:**
```hcl
resource "local_file" "myinfo" {
  filename = "myinfo.txt"
  content  = "Name: John Doe\nFavorite Language: Python"
}
```

### Exercise 4.2: Understanding State

**Question**: After running `terraform destroy`, what happens to:
1. The `hello.txt` file?
2. The `terraform.tfstate` file?
3. The `main.tf` file?

**Answers:**
1. Deleted (Terraform removes it)
2. Still exists, but shows 0 resources
3. Still exists (your configuration code)

### Common Beginner Mistakes

#### Mistake 1: Forgetting `terraform init`

```bash
$ terraform plan
Error: Could not load plugin

# Fix: Always run init first
$ terraform init
```

#### Mistake 2: Typos in Resource Names

```hcl
# Wrong
resource "local_fil" "hello" {  # Typo: "fil" instead of "file"
```

**Error:**
```
Error: Invalid resource type
```

#### Mistake 3: Mismatched Brackets

```hcl
# Wrong
resource "local_file" "hello" {
  filename = "hello.txt"
  content = "Hello"
  # Missing closing bracket!
```

**Error:**
```
Error: Unclosed configuration block
```

### Key Takeaways

📌 **Remember:**
- Terraform workflow: Write → Init → Plan → Apply
- `resource` block creates infrastructure
- `terraform.tfstate` tracks what was created
- Always run `terraform init` first in a new project
- `terraform plan` shows changes before applying
- Use `terraform destroy` to clean up

**Commands Summary:**
```bash
terraform init      # Download providers (run once)
terraform plan      # Preview changes
terraform apply     # Create/update resources
terraform destroy   # Delete resources
terraform validate  # Check syntax
terraform fmt       # Format code
```

---

## Section 5: Understanding the Terraform Workflow

### What You'll Learn
- The complete Terraform lifecycle
- When to use each command
- How Terraform tracks changes
- Best practices for workflow

### The Complete Terraform Lifecycle

```
┌─────────────────────────────────────────────────┐
│                                                 │
│  Development Cycle                              │
│                                                 │
│  ┌──────┐   ┌──────┐   ┌──────┐   ┌──────┐   │
│  │Write │ → │ Init │ → │ Plan │ → │Apply │   │
│  │ Code │   │      │   │      │   │      │   │
│  └──────┘   └──────┘   └──────┘   └──────┘   │
│      │          │           │          │       │
│      └──────────┴───────────┴──────────┘       │
│                     ↓                           │
│               ┌──────────┐                      │
│               │Infrastructure│                  │
│               │   Running   │                  │
│               └──────────┘                      │
│                     │                           │
│                     ↓                           │
│              ┌──────────┐                       │
│              │ Destroy  │ (When done)          │
│              └──────────┘                       │
│                                                 │
└─────────────────────────────────────────────────┘
```

### Phase 1: Write Code

**What You Do:**
Create `.tf` files with your infrastructure requirements

**Example Directory:**
```
my-project/
├── main.tf        # Main configuration
├── variables.tf   # Input variables
├── outputs.tf     # Output values
└── .gitignore     # Git ignore file
```

**Best Practices:**
```hcl
# main.tf
# Use comments to explain complex sections
resource "aws_instance" "web" {
  # Configuration here
}
```

### Phase 2: Initialize (`terraform init`)

**Command:**
```bash
terraform init
```

**What It Does:**
1. Creates `.terraform/` directory
2. Downloads required provider plugins
3. Sets up backend for state storage
4. Creates `.terraform.lock.hcl` (version lock file)

**When to Run:**
- ✅ First time in a new project
- ✅ After adding new providers
- ✅ After cloning a repository
- ✅ After backend configuration changes

**Example Output:**
```
Initializing the backend...

Initializing provider plugins...
- Finding hashicorp/aws versions matching "~> 5.0"...
- Installing hashicorp/aws v5.31.0...

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan".
```

**What Gets Created:**
```
my-project/
├── .terraform/
│   └── providers/
│       └── hashicorp/
│           └── aws/
│               └── 5.31.0/
│                   └── linux_amd64/
│                       └── terraform-provider-aws_v5.31.0
├── .terraform.lock.hcl  # ← Version lock file
└── main.tf
```

### Phase 3: Validate (`terraform validate`)

**Command:**
```bash
terraform validate
```

**What It Does:**
- Checks syntax errors
- Validates resource configurations
- Checks for missing required arguments
- Does NOT check if resources actually exist

**Example - Valid Configuration:**
```bash
$ terraform validate
Success! The configuration is valid.
```

**Example - Invalid Configuration:**
```hcl
# main.tf with error
resource "aws_instance" "web" {
  instance_type = "t2.micro"
  # Missing required argument: ami
}
```

```bash
$ terraform validate
Error: Missing required argument

  on main.tf line 1:
   1: resource "aws_instance" "web" {

The argument "ami" is required, but no definition was found.
```

### Phase 4: Format (`terraform fmt`)

**Command:**
```bash
terraform fmt
```

**What It Does:**
- Formats code to canonical style
- Fixes indentation
- Aligns equals signs
- Makes code consistent

**Example - Before:**
```hcl
resource "aws_instance" "web" {
instance_type="t2.micro"
  ami   =    "ami-12345"
    tags={
Name="web-server"
}
}
```

**After running `terraform fmt`:**
```hcl
resource "aws_instance" "web" {
  instance_type = "t2.micro"
  ami           = "ami-12345"
  tags = {
    Name = "web-server"
  }
}
```

**Pro Tip:**
```bash
# Format all .tf files recursively
terraform fmt -recursive
```

### Phase 5: Plan (`terraform plan`)

**Command:**
```bash
terraform plan
```

**What It Does:**
1. Reads current state
2. Reads your configuration
3. Compares them
4. Shows what will change
5. Does NOT make any changes

**Example Output:**
```
Terraform will perform the following actions:

  # aws_instance.web will be created
  + resource "aws_instance" "web" {
      + ami                    = "ami-12345"
      + instance_type          = "t2.micro"
      + id                     = (known after apply)
      + public_ip              = (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.
```

**Understanding the Symbols:**
- `+` = Resource will be CREATED
- `-` = Resource will be DESTROYED
- `~` = Resource will be UPDATED in-place
- `-/+` = Resource will be REPLACED (destroyed and created)
- `(known after apply)` = Value will be determined during apply

**Save Plan to File:**
```bash
# Save plan
terraform plan -out=myplan

# Review saved plan
terraform show myplan

# Apply saved plan (skips confirmation)
terraform apply myplan
```

### Phase 6: Apply (`terraform apply`)

**Command:**
```bash
terraform apply
```

**What It Does:**
1. Runs plan again
2. Shows proposed changes
3. Asks for confirmation
4. Creates/updates/deletes resources
5. Updates state file

**Example Workflow:**
```bash
$ terraform apply

Terraform will perform the following actions:
  # ... plan output ...

Do you want to perform these actions?
  Only 'yes' will be accepted to approve.

  Enter a value: yes

aws_instance.web: Creating...
aws_instance.web: Still creating... [10s elapsed]
aws_instance.web: Still creating... [20s elapsed]
aws_instance.web: Creation complete after 25s [id=i-1234...]

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```

**Skip Confirmation:**
```bash
terraform apply -auto-approve  # Useful for automation
```

**Apply Specific Resource:**
```bash
terraform apply -target=aws_instance.web
```

### Phase 7: Refresh (`terraform refresh`)

**Command:**
```bash
terraform refresh
```

**What It Does:**
- Updates state file with real infrastructure
- Does NOT modify infrastructure
- Detects manual changes

**When to Use:**
- Someone made manual changes in AWS Console
- Need to sync state with reality
- Before destroying resources

**Note:** `terraform apply` automatically refreshes first.

### Phase 8: Show (`terraform show`)

**Command:**
```bash
terraform show
```

**What It Does:**
- Displays current state
- Shows all managed resources
- Prints in human-readable format

**Example Output:**
```
# aws_instance.web:
resource "aws_instance" "web" {
    ami                    = "ami-12345"
    instance_type          = "t2.micro"
    id                     = "i-1234567890abcdef0"
    public_ip              = "54.123.45.67"
    tags                   = {
        "Name" = "web-server"
    }
}
```

### Phase 9: Output (`terraform output`)

**Command:**
```bash
terraform output
```

**What It Does:**
- Shows output values from state
- Useful for getting resource details

**Example:**
```bash
$ terraform output
instance_ip = "54.123.45.67"
instance_id = "i-1234567890abcdef0"

# Get specific output
$ terraform output instance_ip
54.123.45.67
```

### Phase 10: Destroy (`terraform destroy`)

**Command:**
```bash
terraform destroy
```

**What It Does:**
- Deletes ALL managed resources
- Updates state file
- Asks for confirmation

**Example:**
```bash
$ terraform destroy

Terraform will perform the following actions:

  # aws_instance.web will be destroyed
  - resource "aws_instance" "web" {
      - ami           = "ami-12345"
      - id            = "i-1234567890abcdef0"
    }

Plan: 0 to add, 0 to change, 1 to destroy.

Do you really want to destroy all resources?
  Enter a value: yes

aws_instance.web: Destroying...
aws_instance.web: Destruction complete after 30s

Destroy complete! Resources: 1 destroyed.
```

**Destroy Specific Resource:**
```bash
terraform destroy -target=aws_instance.web
```

### Real-World Workflow Example

**Day 1: Create New Project**
```bash
# 1. Create project
mkdir my-app-infra
cd my-app-infra

# 2. Write configuration
cat > main.tf << 'EOF'
# Configuration here
EOF

# 3. Initialize
terraform init

# 4. Validate
terraform validate

# 5. Format
terraform fmt

# 6. Plan
terraform plan

# 7. Apply
terraform apply
```

**Day 2: Make Changes**
```bash
# 1. Edit main.tf (add more resources)
vim main.tf

# 2. Format
terraform fmt

# 3. Validate
terraform validate

# 4. Plan (review changes)
terraform plan

# 5. Apply (if looks good)
terraform apply
```

**Day 30: Cleanup**
```bash
# Destroy everything
terraform destroy
```

### Workflow Best Practices

#### 1. Always Follow This Order
```
init → validate → fmt → plan → apply
```

#### 2. Never Skip `terraform plan`
```bash
# ❌ DON'T DO THIS
terraform apply -auto-approve

# ✅ DO THIS
terraform plan    # Review changes
terraform apply   # Confirm and apply
```

#### 3. Save Important Plans
```bash
# Before big changes
terraform plan -out=production.plan

# Review with team
terraform show production.plan

# Apply when approved
terraform apply production.plan
```

#### 4. Use Version Control
```bash
# After every successful change
git add main.tf
git commit -m "Added new EC2 instance"
git push
```

#### 5. Document Your Changes
```hcl
# main.tf
# 2024-12-19: Added web server for production app
resource "aws_instance" "web" {
  # Configuration
}
```

### Exercise 5.1: Complete Workflow

**Task**: Create complete workflow for a local file

1. Create `main.tf` with local_file resource
2. Run all commands in correct order
3. Modify the file content
4. Apply changes
5. Destroy

**Solution:**
```bash
# Step 1: Create project
mkdir workflow-practice
cd workflow-practice

# Step 2: Write config
cat > main.tf << 'EOF'
resource "local_file" "practice" {
  filename = "practice.txt"
  content  = "Learning Terraform workflow"
}
EOF

# Step 3: Run workflow
terraform init
terraform validate
terraform fmt
terraform plan
terraform apply

# Step 4: Make change
sed -i 's/Learning/Mastering/' main.tf

# Step 5: Apply change
terraform plan
terraform apply

# Step 6: Clean up
terraform destroy
```

### Exercise 5.2: Understand Plan Output

Given this plan output:
```
Plan: 2 to add, 1 to change, 1 to destroy.
```

**Questions:**
1. How many resources will be created?
2. How many will be updated?
3. How many will be deleted?
4. Total resources after apply?

**Answers:**
1. 2 new resources
2. 1 updated
3. 1 deleted
4. Can't determine without knowing current count

### Troubleshooting Common Issues

#### Issue: "Backend initialization required"
```bash
Error: Backend initialization required

Solution:
$ terraform init
```

#### Issue: "State lock" error
```bash
Error: Error acquiring the state lock

Solution:
Wait for other operation to finish, or:
$ terraform force-unlock <LOCK_ID>
```

#### Issue: "Provider configuration not present"
```bash
Error: Provider configuration not present

Solution:
Add provider block and run:
$ terraform init
```

### Key Takeaways

📌 **Remember:**
- **init**: Download providers (once per project)
- **validate**: Check syntax
- **fmt**: Format code
- **plan**: Preview changes (always!)
- **apply**: Make changes
- **destroy**: Delete everything

**Golden Rule:**
> Always run `terraform plan` before `terraform apply`

**Essential Commands:**
```bash
terraform init      # Start here
terraform validate  # Check syntax
terraform fmt       # Clean code
terraform plan      # Review changes
terraform apply     # Deploy
terraform destroy   # Clean up
```

---

## Section 6: The HCL Language Fundamentals

### What You'll Learn
- HCL syntax and structure
- Blocks, parameters, and arguments
- Comments and formatting
- Data types in HCL
- The "Block-Parameter-Arguments" mantra

### The Terraform Mantra

Everything in Terraform follows one golden rule:

```
BLOCK + PARAMETERS + { ARGUMENTS }
```

This is the **most important concept** to understand. Let's break it down:

### Part 1: BLOCK (What to do)

A **block** defines **what type of thing** you want to work with.

**Common Blocks:**

```hcl
resource      # Create infrastructure
variable      # Define input variables
output        # Display output values
provider      # Configure cloud provider
data          # Fetch existing data
module        # Use reusable modules
locals        # Define local variables
terraform     # Configure Terraform itself
```

### Part 2: PARAMETERS (Details about what)

**Parameters** come after the block name and provide:
1. The **type** of resource
2. The **name** you give it

**Syntax:**
```hcl
block "parameter1" "parameter2" {
  # arguments here
}
```

**Examples:**

```hcl
# Resource block: 2 parameters
resource "aws_instance" "my_server" {
  # ↑ Type         ↑ Name
}

# Variable block: 1 parameter
variable "region" {
  # ↑ Name
}

# Output block: 1 parameter
output "server_ip" {
  # ↑ Name
}
```

### Part 3: ARGUMENTS (Configuration)

**Arguments** are the actual configuration inside `{ }` brackets.

**Format:**
```hcl
argument_name = value
```

**Example:**
```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"      # Argument 1
  instance_type = "t2.micro"       # Argument 2
  count         = 3                # Argument 3
  
  tags = {                         # Argument 4 (nested)
    Name = "web-server"
  }
}
```

### Complete Example with Annotations

```hcl
# ┌─────────── BLOCK: What type of thing
# │           ┌────────────── PARAMETER 1: Resource type
# │           │              ┌─────── PARAMETER 2: Resource name
# ▼           ▼              ▼
resource "aws_instance" "my_server" {
  #         ┌──────────────── ARGUMENT: Which image to use
  #         ▼
  ami           = "ami-abc123"
  instance_type = "t2.micro"
  #               └──────────── ARGUMENT VALUE
  
  # Nested argument
  tags = {
    Name        = "MyServer"
    Environment = "dev"
  }
}
```

### HCL Data Types

#### 1. String
```hcl
variable "region" {
  type    = string
  default = "us-east-2"
}

# Usage
region = "us-west-1"
```

#### 2. Number
```hcl
variable "instance_count" {
  type    = number
  default = 3
}

# Usage
count = 5
port  = 80
```

#### 3. Boolean
```hcl
variable "enable_monitoring" {
  type    = bool
  default = true
}

# Usage
enable_monitoring = false
```

#### 4. List
```hcl
variable "availability_zones" {
  type    = list(string)
  default = ["us-east-2a", "us-east-2b", "us-east-2c"]
}

# Access elements
azs = var.availability_zones[0]  # "us-east-2a"
```

#### 5. Map
```hcl
variable "instance_types" {
  type = map(string)
  default = {
    dev  = "t2.micro"
    prod = "t2.large"
  }
}

# Access values
instance_type = var.instance_types["dev"]  # "t2.micro"
```

#### 6. Object
```hcl
variable "server_config" {
  type = object({
    instance_type = string
    ami           = string
    volume_size   = number
  })
  
  default = {
    instance_type = "t2.micro"
    ami           = "ami-12345"
    volume_size   = 20
  }
}

# Access attributes
ami = var.server_config.ami
```

### Comments in HCL

```hcl
# Single line comment

// Also a single line comment

/*
  Multi-line
  comment block
*/

resource "aws_instance" "web" {
  ami = "ami-12345"  # Inline comment
}
```

### HCL Syntax Rules

#### 1. Indentation
```hcl
# ✅ GOOD: 2 spaces
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
}

# ❌ BAD: Inconsistent indentation
resource "aws_instance" "web" {
ami = "ami-12345"
    instance_type = "t2.micro"
}
```

#### 2. Quotes
```hcl
# ✅ Strings need quotes
region = "us-east-2"

# ✅ Numbers and booleans don't
count   = 3
enabled = true

# ❌ Don't quote numbers/booleans
count   = "3"      # This makes it a string!
enabled = "true"   # This is a string, not boolean!
```

#### 3. Equals Signs
```hcl
# ✅ Align equals signs for readability
ami           = "ami-12345"
instance_type = "t2.micro"

# ✅ But not required
ami = "ami-12345"
instance_type = "t2.micro"
```

#### 4. Brackets and Braces
```hcl
# Lists use square brackets [ ]
list = ["item1", "item2", "item3"]

# Maps and blocks use curly braces { }
map = {
  key1 = "value1"
  key2 = "value2"
}

resource "aws_instance" "web" {
  # Block body
}
```

### Real-World Examples

#### Example 1: Simple Resource

```hcl
resource "local_file" "readme" {
  filename = "README.md"
  content  = "# My Project"
}
```

**Breakdown:**
- Block: `resource`
- Parameters: `"local_file"` (type), `"readme"` (name)
- Arguments: `filename`, `content`

#### Example 2: AWS EC2 Instance

```hcl
resource "aws_instance" "web_server" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  
  tags = {
    Name        = "WebServer"
    Environment = "Production"
  }
}
```

**Breakdown:**
- Block: `resource`
- Parameters: `"aws_instance"`, `"web_server"`
- Arguments: `ami`, `instance_type`, `tags`
- Nested map: `tags` contains key-value pairs

#### Example 3: Variable with Validation

```hcl
variable "environment" {
  type        = string
  description = "Environment name"
  default     = "dev"
  
  validation {
    condition     = contains(["dev", "staging", "prod"], var.environment)
    error_message = "Environment must be dev, staging, or prod."
  }
}
```

**Breakdown:**
- Block: `variable`
- Parameter: `"environment"`
- Arguments: `type`, `description`, `default`
- Nested block: `validation` with its own arguments

### HCL Special Syntax

#### 1. Heredoc Strings
```hcl
# For multi-line strings
user_data = <<-EOF
  #!/bin/bash
  echo "Hello World"
  apt-get update
  apt-get install -y nginx
EOF
```

#### 2. String Templates
```hcl
# Interpolation
name = "${var.environment}-server"

# Expression
count = var.enabled ? 1 : 0
```

#### 3. For Expressions
```hcl
# Transform a list
upper_names = [for name in var.names : upper(name)]

# Transform a map
ports = {for k, v in var.services : k => v.port}
```

### Practical Exercise 6.1: Write Basic HCL

**Task:** Create a configuration with these requirements:
1. A variable for region (string)
2. A variable for instance count (number)
3. A local file resource
4. An output for the file's ID

**Solution:**
```hcl
variable "region" {
  type    = string
  default = "us-east-2"
}

variable "instance_count" {
  type    = number
  default = 3
}

resource "local_file" "config" {
  filename = "config.txt"
  content  = "Region: ${var.region}, Count: ${var.instance_count}"
}

output "file_id" {
  value = local_file.config.id
}
```

### Exercise 6.2: Identify Parts

Given this code, identify:
```hcl
resource "aws_s3_bucket" "data_bucket" {
  bucket = "my-data-bucket"
  acl    = "private"
}
```

**Questions:**
1. What is the block?
2. What are the parameters?
3. What are the arguments?
4. What values are strings?

**Answers:**
1. Block: `resource`
2. Parameters: `"aws_s3_bucket"`, `"data_bucket"`
3. Arguments: `bucket`, `acl`
4. Strings: `"my-data-bucket"`, `"private"`

### Common Mistakes

#### Mistake 1: Forgetting Quotes
```hcl
# ❌ Wrong
resource aws_instance web {
  # Error: String literal expected
}

# ✅ Correct
resource "aws_instance" "web" {
}
```

#### Mistake 2: Wrong Bracket Type
```hcl
# ❌ Wrong
tags = [
  Name = "server"
]

# ✅ Correct
tags = {
  Name = "server"
}
```

#### Mistake 3: Missing Equals Sign
```hcl
# ❌ Wrong
resource "aws_instance" "web" {
  ami "ami-12345"
}

# ✅ Correct
resource "aws_instance" "web" {
  ami = "ami-12345"
}
```

### Key Takeaways

📌 **Remember:**
- Everything follows: BLOCK + PARAMETERS + { ARGUMENTS }
- Strings need quotes, numbers and booleans don't
- Use 2-space indentation
- Comments start with `#` or `//`
- Lists use `[ ]`, maps and blocks use `{ }`
- `terraform fmt` fixes formatting automatically

---

## Section 7: Working with Providers

### What You'll Learn
- What providers are and why they're needed
- Installing and configuring providers
- Provider version constraints
- Working with multiple providers
- Popular providers overview

### What Are Providers?

**Simple Definition:**
> Providers are plugins that let Terraform talk to different services (AWS, Azure, Docker, GitHub, etc.)

**Technical Definition:**
> Providers are Terraform plugins that define and implement resource types for a specific platform or service API.

### How Providers Work

```
┌──────────────┐
│ Your Code    │  resource "aws_instance" "web" { }
│  (main.tf)   │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│   Terraform  │  Reads your code
│    Core      │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ AWS Provider │  Translates to AWS API calls
│   Plugin     │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│  AWS API     │  Creates actual resources
│              │  (EC2, S3, etc.)
└──────────────┘
```

### Provider Configuration

#### Basic Provider Setup

**Step 1: Specify Required Providers**

```hcl
# terraform.tf
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}
```

**Breakdown:**
- `source`: Where to download the provider from
  - Format: `namespace/provider`
  - Example: `hashicorp/aws`
- `version`: Which version to use
  - `"~> 5.0"` = Any 5.x version (5.0, 5.1, 5.2, but not 6.0)

**Step 2: Configure the Provider**

```hcl
# provider.tf
provider "aws" {
  region = "us-east-2"
}
```

### Version Constraints

```hcl
# Exact version
version = "5.0.0"

# Greater than or equal
version = ">= 5.0"

# Less than
version = "< 6.0"

# Pessimistic constraint (recommended)
version = "~> 5.0"   # Allows 5.x, but not 6.0
version = "~> 5.1.0" # Allows 5.1.x, but not 5.2.0

# Range
version = ">= 5.0, < 6.0"

# Multiple acceptable versions
version = ">= 5.0, != 5.1.0, < 6.0"
```

### Popular Providers

#### 1. AWS Provider

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region     = "us-east-2"
  access_key = var.aws_access_key  # Not recommended
  secret_key = var.aws_secret_key  # Not recommended
  
  # Better: Use AWS CLI credentials or IAM roles
}

# Create resource
resource "aws_s3_bucket" "example" {
  bucket = "my-bucket"
}
```

#### 2. Azure Provider

```hcl
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "~> 3.0"
    }
  }
}

provider "azurerm" {
  features {}  # Required but can be empty
}

resource "azurerm_resource_group" "example" {
  name     = "my-resources"
  location = "East US"
}
```

#### 3. Google Cloud Provider

```hcl
terraform {
  required_providers {
    google = {
      source  = "hashicorp/google"
      version = "~> 5.0"
    }
  }
}

provider "google" {
  project = "my-project-id"
  region  = "us-central1"
}

resource "google_storage_bucket" "example" {
  name     = "my-bucket"
  location = "US"
}
```

#### 4. Docker Provider

```hcl
terraform {
  required_providers {
    docker = {
      source  = "kreuzwerker/docker"
      version = "~> 3.0"
    }
  }
}

provider "docker" {
  host = "unix:///var/run/docker.sock"
}

resource "docker_container" "nginx" {
  name  = "my-nginx"
  image = "nginx:latest"
}
```

#### 5. Local Provider (Built-in)

```hcl
# No provider configuration needed for local

resource "local_file" "example" {
  filename = "output.txt"
  content  = "Hello Terraform"
}
```

### Multiple Provider Configurations

You can use multiple instances of the same provider:

```hcl
# Default provider for us-east-2
provider "aws" {
  region = "us-east-2"
}

# Alias for us-west-2
provider "aws" {
  alias  = "west"
  region = "us-west-2"
}

# Use default provider
resource "aws_instance" "east" {
  ami           = "ami-east"
  instance_type = "t2.micro"
}

# Use aliased provider
resource "aws_instance" "west" {
  provider      = aws.west
  ami           = "ami-west"
  instance_type = "t2.micro"
}
```

### Provider Authentication Methods

#### AWS Authentication

**Method 1: AWS CLI (Recommended)**
```bash
aws configure
# Terraform automatically uses these credentials
```

**Method 2: Environment Variables**
```bash
export AWS_ACCESS_KEY_ID="AKIAIOSFODNN7EXAMPLE"
export AWS_SECRET_ACCESS_KEY="wJalr..."
export AWS_DEFAULT_REGION="us-east-2"
```

**Method 3: Provider Block (Not Recommended)**
```hcl
provider "aws" {
  region     = "us-east-2"
  access_key = "AKIAIOSFODNN7EXAMPLE"  # ❌ Don't hardcode!
  secret_key = "wJalr..."               # ❌ Security risk!
}
```

**Method 4: IAM Roles (Best for EC2/ECS)**
```hcl
provider "aws" {
  region = "us-east-2"
  # Automatically uses IAM role attached to instance
}
```

### Provider Features

#### Default Tags

```hcl
provider "aws" {
  region = "us-east-2"
  
  default_tags {
    tags = {
      ManagedBy   = "Terraform"
      Environment = "Production"
      Team        = "DevOps"
    }
  }
}

# All AWS resources will automatically get these tags
```

#### Assume Role

```hcl
provider "aws" {
  region = "us-east-2"
  
  assume_role {
    role_arn = "arn:aws:iam::123456789:role/TerraformRole"
  }
}
```

### Finding Providers

**Terraform Registry:** https://registry.terraform.io/

Search for providers:
- AWS: `hashicorp/aws`
- Azure: `hashicorp/azurerm`
- GCP: `hashicorp/google`
- Kubernetes: `hashicorp/kubernetes`
- GitHub: `integrations/github`
- Docker: `kreuzwerker/docker`

### Provider Documentation

Each provider has extensive documentation:

```
https://registry.terraform.io/providers/hashicorp/aws/latest/docs
                                        ↑         ↑
                                   namespace   provider
```

**Example - Find EC2 Documentation:**
1. Go to AWS provider docs
2. Search "EC2" or "aws_instance"
3. Read resource documentation
4. Copy example code

### Exercise 7.1: Configure Multiple Providers

**Task:** Set up configuration for AWS and Docker

**Solution:**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
    docker = {
      source  = "kreuzwerker/docker"
      version = "~> 3.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

provider "docker" {
  host = "unix:///var/run/docker.sock"
}

# Now you can use both!
resource "aws_s3_bucket" "data" {
  bucket = "my-data"
}

resource "docker_container" "app" {
  name  = "my-app"
  image = "nginx:latest"
}
```

### Exercise 7.2: Understanding Version Constraints

**Question:** What versions are allowed?

```hcl
version = "~> 5.2.0"
```

A. 5.2.0, 5.2.1, 5.2.2, 5.3.0
B. 5.2.0, 5.2.1, 5.2.2
C. 5.0.0, 5.1.0, 5.2.0
D. Any 5.x version

**Answer:** B - Allows 5.2.x but not 5.3.0

### Common Issues

#### Issue 1: Provider Not Found

```
Error: Failed to query available provider packages
```

**Solution:**
```bash
# Run terraform init to download providers
terraform init
```

#### Issue 2: Version Conflict

```
Error: Unsupported Terraform Core version
```

**Solution:**
```hcl
# Check Terraform version
terraform version

# Update constraint
terraform {
  required_version = ">= 1.0"  # Adjust as needed
}
```

#### Issue 3: Authentication Failed

```
Error: No valid credential sources found
```

**Solution:**
```bash
# Configure AWS CLI
aws configure

# Or set environment variables
export AWS_ACCESS_KEY_ID="..."
export AWS_SECRET_ACCESS_KEY="..."
```

### Key Takeaways

📌 **Remember:**
- Providers = Plugins that talk to services
- Specify in `terraform { required_providers { } }`
- Configure with `provider { }` block
- Use `~>` for version constraints
- Never hardcode credentials
- Run `terraform init` to download providers

**Essential Providers:**
- AWS: `hashicorp/aws`
- Azure: `hashicorp/azurerm`
- GCP: `hashicorp/google`
- Kubernetes: `hashicorp/kubernetes`

---

## Section 8: Variables Deep Dive

### What You'll Learn
- Input variables in detail
- Variable types and validation
- Default values and precedence
- Variable files (tfvars)
- Sensitive variables
- Best practices

### Why Use Variables?

**Without Variables:**
```hcl
# ❌ Hardcoded values - hard to reuse
resource "aws_instance" "web" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  
  tags = {
    Environment = "production"
  }
}
```

**With Variables:**
```hcl
# ✅ Flexible and reusable
resource "aws_instance" "web" {
  ami           = var.ami_id
  instance_type = var.instance_type
  
  tags = {
    Environment = var.environment
  }
}
```

### Defining Variables

**File: `variables.tf`**

```hcl
variable "region" {
  description = "AWS region to deploy resources"
  type        = string
  default     = "us-east-2"
}

variable "instance_count" {
  description = "Number of instances to create"
  type        = number
  default     = 1
}

variable "enable_monitoring" {
  description = "Enable detailed monitoring"
  type        = bool
  default     = false
}
```

### Variable Properties

```hcl
variable "name" {
  description = "Human-readable description"    # What this variable is for
  type        = string                          # Data type
  default     = "value"                         # Default value (optional)
  sensitive   = false                           # Hide in output (optional)
  nullable    = true                            # Allow null (optional)
  
  validation {                                  # Custom validation (optional)
    condition     = length(var.name) > 3
    error_message = "Name must be longer than 3 characters."
  }
}
```

### Variable Types in Detail

#### 1. String Variables

```hcl
variable "project_name" {
  type        = string
  description = "Name of the project"
  default     = "my-project"
}

# Usage
name = var.project_name
```

#### 2. Number Variables

```hcl
variable "instance_count" {
  type    = number
  default = 3
}

variable "port" {
  type    = number
  default = 443
}

# Usage
count = var.instance_count
```

#### 3. Boolean Variables

```hcl
variable "enable_backup" {
  type    = bool
  default = true
}

# Usage in conditional
count = var.enable_backup ? 1 : 0
```

#### 4. List Variables

```hcl
# Simple list
variable "availability_zones" {
  type = list(string)
  default = [
    "us-east-2a",
    "us-east-2b",
    "us-east-2c"
  ]
}

# Usage
azs = var.availability_zones

# Access specific element
first_az = var.availability_zones[0]

# Loop through list
resource "aws_subnet" "public" {
  count             = length(var.availability_zones)
  availability_zone = var.availability_zones[count.index]
}
```

#### 5. Map Variables

```hcl
variable "instance_types" {
  type = map(string)
  default = {
    dev     = "t2.micro"
    staging = "t2.small"
    prod    = "t2.large"
  }
}

# Usage
instance_type = var.instance_types["dev"]

# Or with lookup
instance_type = lookup(var.instance_types, var.environment, "t2.micro")
```

#### 6. Object Variables

```hcl
variable "server_config" {
  type = object({
    instance_type = string
    ami           = string
    volume_size   = number
    tags          = map(string)
  })
  
  default = {
    instance_type = "t2.micro"
    ami           = "ami-12345"
    volume_size   = 20
    tags = {
      Name = "default"
    }
  }
}

# Usage
resource "aws_instance" "server" {
  ami           = var.server_config.ami
  instance_type = var.server_config.instance_type
  
  root_block_device {
    volume_size = var.server_config.volume_size
  }
  
  tags = var.server_config.tags
}
```

#### 7. Tuple Variables

```hcl
variable "network_config" {
  type = tuple([string, number, bool])
  default = ["10.0.0.0/16", 3, true]
}

# Access by index
cidr_block = var.network_config[0]  # "10.0.0.0/16"
subnet_count = var.network_config[1]  # 3
enable_nat = var.network_config[2]    # true
```

#### 8. Set Variables

```hcl
variable "allowed_ports" {
  type    = set(number)
  default = [22, 80, 443]
}

# Usage with for_each
resource "aws_security_group_rule" "ingress" {
  for_each = var.allowed_ports
  
  type        = "ingress"
  from_port   = each.value
  to_port     = each.value
  protocol    = "tcp"
  cidr_blocks = ["0.0.0.0/0"]
}
```

### Providing Variable Values

#### Method 1: Command Line

```bash
terraform apply -var="region=us-west-2" -var="instance_count=5"
```

#### Method 2: Variable Files (terraform.tfvars)

**File: `terraform.tfvars`**
```hcl
region         = "us-west-2"
instance_count = 5
enable_backup  = true

instance_types = {
  dev  = "t2.micro"
  prod = "t2.xlarge"
}
```

```bash
# Automatically loaded
terraform apply

# Or specify file
terraform apply -var-file="production.tfvars"
```

#### Method 3: Environment Variables

```bash
export TF_VAR_region="us-west-2"
export TF_VAR_instance_count=5

terraform apply
```

#### Method 4: Interactive Prompt

```bash
# If no value provided, Terraform asks
terraform apply

var.region
  Enter a value: us-west-2
```

### Variable Precedence (Priority)

When the same variable is defined multiple places:

```
1. Command line (-var)          ← Highest priority
2. .auto.tfvars files
3. terraform.tfvars file
4. Environment variables (TF_VAR_*)
5. Default value in variable block  ← Lowest priority
```

### Variable Validation

```hcl
variable "instance_type" {
  type        = string
  description = "EC2 instance type"
  
  validation {
    condition     = contains(["t2.micro", "t2.small", "t2.medium"], var.instance_type)
    error_message = "Instance type must be t2.micro, t2.small, or t2.medium."
  }
}

variable "environment" {
  type = string
  
  validation {
    condition     = can(regex("^(dev|staging|prod)$", var.environment))
    error_message = "Environment must be dev, staging, or prod."
  }
}

variable "cidr_block" {
  type = string
  
  validation {
    condition     = can(cidrhost(var.cidr_block, 0))
    error_message = "Must be a valid IPv4 CIDR block."
  }
}
```

### Sensitive Variables

```hcl
variable "database_password" {
  type        = string
  description = "Database admin password"
  sensitive   = true
  # No default for secrets!
}

# Usage
resource "aws_db_instance" "database" {
  password = var.database_password
}
```

**Output is hidden:**
```bash
terraform apply
# Shows: <sensitive> instead of actual value
```

### Complex Variable Example

```hcl
variable "application_config" {
  description = "Complete application configuration"
  type = object({
    name        = string
    environment = string
    vpc_config = object({
      cidr_block      = string
      azs             = list(string)
      private_subnets = list(string)
      public_subnets  = list(string)
    })
    ec2_config = object({
      instance_type = string
      ami_id        = string
      count         = number
    })
    tags = map(string)
  })
  
  default = {
    name        = "web-app"
    environment = "production"
    vpc_config = {
      cidr_block      = "10.0.0.0/16"
      azs             = ["us-east-2a", "us-east-2b"]
      private_subnets = ["10.0.1.0/24", "10.0.2.0/24"]
      public_subnets  = ["10.0.101.0/24", "10.0.102.0/24"]
    }
    ec2_config = {
      instance_type = "t2.micro"
      ami_id        = "ami-0c55b159cbfafe1f0"
      count         = 2
    }
    tags = {
      ManagedBy = "Terraform"
      Team      = "DevOps"
    }
  }
}

# Usage
module "vpc" {
  source = "./modules/vpc"
  
  cidr_block      = var.application_config.vpc_config.cidr_block
  azs             = var.application_config.vpc_config.azs
  private_subnets = var.application_config.vpc_config.private_subnets
  public_subnets  = var.application_config.vpc_config.public_subnets
  
  tags = merge(
    var.application_config.tags,
    { Name = "${var.application_config.name}-vpc" }
  )
}
```

### Environment-Specific Variables

**Directory Structure:**
```
project/
├── variables.tf
├── main.tf
├── dev.tfvars
├── staging.tfvars
└── prod.tfvars
```

**File: `dev.tfvars`**
```hcl
environment    = "dev"
instance_type  = "t2.micro"
instance_count = 1
enable_backup  = false
```

**File: `prod.tfvars`**
```hcl
environment    = "prod"
instance_type  = "t2.large"
instance_count = 5
enable_backup  = true
```

**Usage:**
```bash
# Deploy to dev
terraform apply -var-file="dev.tfvars"

# Deploy to prod
terraform apply -var-file="prod.tfvars"
```

### Exercise 8.1: Create Variable Configuration

**Task:** Create variables for a web application with:
1. Region (string, default: us-east-2)
2. Instance type (string, validated: t2.micro, t2.small, t2.medium)
3. Number of instances (number, 1-10)
4. Environment (string, validated: dev, staging, prod)
5. Tags (map of strings)

**Solution:**
```hcl
variable "region" {
  type        = string
  description = "AWS region"
  default     = "us-east-2"
}

variable "instance_type" {
  type        = string
  description = "EC2 instance type"
  default     = "t2.micro"
  
  validation {
    condition     = contains(["t2.micro", "t2.small", "t2.medium"], var.instance_type)
    error_message = "Must be t2.micro, t2.small, or t2.medium."
  }
}

variable "instance_count" {
  type        = number
  description = "Number of instances"
  default     = 1
  
  validation {
    condition     = var.instance_count >= 1 && var.instance_count <= 10
    error_message = "Instance count must be between 1 and 10."
  }
}

variable "environment" {
  type        = string
  description = "Environment name"
  
  validation {
    condition     = contains(["dev", "staging", "prod"], var.environment)
    error_message = "Must be dev, staging, or prod."
  }
}

variable "tags" {
  type        = map(string)
  description = "Resource tags"
  default = {
    ManagedBy = "Terraform"
  }
}
```

### Best Practices

#### 1. Always Use Descriptions
```hcl
# ✅ Good
variable "region" {
  description = "AWS region for resources"
  type        = string
}

# ❌ Bad
variable "region" {
  type = string
}
```

#### 2. Specify Types
```hcl
# ✅ Good - explicit type
variable "count" {
  type = number
}

# ❌ Bad - no type (can cause issues)
variable "count" {}
```

#### 3. Use Validation
```hcl
# ✅ Good - validates input
variable "environment" {
  type = string
  
  validation {
    condition     = contains(["dev", "prod"], var.environment)
    error_message = "Must be dev or prod."
  }
}
```

#### 4. Don't Store Secrets in Defaults
```hcl
# ❌ Bad - secret in code
variable "db_password" {
  default = "supersecret123"
}

# ✅ Good - no default, mark sensitive
variable "db_password" {
  type      = string
  sensitive = true
}
```

#### 5. Organize Variables
```hcl
# variables.tf structure
# 1. General variables
variable "region" { }
variable "environment" { }

# 2. Network variables
variable "vpc_cidr" { }
variable "subnets" { }

# 3. Compute variables
variable "instance_type" { }
variable "instance_count" { }

# 4. Application variables
variable "app_name" { }
variable "app_version" { }
```

### Common Mistakes

#### Mistake 1: Wrong Type
```hcl
variable "count" {
  type    = string  # ❌ Should be number
  default = "3"
}

# Fix
variable "count" {
  type    = number
  default = 3
}
```

#### Mistake 2: Forgetting Quotes
```hcl
# ❌ Wrong
terraform apply -var=region=us-west-2

# ✅ Correct
terraform apply -var="region=us-west-2"
```

#### Mistake 3: Not Using .gitignore
```bash
# ❌ Bad - commits secrets
git add terraform.tfvars

# ✅ Good - add to .gitignore
echo "*.tfvars" >> .gitignore
echo "terraform.tfvars" >> .gitignore
```

### Key Takeaways

📌 **Remember:**
- Variables make code reusable
- Define in `variables.tf`
- Provide values via tfvars, CLI, or env vars
- Always use validation for important variables
- Mark sensitive data with `sensitive = true`
- Never commit .tfvars files with secrets

---

## Section 9: Outputs and Data Sources

### What You'll Learn
- Output blocks and their uses
- Accessing outputs from other modules
- Data sources for fetching existing resources
- Combining outputs and data sources

### Understanding Outputs

**Outputs** display information about your infrastructure after applying.

### Why Use Outputs?

1. **Display important values** (IPs, URLs, IDs)
2. **Pass values between modules**
3. **Share information with other tools**
4. **Document what was created**

### Basic Output Syntax

```hcl
output "output_name" {
  value       = resource.type.name.attribute
  description = "What this output is"
  sensitive   = false  # Optional
}
```

### Simple Output Examples

```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
}

# Output instance IP
output "instance_public_ip" {
  value       = aws_instance.web.public_ip
  description = "Public IP of web server"
}

# Output instance ID
output "instance_id" {
  value       = aws_instance.web.id
  description = "Instance ID"
}

# Output instance DNS
output "instance_dns" {
  value       = aws_instance.web.public_dns
  description = "Public DNS name"
}
```

### After Applying

```bash
terraform apply

Outputs:

instance_public_ip = "54.123.45.67"
instance_id = "i-1234567890abcdef0"
instance_dns = "ec2-54-123-45-67.compute-1.amazonaws.com"
```

### View Outputs Anytime

```bash
# Show all outputs
terraform output

# Show specific output
terraform output instance_public_ip

# Output as JSON
terraform output -json

# Save to file
terraform output -json > outputs.json
```

### Advanced Output Examples

#### 1. List Output
```hcl
resource "aws_instance" "servers" {
  count         = 3
  ami           = "ami-12345"
  instance_type = "t2.micro"
}

output "all_instance_ips" {
  value       = aws_instance.servers[*].public_ip
  description = "All server IPs"
}
```

**Result:**
```
all_instance_ips = [
  "54.123.45.67",
  "54.123.45.68",
  "54.123.45.69"
]
```

#### 2. Map Output
```hcl
resource "aws_instance" "servers" {
  for_each = {
    web = "t2.micro"
    app = "t2.small"
    db  = "t2.medium"
  }
  
  ami           = "ami-12345"
  instance_type = each.value
  
  tags = {
    Name = each.key
  }
}

output "server_ips" {
  value = {
    for name, instance in aws_instance.servers :
    name => instance.public_ip
  }
}
```

**Result:**
```
server_ips = {
  "web" = "54.123.45.67"
  "app" = "54.123.45.68"
  "db"  = "54.123.45.69"
}
```

#### 3. Formatted Output
```hcl
output "ssh_connection" {
  value = "ssh -i mykey.pem ec2-user@${aws_instance.web.public_ip}"
  description = "SSH connection command"
}

output "web_url" {
  value = "http://${aws_instance.web.public_dns}"
  description = "Website URL"
}
```

**Result:**
```
ssh_connection = "ssh -i mykey.pem ec2-user@54.123.45.67"
web_url = "http://ec2-54-123-45-67.compute-1.amazonaws.com"
```

#### 4. Sensitive Output
```hcl
resource "random_password" "db_password" {
  length  = 32
  special = true
}

output "database_password" {
  value     = random_password.db_password.result
  sensitive = true
}
```

**Result:**
```
database_password = <sensitive>
```

### Understanding Data Sources

**Data sources** fetch information about existing resources.

### Why Use Data Sources?

1. **Reference existing infrastructure**
2. **Get dynamic values** (latest AMI)
3. **Work with resources created outside Terraform**
4. **Share data between projects**

### Data Source Syntax

```hcl
data "provider_type" "name" {
  # Query parameters
}

# Access with: data.provider_type.name.attribute
```

### Common Data Sources

#### 1. AWS AMI (Latest Amazon Linux)

```hcl
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
  
  filter {
    name   = "virtualization-type"
    values = ["hvm"]
  }
}

# Use in resource
resource "aws_instance" "web" {
  ami = data.aws_ami.amazon_linux.id  # Dynamic AMI!
  instance_type = "t2.micro"
}

# Output AMI info
output "ami_id" {
  value = data.aws_ami.amazon_linux.id
}

output "ami_name" {
  value = data.aws_ami.amazon_linux.name
}
```

#### 2. AWS VPC (Default VPC)

```hcl
data "aws_vpc" "default" {
  default = true
}

# Use in security group
resource "aws_security_group" "web_sg" {
  name   = "web-sg"
  vpc_id = data.aws_vpc.default.id  # Use existing VPC
}

output "vpc_id" {
  value = data.aws_vpc.default.id
}
```

#### 3. AWS Availability Zones

```hcl
data "aws_availability_zones" "available" {
  state = "available"
}

# Use in resource
resource "aws_subnet" "public" {
  count             = 3
  vpc_id            = aws_vpc.main.id
  cidr_block        = cidrsubnet(aws_vpc.main.cidr_block, 8, count.index)
  availability_zone = data.aws_availability_zones.available.names[count.index]
}

output "all_azs" {
  value = data.aws_availability_zones.available.names
}
```

#### 4. AWS Caller Identity (Who Am I?)

```hcl
data "aws_caller_identity" "current" {}

output "account_id" {
  value = data.aws_caller_identity.current.account_id
}

output "caller_arn" {
  value = data.aws_caller_identity.current.arn
}

output "caller_user" {
  value = data.aws_caller_identity.current.user_id
}
```

#### 5. AWS Region (Current Region)

```hcl
data "aws_region" "current" {}

output "current_region" {
  value = data.aws_region.current.name
}

# Use in tags
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Region = data.aws_region.current.name
  }
}
```

#### 6. Terraform Remote State

```hcl
# Read state from another project
data "terraform_remote_state" "vpc" {
  backend = "s3"
  
  config = {
    bucket = "my-terraform-state"
    key    = "vpc/terraform.tfstate"
    region = "us-east-2"
  }
}

# Use outputs from other project
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  subnet_id     = data.terraform_remote_state.vpc.outputs.public_subnet_id
}
```

### Combining Outputs and Data Sources

```hcl
# Get latest Ubuntu AMI
data "aws_ami" "ubuntu" {
  most_recent = true
  owners      = ["099720109477"]  # Canonical
  
  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-*"]
  }
}

# Get current region
data "aws_region" "current" {}

# Get default VPC
data "aws_vpc" "default" {
  default = true
}

# Create instance with data
resource "aws_instance" "web" {
  ami           = data.aws_ami.ubuntu.id
  instance_type = "t2.micro"
  
  tags = {
    Name   = "Ubuntu-Server"
    Region = data.aws_region.current.name
    VPC    = data.aws_vpc.default.id
  }
}

# Output everything
output "instance_info" {
  value = {
    instance_id   = aws_instance.web.id
    public_ip     = aws_instance.web.public_ip
    ami_used      = data.aws_ami.ubuntu.name
    region        = data.aws_region.current.name
    vpc           = data.aws_vpc.default.id
  }
}
```

### Module Outputs

**File: `modules/networking/outputs.tf`**
```hcl
output "vpc_id" {
  value       = aws_vpc.main.id
  description = "VPC ID"
}

output "public_subnet_ids" {
  value       = aws_subnet.public[*].id
  description = "Public subnet IDs"
}
```

**Using module outputs:**
```hcl
module "networking" {
  source = "./modules/networking"
}

# Access module outputs
resource "aws_instance" "web" {
  subnet_id = module.networking.public_subnet_ids[0]
}

output "vpc_from_module" {
  value = module.networking.vpc_id
}
```

### Exercise 9.1: Create Outputs

**Task:** Create outputs for:
1. EC2 instance public IP
2. SSH connection command
3. List of all security group IDs
4. Current AWS account ID

**Solution:**
```hcl
data "aws_caller_identity" "current" {}

resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  vpc_security_group_ids = [
    aws_security_group.web.id,
    aws_security_group.ssh.id
  ]
}

output "instance_ip" {
  value       = aws_instance.web.public_ip
  description = "Public IP address"
}

output "ssh_command" {
  value       = "ssh ec2-user@${aws_instance.web.public_ip}"
  description = "SSH connection command"
}

output "security_groups" {
  value       = aws_instance.web.vpc_security_group_ids
  description = "Security group IDs"
}

output "account_id" {
  value       = data.aws_caller_identity.current.account_id
  description = "AWS Account ID"
}
```

### Exercise 9.2: Use Data Sources

**Task:** Use data sources to:
1. Get latest Amazon Linux 2 AMI
2. Get current region
3. Use them in an EC2 instance
4. Output the AMI ID and region

**Solution:**
```hcl
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

data "aws_region" "current" {}

resource "aws_instance" "web" {
  ami           = data.aws_ami.amazon_linux.id
  instance_type = "t2.micro"
  
  tags = {
    Name   = "web-server"
    Region = data.aws_region.current.name
  }
}

output "ami_used" {
  value = data.aws_ami.amazon_linux.id
}

output "current_region" {
  value = data.aws_region.current.name
}
```

### Best Practices

#### 1. Always Add Descriptions
```hcl
# ✅ Good
output "instance_ip" {
  value       = aws_instance.web.public_ip
  description = "Public IP address of web server"
}

# ❌ Bad
output "ip" {
  value = aws_instance.web.public_ip
}
```

#### 2. Use Sensitive for Secrets
```hcl
output "database_password" {
  value     = aws_db_instance.main.password
  sensitive = true  # Hides from output
}
```

#### 3. Group Related Outputs
```hcl
output "connection_info" {
  value = {
    ip       = aws_instance.web.public_ip
    dns      = aws_instance.web.public_dns
    ssh_user = "ec2-user"
  }
}
```

#### 4. Use Data Sources for Dynamic Values
```hcl
# ✅ Good - always gets latest AMI
data "aws_ami" "latest" {
  most_recent = true
  # ...
}

# ❌ Bad - hardcoded, gets outdated
ami = "ami-12345"
```

### Common Patterns

#### Pattern 1: Connection String
```hcl
output "database_connection" {
  value = "postgresql://${aws_db_instance.main.username}:PASSWORD@${aws_db_instance.main.endpoint}/${aws_db_instance.main.db_name}"
}
```

#### Pattern 2: Module Chain
```hcl
# VPC module outputs
module "vpc" {
  source = "./modules/vpc"
}

# Use VPC outputs in compute module
module "compute" {
  source = "./modules/compute"
  
  vpc_id     = module.vpc.vpc_id
  subnet_ids = module.vpc.private_subnet_ids
}

# Final output
output "app_url" {
  value = "http://${module.compute.load_balancer_dns}"
}
```

### Key Takeaways

📌 **Remember:**
- Outputs display values after apply
- Data sources fetch existing resources
- Use `terraform output` to view outputs anytime
- Mark sensitive outputs with `sensitive = true`
- Data sources enable dynamic, up-to-date values
- Module outputs enable composition

**Common Commands:**
```bash
terraform output              # Show all
terraform output instance_ip  # Show specific
terraform output -json        # JSON format
```

---

## Section 10: String Interpolation and Functions

### What You'll Learn
- String interpolation syntax
- Built-in Terraform functions
- Common use cases for functions
- Function composition

### String Interpolation

**String interpolation** lets you embed expressions inside strings.

### Basic Syntax

```hcl
"Hello, ${expression}"
```

### Simple Examples

```hcl
variable "name" {
  default = "John"
}

variable "age" {
  default = 25
}

# Interpolation
output "greeting" {
  value = "Hello, ${var.name}!"
}

output "message" {
  value = "${var.name} is ${var.age} years old"
}

# Result:
# greeting = "Hello, John!"
# message = "John is 25 years old"
```

### In Resource Names

```hcl
variable "environment" {
  default = "prod"
}

variable "project" {
  default = "webapp"
}

resource "aws_instance" "server" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Name = "${var.project}-${var.environment}-server"
    # Result: "webapp-prod-server"
  }
}
```

### Terraform Functions

Terraform has **80+ built-in functions** in categories:
- Numeric functions
- String functions
- Collection functions
- Encoding functions
- Filesystem functions
- Date/Time functions
- Hash/Crypto functions
- IP Network functions
- Type Conversion functions

### Testing Functions in Console

```bash
terraform console

> upper("hello")
"HELLO"

> length([1, 2, 3])
3

> max(5, 12, 9)
12
```

### 1. String Functions

#### upper() / lower()
```hcl
variable "env" {
  default = "Production"
}

resource "aws_instance" "server" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Environment = upper(var.env)  # "PRODUCTION"
    Name        = lower("MyServer")  # "myserver"
  }
}
```

#### title() / replace()
```hcl
output "formatted_name" {
  value = title("hello world")  # "Hello World"
}

output "sanitized" {
  value = replace("my_bucket_name", "_", "-")  # "my-bucket-name"
}
```

#### trim() / trimprefix() / trimsuffix()
```hcl
variable "bucket_name" {
  default = "  my-bucket  "
}

output "clean_name" {
  value = trim(var.bucket_name, " ")  # "my-bucket"
}

output "without_prefix" {
  value = trimprefix("aws-my-bucket", "aws-")  # "my-bucket"
}

output "without_suffix" {
  value = trimsuffix("my-bucket-prod", "-prod")  # "my-bucket"
}
```

#### split() / join()
```hcl
variable "az_string" {
  default = "us-east-2a,us-east-2b,us-east-2c"
}

locals {
  # Split string into list
  az_list = split(",", var.az_string)
  # ["us-east-2a", "us-east-2b", "us-east-2c"]
  
  # Join list into string
  az_joined = join(", ", local.az_list)
  # "us-east-2a, us-east-2b, us-east-2c"
}
```

#### substr()
```hcl
variable "long_string" {
  default = "Hello, World!"
}

output "substring" {
  value = substr(var.long_string, 0, 5)  # "Hello"
}

output "from_position" {
  value = substr(var.long_string, 7, 5)  # "World"
}
```

#### format() / formatlist()
```hcl
variable "counter" {
  default = 5
}

output "formatted" {
  value = format("Server-%03d", var.counter)  # "Server-005"
}

locals {
  numbers = [1, 2, 3]
}

output "server_names" {
  value = formatlist("server-%02d", local.numbers)
  # ["server-01", "server-02", "server-03"]
}
```

### 2. Numeric Functions

#### min() / max()
```hcl
output "minimum" {
  value = min(5, 12, 9, 3)  # 3
}

output "maximum" {
  value = max(5, 12, 9, 3)  # 12
}
```

#### ceil() / floor()
```hcl
output "ceiling" {
  value = ceil(4.3)  # 5
}

output "floor" {
  value = floor(4.9)  # 4
}
```

#### abs() / pow()
```hcl
output "absolute" {
  value = abs(-15)  # 15
}

output "power" {
  value = pow(2, 3)  # 8
}
```

### 3. Collection Functions

#### length()
```hcl
locals {
  my_list = ["a", "b", "c"]
  my_map  = { name = "John", age = 30 }
}

output "list_length" {
  value = length(local.my_list)  # 3
}

output "map_length" {
  value = length(local.my_map)  # 2
}
```

#### contains()
```hcl
locals {
  allowed_types = ["t2.micro", "t2.small", "t2.medium"]
}

variable "instance_type" {
  type    = string
  default = "t2.micro"
  
  validation {
    condition     = contains(local.allowed_types, var.instance_type)
    error_message = "Invalid instance type!"
  }
}
```

#### element()
```hcl
locals {
  azs = ["us-east-2a", "us-east-2b", "us-east-2c"]
}

resource "aws_subnet" "example" {
  count             = 5
  availability_zone = element(local.azs, count.index)
  # Wraps around: [0]=a, [1]=b, [2]=c, [3]=a, [4]=b
}
```

#### concat()
```hcl
locals {
  list1 = ["a", "b"]
  list2 = ["c", "d"]
  
  combined = concat(list1, list2)  # ["a", "b", "c", "d"]
}
```

#### merge()
```hcl
locals {
  default_tags = {
    ManagedBy = "Terraform"
    Project   = "MyApp"
  }
  
  custom_tags = {
    Environment = "prod"
    Owner       = "DevOps"
  }
  
  all_tags = merge(local.default_tags, local.custom_tags)
  # {
  #   ManagedBy   = "Terraform"
  #   Project     = "MyApp"
  #   Environment = "prod"
  #   Owner       = "DevOps"
  # }
}

resource "aws_instance" "server" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = merge(
    local.default_tags,
    { Name = "web-server" }
  )
}
```

#### keys() / values()
```hcl
locals {
  instance_types = {
    dev  = "t2.micro"
    prod = "t2.large"
  }
}

output "environments" {
  value = keys(local.instance_types)  # ["dev", "prod"]
}

output "types" {
  value = values(local.instance_types)  # ["t2.micro", "t2.large"]
}
```

#### lookup()
```hcl
locals {
  instance_types = {
    dev     = "t2.micro"
    staging = "t2.small"
    prod    = "t2.large"
  }
}

variable "environment" {
  default = "dev"
}

resource "aws_instance" "server" {
  ami           = "ami-12345"
  instance_type = lookup(local.instance_types, var.environment, "t2.micro")
  # If environment not found, use "t2.micro" as default
}
```

#### flatten()
```hcl
locals {
  nested = [
    ["a", "b"],
    ["c", "d"],
    ["e"]
  ]
  
  flat = flatten(local.nested)  # ["a", "b", "c", "d", "e"]
}
```

#### distinct()
```hcl
locals {
  with_duplicates = ["a", "b", "a", "c", "b"]
  
  unique = distinct(local.with_duplicates)  # ["a", "b", "c"]
}
```

#### slice()
```hcl
locals {
  full_list = ["a", "b", "c", "d", "e"]
  
  subset = slice(local.full_list, 1, 4)  # ["b", "c", "d"]
  # Start at index 1, end before index 4
}
```

### 4. IP Network Functions

#### cidrsubnet()
```hcl
# Divide VPC CIDR into subnets
locals {
  vpc_cidr = "10.0.0.0/16"
}

resource "aws_subnet" "public" {
  count      = 3
  vpc_id     = aws_vpc.main.id
  cidr_block = cidrsubnet(local.vpc_cidr, 8, count.index)
  # cidrsubnet(prefix, newbits, netnum)
  # Results:
  # [0] = "10.0.0.0/24"
  # [1] = "10.0.1.0/24"
  # [2] = "10.0.2.0/24"
}
```

#### cidrhost()
```hcl
locals {
  subnet_cidr = "10.0.1.0/24"
}

output "first_ip" {
  value = cidrhost(local.subnet_cidr, 0)  # "10.0.1.0"
}

output "tenth_ip" {
  value = cidrhost(local.subnet_cidr, 10)  # "10.0.1.10"
}
```

### 5. Filesystem Functions

#### file()
```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  user_data     = file("${path.module}/scripts/init.sh")
}
```

#### templatefile()
```hcl
# File: templates/user_data.tpl
#  #!/bin/bash
#  echo "Environment: ${environment}"
#  echo "App Name: ${app_name}"

resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  user_data = templatefile("${path.module}/templates/user_data.tpl", {
    environment = var.environment
    app_name    = var.app_name
  })
}
```

#### path variables
```hcl
output "module_path" {
  value = path.module  # Current module path
}

output "root_path" {
  value = path.root  # Root module path
}

output "current_path" {
  value = path.cwd  # Current working directory
}
```

### 6. Date/Time Functions

#### timestamp()
```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    CreatedAt = timestamp()  # "2024-01-15T10:30:00Z"
  }
}
```

#### formatdate()
```hcl
output "formatted_time" {
  value = formatdate("DD MMM YYYY hh:mm ZZZ", timestamp())
  # "15 Jan 2024 10:30 UTC"
}
```

### 7. Type Conversion Functions

#### tostring() / tonumber() / tobool()
```hcl
locals {
  string_num = "42"
  number     = tonumber(local.string_num)  # 42
  
  bool_string = "true"
  boolean     = tobool(local.bool_string)  # true
  
  num         = 100
  string      = tostring(local.num)  # "100"
}
```

#### tolist() / toset() / tomap()
```hcl
locals {
  tuple_var = ["a", "b", "c"]
  list_var  = tolist(local.tuple_var)
  
  with_dupes = ["a", "b", "a", "c"]
  unique_set = toset(local.with_dupes)  # Set removes duplicates
}
```

### 8. Encoding Functions

#### jsonencode() / jsondecode()
```hcl
locals {
  policy = {
    Version = "2012-10-17"
    Statement = [{
      Effect   = "Allow"
      Action   = "s3:*"
      Resource = "*"
    }]
  }
  
  policy_json = jsonencode(local.policy)
}

resource "aws_iam_policy" "policy" {
  name   = "my-policy"
  policy = local.policy_json
}
```

#### base64encode() / base64decode()
```hcl
locals {
  original = "Hello, World!"
  encoded  = base64encode(local.original)  # "SGVsbG8sIFdvcmxkIQ=="
  decoded  = base64decode(local.encoded)   # "Hello, World!"
}
```

### 9. Hash/Crypto Functions

#### md5() / sha256()
```hcl
locals {
  content = "Important data"
  
  md5_hash    = md5(local.content)
  sha256_hash = sha256(local.content)
}

# Trigger replacement when file changes
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    ConfigHash = md5(file("${path.module}/config/app.conf"))
  }
}
```

### Practical Function Combinations

#### Example 1: Dynamic Tags
```hcl
locals {
  default_tags = {
    ManagedBy   = "Terraform"
    Environment = var.environment
    CreatedAt   = formatdate("YYYY-MM-DD", timestamp())
  }
}

resource "aws_instance" "servers" {
  for_each = toset(["web", "app", "db"])
  
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = merge(
    local.default_tags,
    {
      Name = "${var.project}-${each.key}-${var.environment}"
      Role = upper(each.key)
    }
  )
}
```

#### Example 2: Dynamic Subnets
```hcl
locals {
  vpc_cidr = "10.0.0.0/16"
  azs      = ["us-east-2a", "us-east-2b", "us-east-2c"]
}

resource "aws_subnet" "private" {
  count             = length(local.azs)
  vpc_id            = aws_vpc.main.id
  cidr_block        = cidrsubnet(local.vpc_cidr, 8, count.index)
  availability_zone = element(local.azs, count.index)
  
  tags = {
    Name = format("private-subnet-%02d", count.index + 1)
    # "private-subnet-01", "private-subnet-02", ...
  }
}
```

#### Example 3: Conditional Resource Creation
```hcl
variable "create_database" {
  type    = bool
  default = true
}

resource "aws_db_instance" "main" {
  count = var.create_database ? 1 : 0
  
  identifier     = "${var.project}-db"
  engine         = "postgres"
  instance_class = "db.t3.micro"
}

output "database_endpoint" {
  value = var.create_database ? aws_db_instance.main[0].endpoint : "No database created"
}
```

### Exercise 10.1: String Manipulation

**Task:** Create variables and use functions to:
1. Convert project name to uppercase
2. Replace underscores with hyphens in bucket name
3. Create a formatted server name with environment

**Solution:**
```hcl
variable "project_name" {
  default = "my_webapp"
}

variable "environment" {
  default = "production"
}

locals {
  uppercase_project = upper(var.project_name)
  bucket_name       = replace(var.project_name, "_", "-")
  server_name       = "${local.bucket_name}-${lower(var.environment)}-server"
}

output "results" {
  value = {
    uppercase = local.uppercase_project      # "MY_WEBAPP"
    bucket    = local.bucket_name            # "my-webapp"
    server    = local.server_name            # "my-webapp-production-server"
  }
}
```

### Exercise 10.2: Working with Lists

**Task:** Given a list of availability zones, create:
1. Count of zones
2. First and last zone
3. Subnets using cidrsubnet

**Solution:**
```hcl
locals {
  vpc_cidr = "10.0.0.0/16"
  azs      = ["us-east-2a", "us-east-2b", "us-east-2c"]
  
  zone_count = length(local.azs)
  first_zone = local.azs[0]
  last_zone  = local.azs[length(local.azs) - 1]
}

resource "aws_subnet" "subnets" {
  count             = local.zone_count
  vpc_id            = aws_vpc.main.id
  cidr_block        = cidrsubnet(local.vpc_cidr, 8, count.index)
  availability_zone = local.azs[count.index]
  
  tags = {
    Name = format("subnet-%s", local.azs[count.index])
  }
}

output "subnet_info" {
  value = {
    count      = local.zone_count
    first_zone = local.first_zone
    last_zone  = local.last_zone
  }
}
```

### Common Function Patterns

#### Pattern 1: Name Normalization
```hcl
locals {
  raw_name = "My_Resource Name!"
  
  # Clean and normalize
  clean_name = lower(replace(replace(local.raw_name, " ", "-"), "!", ""))
  # "my_resource-name"
}
```

#### Pattern 2: Conditional Values
```hcl
variable "environment" {
  default = "prod"
}

locals {
  instance_type = var.environment == "prod" ? "t2.large" : "t2.micro"
  backup_count  = var.environment == "prod" ? 7 : 1
}
```

#### Pattern 3: Dynamic Port Rules
```hcl
locals {
  allowed_ports = [22, 80, 443]
}

resource "aws_security_group_rule" "ingress" {
  count = length(local.allowed_ports)
  
  type        = "ingress"
  from_port   = local.allowed_ports[count.index]
  to_port     = local.allowed_ports[count.index]
  protocol    = "tcp"
  cidr_blocks = ["0.0.0.0/0"]
  
  security_group_id = aws_security_group.main.id
}
```

### Best Practices

#### 1. Use Locals for Complex Expressions
```hcl
# ✅ Good
locals {
  server_name = "${var.project}-${var.environment}-server"
}

resource "aws_instance" "web" {
  tags = {
    Name = local.server_name
  }
}

# ❌ Bad - repeated complex expression
resource "aws_instance" "web" {
  tags = {
    Name = "${var.project}-${var.environment}-server"
  }
}
```

#### 2. Use Type Conversion Explicitly
```hcl
# ✅ Good
variable "count_string" {
  default = "3"
}

resource "aws_instance" "servers" {
  count = tonumber(var.count_string)
}
```

#### 3. Validate with Functions
```hcl
variable "environment" {
  type = string
  
  validation {
    condition     = contains(["dev", "staging", "prod"], var.environment)
    error_message = "Environment must be dev, staging, or prod."
  }
}
```

### Key Takeaways

📌 **Remember:**
- Use `${}` for interpolation
- Test functions in `terraform console`
- Use locals for complex calculations
- Combine functions for powerful transformations
- Functions are pure (no side effects)
- Use `format()` for consistent naming

**Most Used Functions:**
```hcl
format()      # String formatting
lookup()      # Map lookup with default
merge()       # Merge maps
concat()      # Combine lists
cidrsubnet()  # Calculate subnets
element()     # Safe list access
length()      # Count items
contains()    # Check membership
```

---

**🎉 Congratulations!** You've completed Part 2: Core Concepts!

You now understand:
- ✅ HCL language fundamentals
- ✅ Providers and their configuration
- ✅ Variables and their types
- ✅ Outputs and data sources
- ✅ String interpolation and functions

---

# Part 3: AWS Basics

Now let's apply what you've learned to real AWS resources!

---

## Section 11: AWS Setup and Configuration

### What You'll Learn
- AWS account setup
- IAM user creation
- Access keys and credentials
- AWS CLI configuration
- Terraform AWS provider setup

### Prerequisites

You need an **AWS account**. If you don't have one:

1. Go to [aws.amazon.com](https://aws.amazon.com)
2. Click "Create an AWS Account"
3. Follow the signup process
4. **Note:** You'll need a credit card, but we'll use Free Tier services

### AWS Free Tier

AWS offers a **Free Tier** that includes:
- 750 hours/month of t2.micro EC2 instances (12 months)
- 5 GB of S3 storage (12 months)
- 25 GB of DynamoDB storage (always free)
- 1 million Lambda requests/month (always free)

### Step 1: Create IAM User

**Why not use root account?**
- Root account has unlimited access (dangerous)
- Can't be restricted
- If compromised, entire account at risk

**Create IAM user instead:**

1. **Log in to AWS Console**
   - Go to console.aws.amazon.com
   - Sign in with root account

2. **Navigate to IAM**
   - Search for "IAM" in services
   - Click "IAM"

3. **Create User**
   ```
   IAM Dashboard → Users → Add users
   
   User name: terraform-user
   
   ✅ Access key - Programmatic access
   ❌ Password - AWS Management Console access (optional)
   ```

4. **Set Permissions**
   ```
   Method 1: Attach existing policies directly
   Search and select: AdministratorAccess
   
   (For production, use more restricted permissions)
   ```

5. **Review and Create**
   ```
   Review settings
   Click: Create user
   ```

6. **Download Credentials**
   ```
   ⚠️ IMPORTANT: This is your only chance!
   
   Download .csv file containing:
   - Access Key ID
   - Secret Access Key
   
   Store securely!
   ```

### Step 2: Install AWS CLI

#### Linux
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

# Verify
aws --version
```

#### macOS
```bash
# Using Homebrew
brew install awscli

# Or download installer
curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
sudo installer -pkg AWSCLIV2.pkg -target /

# Verify
aws --version
```

#### Windows
```powershell
# Download and run installer from:
# https://awscli.amazonaws.com/AWSCLIV2.msi

# Verify in Command Prompt
aws --version
```

### Step 3: Configure AWS CLI

```bash
aws configure
```

**Prompts:**
```
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-east-2
Default output format [None]: json
```

**This creates two files:**

**~/.aws/credentials** (Linux/Mac) or **%USERPROFILE%\.aws\credentials** (Windows)
```ini
[default]
aws_access_key_id = AKIAIOSFODNN7EXAMPLE
aws_secret_access_key = wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
```

**~/.aws/config**
```ini
[default]
region = us-east-2
output = json
```

### Step 4: Verify AWS Access

```bash
# Get caller identity
aws sts get-caller-identity
```

**Output:**
```json
{
    "UserId": "AIDAI...",
    "Account": "123456789012",
    "Arn": "arn:aws:iam::123456789012:user/terraform-user"
}
```

```bash
# List S3 buckets (should work even if empty)
aws s3 ls

# List EC2 instances
aws ec2 describe-instances --region us-east-2
```

### Step 5: Terraform AWS Provider Setup

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
  
  # Optional: use specific profile
  # profile = "terraform-user"
  
  # Optional: add default tags to all resources
  default_tags {
    tags = {
      ManagedBy = "Terraform"
      Project   = "LearningTerraform"
    }
  }
}
```

### Provider Authentication Methods

#### Method 1: AWS CLI Credentials (Recommended for Learning)
```hcl
provider "aws" {
  region = "us-east-2"
  # Automatically uses ~/.aws/credentials
}
```

#### Method 2: Named Profile
```hcl
provider "aws" {
  region  = "us-east-2"
  profile = "terraform-user"
}
```

**~/.aws/credentials:**
```ini
[default]
aws_access_key_id = KEY1
aws_secret_access_key = SECRET1

[terraform-user]
aws_access_key_id = KEY2
aws_secret_access_key = SECRET2
```

#### Method 3: Environment Variables
```bash
export AWS_ACCESS_KEY_ID="AKIAIOSFODNN7EXAMPLE"
export AWS_SECRET_ACCESS_KEY="wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY"
export AWS_DEFAULT_REGION="us-east-2"

terraform apply
```

#### Method 4: Hard-coded (❌ NOT RECOMMENDED)
```hcl
provider "aws" {
  region     = "us-east-2"
  access_key = "AKIAIOSFODNN7EXAMPLE"  # ❌ Never do this!
  secret_key = "wJalrXUtnFEMI/K7MD..."  # ❌ Never commit secrets!
}
```

### Testing Provider Connection

**File: `main.tf`**
```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

# Get current AWS account info
data "aws_caller_identity" "current" {}

data "aws_region" "current" {}

# Output the information
output "account_id" {
  value = data.aws_caller_identity.current.account_id
}

output "caller_arn" {
  value = data.aws_caller_identity.current.arn
}

output "region" {
  value = data.aws_region.current.name
}
```

**Run it:**
```bash
terraform init
terraform plan
terraform apply
```

**Output:**
```
account_id = "123456789012"
caller_arn = "arn:aws:iam::123456789012:user/terraform-user"
region = "us-east-2"
```

### Multiple AWS Regions

```hcl
provider "aws" {
  alias  = "us_east"
  region = "us-east-1"
}

provider "aws" {
  alias  = "us_west"
  region = "us-west-2"
}

# Use specific provider
resource "aws_s3_bucket" "east_bucket" {
  provider = aws.us_east
  bucket   = "my-east-bucket"
}

resource "aws_s3_bucket" "west_bucket" {
  provider = aws.us_west
  bucket   = "my-west-bucket"
}
```

### AWS Regions and Availability Zones

**AWS Regions:**
- us-east-1 (N. Virginia)
- us-east-2 (Ohio)
- us-west-1 (N. California)
- us-west-2 (Oregon)
- eu-west-1 (Ireland)
- ap-south-1 (Mumbai)
- And many more...

**Get available regions:**
```hcl
data "aws_regions" "available" {}

output "all_regions" {
  value = data.aws_regions.available.names
}
```

**Get availability zones:**
```hcl
data "aws_availability_zones" "available" {
  state = "available"
}

output "azs" {
  value = data.aws_availability_zones.available.names
  # ["us-east-2a", "us-east-2b", "us-east-2c"]
}
```

### Exercise 11.1: AWS Setup

**Task:**
1. Create IAM user with programmatic access
2. Configure AWS CLI
3. Create Terraform configuration with AWS provider
4. Get and output your account ID and region

**Solution:**
```hcl
# main.tf
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

data "aws_caller_identity" "current" {}
data "aws_region" "current" {}
data "aws_availability_zones" "available" {}

output "my_account_id" {
  value = data.aws_caller_identity.current.account_id
}

output "my_region" {
  value = data.aws_region.current.name
}

output "available_azs" {
  value = data.aws_availability_zones.available.names
}
```

### Security Best Practices

#### 1. Use IAM Users, Not Root
```
✅ Create IAM user for Terraform
❌ Never use root account credentials
```

#### 2. Use Least Privilege
```hcl
# ❌ Bad - too permissive
Permission: AdministratorAccess

# ✅ Better - specific permissions
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": [
      "ec2:*",
      "s3:*",
      "iam:GetRole"
    ],
    "Resource": "*"
  }]
}
```

#### 3. Never Commit Credentials
```bash
# .gitignore
*.tfvars
.terraform/
terraform.tfstate*
.env
*.pem
*.key
```

#### 4. Rotate Access Keys
```bash
# Every 90 days
aws iam create-access-key --user-name terraform-user
aws configure  # Update with new key
aws iam delete-access-key --access-key-id OLD_KEY --user-name terraform-user
```

#### 5. Enable MFA
```
For IAM user:
IAM → Users → terraform-user → Security credentials → Enable MFA
```

### Troubleshooting

#### Error: "Unable to locate credentials"
```bash
# Check AWS CLI configuration
aws configure list

# Verify credentials file
cat ~/.aws/credentials  # Linux/Mac
type %USERPROFILE%\.aws\credentials  # Windows

# Test AWS access
aws sts get-caller-identity
```

#### Error: "AuthFailure"
```bash
# Access key might be wrong
aws configure

# Or credentials expired
# Create new access key in IAM console
```

#### Error: "Region not specified"
```hcl
# Add region to provider
provider "aws" {
  region = "us-east-2"
}
```

### Key Takeaways

📌 **Remember:**
- Create IAM user for Terraform (not root)
- Use AWS CLI for local development
- Configure credentials in ~/.aws/credentials
- Never hardcode credentials in Terraform files
- Use Free Tier for learning
- Choose a region close to you

**Your setup should have:**
- ✅ AWS account
- ✅ IAM user with programmatic access
- ✅ AWS CLI installed and configured
- ✅ Terraform with AWS provider configured
- ✅ Test connection successful

---

## Section 12: Creating Your First EC2 Instance

### What You'll Learn
- EC2 basics and instance types
- Creating an EC2 instance with Terraform
- SSH key pairs
- Connecting to your instance
- User data scripts

### What is EC2?

**EC2 (Elastic Compute Cloud)** = Virtual servers in AWS cloud

**Think of it as:**
- Renting a computer in AWS data center
- You choose size (CPU, RAM, storage)
- You control OS and software
- Pay only for what you use

### EC2 Instance Types

```
Format: [Family][Generation].[Size]

Example: t2.micro
- t = Family (general purpose)
- 2 = Generation
- micro = Size
```

**Common Free Tier Instance:**
- `t2.micro`: 1 vCPU, 1 GB RAM (750 hours/month free)

### Step 1: Find an AMI

**AMI (Amazon Machine Image)** = Operating system template

```hcl
# Get latest Amazon Linux 2 AMI
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

output "ami_id" {
  value = data.aws_ami.amazon_linux.id
}
```

### Step 2: Create SSH Key Pair

**For Linux/Mac:**
```bash
ssh-keygen -t rsa -b 2048 -f ~/.ssh/terraform-key

# Two files created:
# terraform-key      (private key - keep secret!)
# terraform-key.pub  (public key - can share)
```

**For Windows (PowerShell):**
```powershell
ssh-keygen -t rsa -b 2048 -f $env:USERPROFILE\.ssh\terraform-key
```

### Step 3: Create AWS Key Pair Resource

```hcl
# Import public key to AWS
resource "aws_key_pair" "terraform_key" {
  key_name   = "terraform-key"
  public_key = file("~/.ssh/terraform-key.pub")
}
```

### Step 4: Create EC2 Instance

**File: `main.tf`**
```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

# Get latest Amazon Linux 2 AMI
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

# Create key pair
resource "aws_key_pair" "terraform_key" {
  key_name   = "terraform-key"
  public_key = file("~/.ssh/terraform-key.pub")
}

# Create EC2 instance
resource "aws_instance" "web_server" {
  ami           = data.aws_ami.amazon_linux.id
  instance_type = "t2.micro"
  key_name      = aws_key_pair.terraform_key.key_name
  
  tags = {
    Name = "MyFirstServer"
  }
}

# Output instance information
output "instance_id" {
  value = aws_instance.web_server.id
}

output "instance_public_ip" {
  value = aws_instance.web_server.public_ip
}

output "instance_public_dns" {
  value = aws_instance.web_server.public_dns
}
```

### Step 5: Apply Configuration

```bash
# Initialize
terraform init

# Plan
terraform plan

# Apply
terraform apply

# Output will show:
# instance_id = "i-1234567890abcdef0"
# instance_public_ip = "18.191.12.34"
# instance_public_dns = "ec2-18-191-12-34.us-east-2.compute.amazonaws.com"
```

### Step 6: Connect to Instance

**Linux/Mac:**
```bash
# Get public IP from output
terraform output instance_public_ip

# SSH into instance
chmod 400 ~/.ssh/terraform-key
ssh -i ~/.ssh/terraform-key ec2-user@18.191.12.34
```

**Windows (PowerShell):**
```powershell
# Set permissions
icacls $env:USERPROFILE\.ssh\terraform-key /inheritance:r
icacls $env:USERPROFILE\.ssh\terraform-key /grant:r "$($env:USERNAME):(R)"

# Connect
ssh -i $env:USERPROFILE\.ssh\terraform-key ec2-user@18.191.12.34
```

### Adding User Data

**User data** = Script that runs when instance starts

```hcl
resource "aws_instance" "web_server" {
  ami           = data.aws_ami.amazon_linux.id
  instance_type = "t2.micro"
  key_name      = aws_key_pair.terraform_key.key_name
  
  user_data = <<-EOF
              #!/bin/bash
              yum update -y
              yum install -y httpd
              systemctl start httpd
              systemctl enable httpd
              echo "<h1>Hello from Terraform!</h1>" > /var/www/html/index.html
              EOF
  
  tags = {
    Name = "WebServer"
  }
}
```

### Security Group for HTTP Access

```hcl
# Create security group
resource "aws_security_group" "web_sg" {
  name        = "web-security-group"
  description = "Allow HTTP and SSH"
  
  # Allow HTTP from anywhere
  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  # Allow SSH from anywhere (restrict in production!)
  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  # Allow all outbound traffic
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  tags = {
    Name = "WebServerSG"
  }
}

# Attach security group to instance
resource "aws_instance" "web_server" {
  ami                    = data.aws_ami.amazon_linux.id
  instance_type          = "t2.micro"
  key_name               = aws_key_pair.terraform_key.key_name
  vpc_security_group_ids = [aws_security_group.web_sg.id]
  
  user_data = <<-EOF
              #!/bin/bash
              yum update -y
              yum install -y httpd
              systemctl start httpd
              systemctl enable httpd
              echo "<h1>Hello from Terraform!</h1>" > /var/www/html/index.html
              EOF
  
  tags = {
    Name = "WebServer"
  }
}

output "website_url" {
  value = "http://${aws_instance.web_server.public_dns}"
}
```

### Complete Example with Variables

**File: `variables.tf`**
```hcl
variable "region" {
  description = "AWS region"
  type        = string
  default     = "us-east-2"
}

variable "instance_type" {
  description = "EC2 instance type"
  type        = string
  default     = "t2.micro"
}

variable "key_name" {
  description = "SSH key name"
  type        = string
  default     = "terraform-key"
}
```

**File: `main.tf`**
```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = var.region
}

data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

resource "aws_security_group" "web_sg" {
  name        = "web-sg"
  description = "Allow HTTP and SSH"
  
  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

resource "aws_key_pair" "terraform_key" {
  key_name   = var.key_name
  public_key = file("~/.ssh/${var.key_name}.pub")
}

resource "aws_instance" "web_server" {
  ami                    = data.aws_ami.amazon_linux.id
  instance_type          = var.instance_type
  key_name               = aws_key_pair.terraform_key.key_name
  vpc_security_group_ids = [aws_security_group.web_sg.id]
  
  user_data = file("${path.module}/user_data.sh")
  
  tags = {
    Name = "TerraformWebServer"
  }
}
```

**File: `user_data.sh`**
```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd

cat <<HTML > /var/www/html/index.html
<!DOCTYPE html>
<html>
<head>
    <title>Terraform Server</title>
</head>
<body>
    <h1>Hello from Terraform!</h1>
    <p>This server was provisioned using Terraform</p>
    <p>Instance ID: $(ec2-metadata --instance-id | cut -d ' ' -f 2)</p>
</body>
</html>
HTML
```

**File: `outputs.tf`**
```hcl
output "instance_id" {
  description = "EC2 instance ID"
  value       = aws_instance.web_server.id
}

output "public_ip" {
  description = "Public IP address"
  value       = aws_instance.web_server.public_ip
}

output "website_url" {
  description = "Website URL"
  value       = "http://${aws_instance.web_server.public_dns}"
}

output "ssh_connection" {
  description = "SSH connection command"
  value       = "ssh -i ~/.ssh/${var.key_name} ec2-user@${aws_instance.web_server.public_ip}"
}
```

### Exercise 12.1: Create Web Server

**Task:** Create an EC2 instance that:
1. Runs Amazon Linux 2
2. Has SSH and HTTP access
3. Installs and starts Apache web server
4. Displays custom HTML page

**Solution:** (See complete example above)

### Cleanup

```bash
# Destroy all resources
terraform destroy

# Confirm with: yes
```

### EC2 Instance Attributes

```hcl
resource "aws_instance" "example" {
  # Required
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  # Networking
  subnet_id                   = aws_subnet.public.id
  vpc_security_group_ids      = [aws_security_group.web.id]
  associate_public_ip_address = true
  
  # Storage
  root_block_device {
    volume_size = 20
    volume_type = "gp3"
    encrypted   = true
  }
  
  ebs_block_device {
    device_name = "/dev/sdf"
    volume_size = 50
    volume_type = "gp3"
  }
  
  # Configuration
  key_name  = aws_key_pair.main.key_name
  user_data = file("user_data.sh")
  
  # IAM
  iam_instance_profile = aws_iam_instance_profile.ec2_profile.name
  
  # Behavior
  disable_api_termination = false
  monitoring              = true
  
  # Metadata options
  metadata_options {
    http_tokens   = "required"  # IMDSv2
    http_endpoint = "enabled"
  }
  
  # Tags
  tags = {
    Name = "MyInstance"
  }
  
  # Lifecycle
  lifecycle {
    create_before_destroy = true
  }
}
```

### Common Instance Types

```hcl
# Free Tier
t2.micro      # 1 vCPU, 1 GB RAM

# General Purpose
t3.small      # 2 vCPU, 2 GB RAM
t3.medium     # 2 vCPU, 4 GB RAM
t3.large      # 2 vCPU, 8 GB RAM

# Compute Optimized
c5.large      # 2 vCPU, 4 GB RAM

# Memory Optimized
r5.large      # 2 vCPU, 16 GB RAM

# Storage Optimized
i3.large      # 2 vCPU, 15.25 GB RAM
```

### Key Takeaways

📌 **Remember:**
- EC2 = Virtual servers in AWS
- AMI = Operating system template
- Security groups = Firewall rules
- User data = Initialization script
- t2.micro is Free Tier eligible
- Always use SSH key pairs for access
- Clean up resources to avoid charges

**Basic EC2 workflow:**
```bash
1. Create SSH key pair
2. Define security group
3. Choose AMI
4. Create EC2 instance
5. Connect via SSH
6. terraform destroy when done
```

---

## Section 13: Networking Basics - VPC and Security Groups

### What You'll Learn
- VPC (Virtual Private Cloud) concepts
- Subnets (public and private)
- Internet Gateway
- Security Groups vs NACLs
- Creating complete network infrastructure

### What is a VPC?

**VPC = Your own private network in AWS**

**Analogy:**
- AWS Region = City
- VPC = Your private building
- Subnets = Floors in the building
- Security Groups = Door locks
- Route Tables = Directions inside building

### VPC Components

```
VPC
├── Subnets (Public & Private)
├── Internet Gateway (for public internet access)
├── Route Tables (traffic directions)
├── Security Groups (instance-level firewall)
└── NACLs (subnet-level firewall)
```

### Default VPC vs Custom VPC

**Default VPC:**
- ✅ Created automatically
- ✅ Ready to use
- ✅ Good for learning
- ❌ Limited control
- ❌ Not for production

**Custom VPC:**
- ✅ Full control
- ✅ Better security
- ✅ Production ready
- ❌ More complex

### Creating a Custom VPC

#### Step 1: VPC

```hcl
resource "aws_vpc" "main" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  enable_dns_support   = true
  
  tags = {
    Name = "main-vpc"
  }
}
```

**CIDR Block Explained:**
- `10.0.0.0/16` = 65,536 IP addresses (10.0.0.0 to 10.0.255.255)
- `/16` = Network prefix (first 16 bits fixed)

#### Step 2: Internet Gateway

```hcl
resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id
  
  tags = {
    Name = "main-igw"
  }
}
```

#### Step 3: Public Subnets

```hcl
data "aws_availability_zones" "available" {
  state = "available"
}

resource "aws_subnet" "public" {
  count                   = 2
  vpc_id                  = aws_vpc.main.id
  cidr_block              = cidrsubnet(aws_vpc.main.cidr_block, 8, count.index)
  availability_zone       = data.aws_availability_zones.available.names[count.index]
  map_public_ip_on_launch = true
  
  tags = {
    Name = "public-subnet-${count.index + 1}"
    Type = "Public"
  }
}
```

#### Step 4: Route Table for Public Subnets

```hcl
resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id
  
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.main.id
  }
  
  tags = {
    Name = "public-rt"
  }
}

resource "aws_route_table_association" "public" {
  count          = length(aws_subnet.public)
  subnet_id      = aws_subnet.public[count.index].id
  route_table_id = aws_route_table.public.id
}
```

#### Step 5: Private Subnets

```hcl
resource "aws_subnet" "private" {
  count             = 2
  vpc_id            = aws_vpc.main.id
  cidr_block        = cidrsubnet(aws_vpc.main.cidr_block, 8, count.index + 10)
  availability_zone = data.aws_availability_zones.available.names[count.index]
  
  tags = {
    Name = "private-subnet-${count.index + 1}"
    Type = "Private"
  }
}
```

### Complete VPC Example

**File: `vpc.tf`**
```hcl
# VPC
resource "aws_vpc" "main" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  enable_dns_support   = true
  
  tags = {
    Name = "main-vpc"
  }
}

# Internet Gateway
resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id
  
  tags = {
    Name = "main-igw"
  }
}

# Public Subnets
resource "aws_subnet" "public" {
  count                   = 2
  vpc_id                  = aws_vpc.main.id
  cidr_block              = cidrsubnet(aws_vpc.main.cidr_block, 8, count.index)
  availability_zone       = data.aws_availability_zones.available.names[count.index]
  map_public_ip_on_launch = true
  
  tags = {
    Name = "public-subnet-${count.index + 1}"
  }
}

# Private Subnets
resource "aws_subnet" "private" {
  count             = 2
  vpc_id            = aws_vpc.main.id
  cidr_block        = cidrsubnet(aws_vpc.main.cidr_block, 8, count.index + 10)
  availability_zone = data.aws_availability_zones.available.names[count.index]
  
  tags = {
    Name = "private-subnet-${count.index + 1}"
  }
}

# Public Route Table
resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id
  
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.main.id
  }
  
  tags = {
    Name = "public-rt"
  }
}

# Associate Public Subnets with Public Route Table
resource "aws_route_table_association" "public" {
  count          = length(aws_subnet.public)
  subnet_id      = aws_subnet.public[count.index].id
  route_table_id = aws_route_table.public.id
}

# Private Route Table (no internet gateway)
resource "aws_route_table" "private" {
  vpc_id = aws_vpc.main.id
  
  tags = {
    Name = "private-rt"
  }
}

# Associate Private Subnets with Private Route Table
resource "aws_route_table_association" "private" {
  count          = length(aws_subnet.private)
  subnet_id      = aws_subnet.private[count.index].id
  route_table_id = aws_route_table.private.id
}
```

### Security Groups

**Security Group = Firewall for EC2 instances**

#### Web Server Security Group

```hcl
resource "aws_security_group" "web" {
  name        = "web-sg"
  description = "Security group for web servers"
  vpc_id      = aws_vpc.main.id
  
  # HTTP from anywhere
  ingress {
    description = "HTTP"
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  # HTTPS from anywhere
  ingress {
    description = "HTTPS"
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  # SSH from specific IP only
  ingress {
    description = "SSH"
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["YOUR_IP/32"]  # Replace with your IP
  }
  
  # All outbound traffic
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  tags = {
    Name = "web-sg"
  }
}
```

#### Database Security Group

```hcl
resource "aws_security_group" "database" {
  name        = "database-sg"
  description = "Security group for database"
  vpc_id      = aws_vpc.main.id
  
  # MySQL from web servers only
  ingress {
    description     = "MySQL"
    from_port       = 3306
    to_port         = 3306
    protocol        = "tcp"
    security_groups = [aws_security_group.web.id]
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  tags = {
    Name = "database-sg"
  }
}
```

### Security Group Rules as Separate Resources

```hcl
resource "aws_security_group" "web" {
  name        = "web-sg"
  description = "Web server security group"
  vpc_id      = aws_vpc.main.id
  
  tags = {
    Name = "web-sg"
  }
}

# HTTP rule
resource "aws_security_group_rule" "web_http" {
  type              = "ingress"
  from_port         = 80
  to_port           = 80
  protocol          = "tcp"
  cidr_blocks       = ["0.0.0.0/0"]
  security_group_id = aws_security_group.web.id
}

# HTTPS rule
resource "aws_security_group_rule" "web_https" {
  type              = "ingress"
  from_port         = 443
  to_port           = 443
  protocol          = "tcp"
  cidr_blocks       = ["0.0.0.0/0"]
  security_group_id = aws_security_group.web.id
}

# Egress rule
resource "aws_security_group_rule" "web_egress" {
  type              = "egress"
  from_port         = 0
  to_port           = 0
  protocol          = "-1"
  cidr_blocks       = ["0.0.0.0/0"]
  security_group_id = aws_security_group.web.id
}
```

### Dynamic Security Group Rules

```hcl
locals {
  ingress_rules = [
    { port = 80, description = "HTTP" },
    { port = 443, description = "HTTPS" },
    { port = 22, description = "SSH" }
  ]
}

resource "aws_security_group" "web" {
  name   = "web-sg"
  vpc_id = aws_vpc.main.id
  
  dynamic "ingress" {
    for_each = local.ingress_rules
    
    content {
      description = ingress.value.description
      from_port   = ingress.value.port
      to_port     = ingress.value.port
      protocol    = "tcp"
      cidr_blocks = ["0.0.0.0/0"]
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

### Complete Network + EC2 Example

```hcl
# main.tf
provider "aws" {
  region = "us-east-2"
}

data "aws_availability_zones" "available" {
  state = "available"
}

# VPC
resource "aws_vpc" "main" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  
  tags = {
    Name = "main-vpc"
  }
}

# Internet Gateway
resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id
}

# Public Subnet
resource "aws_subnet" "public" {
  vpc_id                  = aws_vpc.main.id
  cidr_block              = "10.0.1.0/24"
  availability_zone       = data.aws_availability_zones.available.names[0]
  map_public_ip_on_launch = true
  
  tags = {
    Name = "public-subnet"
  }
}

# Route Table
resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id
  
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.main.id
  }
}

resource "aws_route_table_association" "public" {
  subnet_id      = aws_subnet.public.id
  route_table_id = aws_route_table.public.id
}

# Security Group
resource "aws_security_group" "web" {
  name   = "web-sg"
  vpc_id = aws_vpc.main.id
  
  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

# EC2 Instance
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

resource "aws_instance" "web" {
  ami                    = data.aws_ami.amazon_linux.id
  instance_type          = "t2.micro"
  subnet_id              = aws_subnet.public.id
  vpc_security_group_ids = [aws_security_group.web.id]
  
  user_data = <<-EOF
              #!/bin/bash
              yum update -y
              yum install -y httpd
              systemctl start httpd
              echo "<h1>Hello from VPC!</h1>" > /var/www/html/index.html
              EOF
  
  tags = {
    Name = "web-server"
  }
}

output "instance_url" {
  value = "http://${aws_instance.web.public_ip}"
}
```

### Key Takeaways

📌 **Remember:**
- VPC = Your private network in AWS
- Public subnet = Has internet access via IGW
- Private subnet = No direct internet access
- Security Group = Instance firewall (stateful)
- CIDR /16 = 65,536 IPs, /24 = 256 IPs
- Always use specific CIDR blocks for SSH access

---

## Section 14: Storage with S3 Buckets

### What You'll Learn
- S3 basics and use cases
- Creating S3 buckets
- Bucket policies and ACLs
- Versioning and lifecycle rules
- Static website hosting

### What is S3?

**S3 (Simple Storage Service)** = Object storage in AWS cloud

**Think of it as:**
- Unlimited Google Drive
- Store any type of file
- Access from anywhere
- Pay for what you use

### S3 Concepts

- **Bucket** = Container (like a folder)
- **Object** = File stored in bucket
- **Key** = File name/path
- **Region** = Where bucket is located

### Creating an S3 Bucket

```hcl
resource "aws_s3_bucket" "my_bucket" {
  bucket = "my-unique-bucket-name-12345"
  
  tags = {
    Name = "My Bucket"
  }
}
```

**⚠️ Bucket names must be:**
- Globally unique across ALL AWS accounts
- 3-63 characters long
- Lowercase letters, numbers, hyphens only
- No underscores, no spaces

### Bucket Versioning

```hcl
resource "aws_s3_bucket" "my_bucket" {
  bucket = "my-versioned-bucket"
}

resource "aws_s3_bucket_versioning" "my_bucket" {
  bucket = aws_s3_bucket.my_bucket.id
  
  versioning_configuration {
    status = "Enabled"
  }
}
```

### Bucket Encryption

```hcl
resource "aws_s3_bucket_server_side_encryption_configuration" "my_bucket" {
  bucket = aws_s3_bucket.my_bucket.id
  
  rule {
    apply_server_side_encryption_by_default {
      sse_algorithm = "AES256"
    }
  }
}
```

### Block Public Access

```hcl
resource "aws_s3_bucket_public_access_block" "my_bucket" {
  bucket = aws_s3_bucket.my_bucket.id
  
  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}
```

### Bucket Policy

```hcl
resource "aws_s3_bucket_policy" "my_bucket" {
  bucket = aws_s3_bucket.my_bucket.id
  
  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Sid       = "PublicReadGetObject"
        Effect    = "Allow"
        Principal = "*"
        Action    = "s3:GetObject"
        Resource  = "${aws_s3_bucket.my_bucket.arn}/*"
      }
    ]
  })
}
```

### Static Website Hosting

```hcl
resource "aws_s3_bucket" "website" {
  bucket = "my-website-bucket-12345"
}

resource "aws_s3_bucket_website_configuration" "website" {
  bucket = aws_s3_bucket.website.id
  
  index_document {
    suffix = "index.html"
  }
  
  error_document {
    key = "error.html"
  }
}

resource "aws_s3_bucket_public_access_block" "website" {
  bucket = aws_s3_bucket.website.id
  
  block_public_acls       = false
  block_public_policy     = false
  ignore_public_acls      = false
  restrict_public_buckets = false
}

resource "aws_s3_bucket_policy" "website" {
  bucket = aws_s3_bucket.website.id
  
  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Sid       = "PublicReadGetObject"
        Effect    = "Allow"
        Principal = "*"
        Action    = "s3:GetObject"
        Resource  = "${aws_s3_bucket.website.arn}/*"
      }
    ]
  })
}

# Upload index.html
resource "aws_s3_object" "index" {
  bucket       = aws_s3_bucket.website.id
  key          = "index.html"
  content      = "<h1>Hello from S3!</h1>"
  content_type = "text/html"
}

output "website_url" {
  value = "http://${aws_s3_bucket_website_configuration.website.website_endpoint}"
}
```

### Uploading Files

```hcl
resource "aws_s3_object" "file" {
  bucket = aws_s3_bucket.my_bucket.id
  key    = "path/to/file.txt"
  source = "${path.module}/files/file.txt"
  etag   = filemd5("${path.module}/files/file.txt")
}
```

### Lifecycle Rules

```hcl
resource "aws_s3_bucket_lifecycle_configuration" "my_bucket" {
  bucket = aws_s3_bucket.my_bucket.id
  
  rule {
    id     = "archive-old-files"
    status = "Enabled"
    
    transition {
      days          = 30
      storage_class = "STANDARD_IA"
    }
    
    transition {
      days          = 90
      storage_class = "GLACIER"
    }
    
    expiration {
      days = 365
    }
  }
}
```

### Complete S3 Example

```hcl
# S3 bucket for storing application data
resource "aws_s3_bucket" "app_data" {
  bucket = "myapp-data-${random_id.bucket_suffix.hex}"
  
  tags = {
    Name        = "Application Data"
    Environment = "Production"
  }
}

# Generate random suffix for unique bucket name
resource "random_id" "bucket_suffix" {
  byte_length = 4
}

# Enable versioning
resource "aws_s3_bucket_versioning" "app_data" {
  bucket = aws_s3_bucket.app_data.id
  
  versioning_configuration {
    status = "Enabled"
  }
}

# Enable encryption
resource "aws_s3_bucket_server_side_encryption_configuration" "app_data" {
  bucket = aws_s3_bucket.app_data.id
  
  rule {
    apply_server_side_encryption_by_default {
      sse_algorithm = "AES256"
    }
  }
}

# Block all public access
resource "aws_s3_bucket_public_access_block" "app_data" {
  bucket = aws_s3_bucket.app_data.id
  
  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}

# Lifecycle rule
resource "aws_s3_bucket_lifecycle_configuration" "app_data" {
  bucket = aws_s3_bucket.app_data.id
  
  rule {
    id     = "cleanup-old-versions"
    status = "Enabled"
    
    noncurrent_version_expiration {
      noncurrent_days = 90
    }
  }
}

output "bucket_name" {
  value = aws_s3_bucket.app_data.id
}

output "bucket_arn" {
  value = aws_s3_bucket.app_data.arn
}
```

### Key Takeaways

📌 **Remember:**
- S3 = Object storage service
- Bucket names must be globally unique
- Use versioning to keep file history
- Always encrypt sensitive data
- Block public access by default
- Use lifecycle rules to save costs

---

## Section 15: Connecting Everything Together

### What You'll Learn
- Building complete infrastructure
- EC2 with custom VPC
- S3 integration with EC2
- IAM roles for EC2
- Complete project example

### Project: Web Application Infrastructure

**Architecture:**
```
Internet
    ↓
Internet Gateway
    ↓
Public Subnet
    ↓
EC2 Instance (Web Server)
    ↓
S3 Bucket (Static Assets)
```

### Complete Infrastructure Code

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = var.aws_region
  
  default_tags {
    tags = {
      Project   = var.project_name
      ManagedBy = "Terraform"
    }
  }
}

# Data Sources
data "aws_availability_zones" "available" {
  state = "available"
}

data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

# VPC
resource "aws_vpc" "main" {
  cidr_block           = var.vpc_cidr
  enable_dns_hostnames = true
  enable_dns_support   = true
  
  tags = {
    Name = "${var.project_name}-vpc"
  }
}

# Internet Gateway
resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id
  
  tags = {
    Name = "${var.project_name}-igw"
  }
}

# Public Subnet
resource "aws_subnet" "public" {
  vpc_id                  = aws_vpc.main.id
  cidr_block              = cidrsubnet(var.vpc_cidr, 8, 1)
  availability_zone       = data.aws_availability_zones.available.names[0]
  map_public_ip_on_launch = true
  
  tags = {
    Name = "${var.project_name}-public-subnet"
  }
}

# Route Table
resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id
  
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.main.id
  }
  
  tags = {
    Name = "${var.project_name}-public-rt"
  }
}

resource "aws_route_table_association" "public" {
  subnet_id      = aws_subnet.public.id
  route_table_id = aws_route_table.public.id
}

# Security Group
resource "aws_security_group" "web" {
  name        = "${var.project_name}-web-sg"
  description = "Security group for web server"
  vpc_id      = aws_vpc.main.id
  
  ingress {
    description = "HTTP"
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  ingress {
    description = "SSH"
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  tags = {
    Name = "${var.project_name}-web-sg"
  }
}

# IAM Role for EC2
resource "aws_iam_role" "ec2_role" {
  name = "${var.project_name}-ec2-role"
  
  assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Action = "sts:AssumeRole"
        Effect = "Allow"
        Principal = {
          Service = "ec2.amazonaws.com"
        }
      }
    ]
  })
}

# IAM Policy for S3 Access
resource "aws_iam_role_policy" "s3_access" {
  name = "${var.project_name}-s3-access"
  role = aws_iam_role.ec2_role.id
  
  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Effect = "Allow"
        Action = [
          "s3:GetObject",
          "s3:PutObject",
          "s3:ListBucket"
        ]
        Resource = [
          aws_s3_bucket.app_bucket.arn,
          "${aws_s3_bucket.app_bucket.arn}/*"
        ]
      }
    ]
  })
}

# IAM Instance Profile
resource "aws_iam_instance_profile" "ec2_profile" {
  name = "${var.project_name}-ec2-profile"
  role = aws_iam_role.ec2_role.name
}

# S3 Bucket
resource "aws_s3_bucket" "app_bucket" {
  bucket = "${var.project_name}-app-${random_id.bucket_suffix.hex}"
  
  tags = {
    Name = "${var.project_name}-bucket"
  }
}

resource "random_id" "bucket_suffix" {
  byte_length = 4
}

resource "aws_s3_bucket_versioning" "app_bucket" {
  bucket = aws_s3_bucket.app_bucket.id
  
  versioning_configuration {
    status = "Enabled"
  }
}

# EC2 Instance
resource "aws_instance" "web" {
  ami                    = data.aws_ami.amazon_linux.id
  instance_type          = var.instance_type
  subnet_id              = aws_subnet.public.id
  vpc_security_group_ids = [aws_security_group.web.id]
  iam_instance_profile   = aws_iam_instance_profile.ec2_profile.name
  
  user_data = templatefile("${path.module}/user_data.sh", {
    bucket_name = aws_s3_bucket.app_bucket.id
  })
  
  tags = {
    Name = "${var.project_name}-web-server"
  }
}
```

**File: `variables.tf`**
```hcl
variable "aws_region" {
  description = "AWS region"
  type        = string
  default     = "us-east-2"
}

variable "project_name" {
  description = "Project name"
  type        = string
  default     = "webapp"
}

variable "vpc_cidr" {
  description = "VPC CIDR block"
  type        = string
  default     = "10.0.0.0/16"
}

variable "instance_type" {
  description = "EC2 instance type"
  type        = string
  default     = "t2.micro"
}
```

**File: `outputs.tf`**
```hcl
output "vpc_id" {
  description = "VPC ID"
  value       = aws_vpc.main.id
}

output "instance_id" {
  description = "EC2 instance ID"
  value       = aws_instance.web.id
}

output "instance_public_ip" {
  description = "EC2 public IP"
  value       = aws_instance.web.public_ip
}

output "website_url" {
  description = "Website URL"
  value       = "http://${aws_instance.web.public_ip}"
}

output "bucket_name" {
  description = "S3 bucket name"
  value       = aws_s3_bucket.app_bucket.id
}

output "ssh_command" {
  description = "SSH command"
  value       = "ssh ec2-user@${aws_instance.web.public_ip}"
}
```

**File: `user_data.sh`**
```bash
#!/bin/bash
yum update -y
yum install -y httpd aws-cli

# Start Apache
systemctl start httpd
systemctl enable httpd

# Create index page
cat <<HTML > /var/www/html/index.html
<!DOCTYPE html>
<html>
<head>
    <title>Web Application</title>
</head>
<body>
    <h1>Welcome to Our Web Application!</h1>
    <p>Powered by Terraform</p>
    <p>S3 Bucket: ${bucket_name}</p>
    <p>Instance ID: $(ec2-metadata --instance-id | cut -d ' ' -f 2)</p>
</body>
</html>
HTML

# Test S3 access
echo "Testing S3 access..." > /tmp/test.txt
aws s3 cp /tmp/test.txt s3://${bucket_name}/test.txt
```

### Deploy the Infrastructure

```bash
# Initialize
terraform init

# Plan
terraform plan

# Apply
terraform apply

# Get outputs
terraform output

# Visit website
terraform output website_url
```

### Key Takeaways

📌 **Remember:**
- Always organize code into separate files
- Use variables for flexibility
- Create IAM roles for EC2 to access AWS services
- Use user data for instance initialization
- Output important values for easy access

---

**🎉 Congratulations!** You've completed Part 3: AWS Basics!

---

# Part 4: State Management

---

## Section 16: Understanding Terraform State

### What You'll Learn
- What is Terraform state
- Why state is important
- State file structure
- Local vs remote state
- State security considerations

### What is Terraform State?

**State file** = Terraform's memory of your infrastructure

**Analogy:**
- You build a house (infrastructure)
- State file = Blueprint that tracks what was built
- Terraform checks blueprint before making changes

### The State File

**File:** `terraform.tfstate`

```json
{
  "version": 4,
  "terraform_version": "1.5.0",
  "serial": 1,
  "lineage": "abc-123-def",
  "resources": [
    {
      "type": "aws_instance",
      "name": "web",
      "provider": "provider[\"registry.terraform.io/hashicorp/aws\"]",
      "instances": [
        {
          "attributes": {
            "id": "i-1234567890abcdef0",
            "ami": "ami-12345",
            "instance_type": "t2.micro",
            "public_ip": "54.123.45.67"
          }
        }
      ]
    }
  ]
}
```

### Why State is Important

1. **Mapping** - Links Terraform config to real resources
2. **Metadata** - Stores resource dependencies
3. **Performance** - Caches resource attributes
4. **Collaboration** - Shared state for teams

### State Workflow

```
terraform plan
    ↓
Read current state
    ↓
Compare with config
    ↓
Calculate changes
    ↓
terraform apply
    ↓
Update resources
    ↓
Update state file
```

### State File Contents

```hcl
# Your config
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
}

# State stores:
# - Real resource ID
# - All attributes
# - Dependencies
# - Provider config
```

### Local State

**Default behavior:**
```
project/
├── main.tf
├── terraform.tfstate          ← State file
└── terraform.tfstate.backup   ← Previous version
```

**Advantages:**
- ✅ Simple
- ✅ Fast
- ✅ Good for learning

**Disadvantages:**
- ❌ Not shared (team issues)
- ❌ No locking (concurrent edits)
- ❌ No encryption
- ❌ Easy to lose/delete

### Remote State

**Store state in:**
- S3 (AWS)
- Azure Blob Storage
- Google Cloud Storage
- Terraform Cloud
- Consul
- Postgres

**Advantages:**
- ✅ Shared across team
- ✅ State locking
- ✅ Encryption
- ✅ Versioning
- ✅ Backup

### State Security

**⚠️ State files contain sensitive data:**
- Passwords
- API keys
- Private IPs
- Resource IDs

**Best Practices:**
1. Never commit state to Git
2. Use remote state with encryption
3. Restrict access to state files
4. Use state locking
5. Enable versioning

### .gitignore for Terraform

```bash
# .gitignore
*.tfstate
*.tfstate.*
.terraform/
.terraform.lock.hcl
crash.log
override.tf
override.tf.json
*_override.tf
*_override.tf.json
.terraformrc
terraform.rc
```

### Inspecting State

```bash
# Show all resources in state
terraform state list

# Show specific resource details
terraform state show aws_instance.web

# Show state in JSON
terraform show -json
```

### State Locking

**Prevents concurrent modifications:**

```
User A runs terraform apply
    ↓
State locked
    ↓
User B tries terraform apply
    ↓
❌ Error: State locked by User A
```

### Key Takeaways

📌 **Remember:**
- State = Terraform's memory
- Never commit state to Git
- Use remote state for teams
- State contains sensitive data
- State locking prevents conflicts
- Always backup state files

---

## Section 17: State Commands and Operations

### What You'll Learn
- Essential state commands
- Importing existing resources
- Moving resources
- Removing resources from state
- State recovery

### Essential State Commands

```bash
# List all resources
terraform state list

# Show specific resource
terraform state show <resource>

# Move resource
terraform state mv <source> <destination>

# Remove resource from state
terraform state rm <resource>

# Import existing resource
terraform import <resource> <id>

# Replace resource
terraform apply -replace=<resource>

# Refresh state
terraform refresh
```

### terraform state list

```bash
# List all resources
terraform state list

# Output:
# aws_vpc.main
# aws_subnet.public[0]
# aws_subnet.public[1]
# aws_instance.web
# aws_security_group.web
```

### terraform state show

```bash
# Show details of specific resource
terraform state show aws_instance.web

# Output:
# resource "aws_instance" "web" {
#     ami                          = "ami-12345"
#     instance_type                = "t2.micro"
#     id                           = "i-1234567890abcdef0"
#     public_ip                    = "54.123.45.67"
#     ...
# }
```

### terraform state mv

**Rename a resource:**

```bash
# Before: resource "aws_instance" "server" {}
# After:  resource "aws_instance" "web_server" {}

terraform state mv aws_instance.server aws_instance.web_server
```

**Move to module:**

```bash
terraform state mv aws_instance.web module.compute.aws_instance.web
```

**Move from module:**

```bash
terraform state mv module.compute.aws_instance.web aws_instance.web
```

### terraform state rm

**Remove from state (keeps real resource):**

```bash
# Remove specific resource
terraform state rm aws_instance.old_server

# Remove all instances with count
terraform state rm 'aws_instance.servers[*]'

# Remove module
terraform state rm module.networking
```

**Use case:** Resource created manually, now managing with Terraform

### terraform import

**Import existing AWS resources:**

```hcl
# 1. Write resource config (without creating)
resource "aws_instance" "imported" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  # Add other required attributes
}
```

```bash
# 2. Import using resource ID
terraform import aws_instance.imported i-1234567890abcdef0

# 3. Verify
terraform plan  # Should show no changes
```

**Import Examples:**

```bash
# EC2 Instance
terraform import aws_instance.web i-1234567890abcdef0

# S3 Bucket
terraform import aws_s3_bucket.my_bucket my-bucket-name

# VPC
terraform import aws_vpc.main vpc-12345678

# Security Group
terraform import aws_security_group.web sg-12345678

# Subnet
terraform import aws_subnet.public subnet-12345678
```

### terraform apply -replace

**Force replace (recreate) a resource:**

```bash
# Old way (deprecated)
terraform taint aws_instance.web
terraform apply

# New way (Terraform 0.15.2+)
terraform apply -replace="aws_instance.web"
```

**Use cases:**
- Resource corrupted
- Need to trigger user_data again
- Force recreation for testing

### terraform refresh

**Update state from real infrastructure:**

```bash
terraform refresh

# Or (newer)
terraform apply -refresh-only
```

**Use case:** Someone made manual changes in AWS Console

### Practical Examples

#### Example 1: Renaming Resources

**Before:**
```hcl
resource "aws_instance" "server1" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
}
```

**Want to rename to:**
```hcl
resource "aws_instance" "web_server" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
}
```

**Steps:**
```bash
# 1. Update code
# 2. Move in state
terraform state mv aws_instance.server1 aws_instance.web_server

# 3. Verify
terraform plan  # Should show no changes
```

#### Example 2: Import Existing Infrastructure

**Scenario:** EC2 instance created manually, now want to manage with Terraform

```hcl
# 1. Define resource
resource "aws_instance" "existing" {
  ami           = "ami-12345"  # Must match real resource
  instance_type = "t2.micro"   # Must match real resource
  
  # Add all required attributes
}
```

```bash
# 2. Import
terraform import aws_instance.existing i-1234567890abcdef0

# 3. Check differences
terraform plan

# 4. Fix config to match real resource
# Edit main.tf to match all attributes shown in plan

# 5. Verify
terraform plan  # Should show 0 changes
```

#### Example 3: Remove Resource Without Deleting

**Scenario:** Want Terraform to forget about a resource but keep it in AWS

```bash
# Remove from state only
terraform state rm aws_instance.keep_this

# Now Terraform won't manage or delete this resource
```

#### Example 4: Moving to Module Structure

**Before:**
```hcl
# main.tf
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"
}
```

**After:**
```hcl
# main.tf
module "networking" {
  source = "./modules/networking"
}

# modules/networking/main.tf
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"
}
```

**Move resource:**
```bash
terraform state mv aws_vpc.main module.networking.aws_vpc.main
```

### State Backup and Recovery

**Automatic backups:**
```bash
# Terraform automatically creates backup
terraform.tfstate         # Current state
terraform.tfstate.backup  # Previous state
```

**Manual backup:**
```bash
# Backup current state
cp terraform.tfstate terraform.tfstate.$(date +%Y%m%d)

# Or
terraform state pull > backup.tfstate
```

**Restore from backup:**
```bash
# If using local state
cp terraform.tfstate.backup terraform.tfstate

# If using remote state
terraform state push backup.tfstate
```

### State Locking

**Check lock status:**
```bash
# If apply is stuck
terraform force-unlock <LOCK_ID>

# Find lock ID in error message:
# Error: Error acquiring the state lock
# Lock Info:
#   ID:        abc-123-def
```

### Troubleshooting State Issues

#### Issue 1: State and Reality Mismatch

```bash
# Sync state with real infrastructure
terraform refresh

# Or
terraform apply -refresh-only
```

#### Issue 2: Corrupted State

```bash
# Restore from backup
cp terraform.tfstate.backup terraform.tfstate

# Verify
terraform plan
```

#### Issue 3: Lost State File

```bash
# If using remote backend, re-initialize
terraform init

# If local state is lost, you must:
# 1. Manually map resources
# 2. Import each resource one by one
terraform import aws_instance.web i-1234567890abcdef0
# ... repeat for all resources
```

### Best Practices

1. **Before major changes:**
   ```bash
   cp terraform.tfstate terraform.tfstate.backup-before-changes
   ```

2. **Test state operations:**
   ```bash
   terraform plan  # Always plan before apply
   ```

3. **Use version control:**
   ```bash
   # But DON'T commit state files
   echo "*.tfstate*" >> .gitignore
   ```

4. **Document state operations:**
   ```bash
   # Keep a log of state commands run
   echo "$(date): terraform state mv ..." >> state-changes.log
   ```

### Key Takeaways

📌 **Remember:**
- `terraform state list` - See all resources
- `terraform state show` - See resource details
- `terraform state mv` - Rename resources
- `terraform state rm` - Remove from state (keep resource)
- `terraform import` - Add existing resources
- `terraform apply -replace` - Force recreate
- Always backup before state operations
- Test with `terraform plan` after state changes

---

## Section 18: Remote Backend with S3

### What You'll Learn
- Setting up S3 backend
- Backend configuration
- State locking with DynamoDB
- Backend initialization
- Team collaboration setup

### Why Remote Backend?

**Local State Problems:**
- ❌ Not shared (team can't collaborate)
- ❌ No locking (concurrent changes cause issues)
- ❌ No encryption (secrets exposed)
- ❌ Easy to lose

**Remote Backend (S3) Benefits:**
- ✅ Shared state across team
- ✅ State locking (with DynamoDB)
- ✅ Encryption at rest
- ✅ Versioning enabled
- ✅ Access control via IAM

### Architecture

```
Terraform
    ↓
S3 Bucket (stores state)
    ↓
DynamoDB Table (state locking)
```

### Step 1: Create S3 Bucket for State

**File: `backend-setup.tf`**
```hcl
# Run this first to create backend resources
provider "aws" {
  region = "us-east-2"
}

# S3 Bucket for state
resource "aws_s3_bucket" "terraform_state" {
  bucket = "my-terraform-state-bucket-12345"  # Must be unique
  
  lifecycle {
    prevent_destroy = true  # Protect from accidental deletion
  }
  
  tags = {
    Name = "Terraform State Bucket"
  }
}

# Enable versioning
resource "aws_s3_bucket_versioning" "terraform_state" {
  bucket = aws_s3_bucket.terraform_state.id
  
  versioning_configuration {
    status = "Enabled"
  }
}

# Enable encryption
resource "aws_s3_bucket_server_side_encryption_configuration" "terraform_state" {
  bucket = aws_s3_bucket.terraform_state.id
  
  rule {
    apply_server_side_encryption_by_default {
      sse_algorithm = "AES256"
    }
  }
}

# Block public access
resource "aws_s3_bucket_public_access_block" "terraform_state" {
  bucket = aws_s3_bucket.terraform_state.id
  
  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}

# Output bucket name
output "state_bucket_name" {
  value = aws_s3_bucket.terraform_state.id
}
```

### Step 2: Create DynamoDB Table for Locking

```hcl
# DynamoDB table for state locking
resource "aws_dynamodb_table" "terraform_locks" {
  name         = "terraform-state-locks"
  billing_mode = "PAY_PER_REQUEST"
  hash_key     = "LockID"
  
  attribute {
    name = "LockID"
    type = "S"
  }
  
  tags = {
    Name = "Terraform State Lock Table"
  }
}

output "dynamodb_table_name" {
  value = aws_dynamodb_table.terraform_locks.id
}
```

### Step 3: Apply Backend Setup

```bash
# Create S3 and DynamoDB
terraform init
terraform apply

# Note the output values
# state_bucket_name = "my-terraform-state-bucket-12345"
# dynamodb_table_name = "terraform-state-locks"
```

### Step 4: Configure Backend in Main Project

**File: `backend.tf`** (in your main project)
```hcl
terraform {
  backend "s3" {
    bucket         = "my-terraform-state-bucket-12345"
    key            = "project-name/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true
    dynamodb_table = "terraform-state-locks"
  }
}
```

### Step 5: Initialize Backend

```bash
# Migrate from local to remote state
terraform init

# Terraform will ask:
# Do you want to copy existing state to the new backend?
# Answer: yes
```

### Backend Configuration Options

```hcl
terraform {
  backend "s3" {
    # Required
    bucket = "my-state-bucket"
    key    = "path/to/terraform.tfstate"
    region = "us-east-2"
    
    # Recommended
    encrypt        = true
    dynamodb_table = "terraform-locks"
    
    # Optional
    workspace_key_prefix = "workspaces"
    role_arn             = "arn:aws:iam::123456789:role/TerraformRole"
    profile              = "terraform-user"
    
    # Versioning (handled by S3 bucket config)
    # Encryption (handled by S3 bucket config)
  }
}
```

### Multiple Environments

**Using different state files:**

```hcl
# Dev environment
terraform {
  backend "s3" {
    bucket = "my-state-bucket"
    key    = "dev/terraform.tfstate"
    region = "us-east-2"
  }
}

# Prod environment
terraform {
  backend "s3" {
    bucket = "my-state-bucket"
    key    = "prod/terraform.tfstate"
    region = "us-east-2"
  }
}
```

### Partial Backend Configuration

**File: `backend.tf`**
```hcl
terraform {
  backend "s3" {
    # Partial config - specify rest via CLI or file
  }
}
```

**File: `backend-config.hcl`**
```hcl
bucket         = "my-state-bucket"
key            = "project/terraform.tfstate"
region         = "us-east-2"
encrypt        = true
dynamodb_table = "terraform-locks"
```

```bash
# Initialize with config file
terraform init -backend-config=backend-config.hcl

# Or via command line
terraform init \
  -backend-config="bucket=my-state-bucket" \
  -backend-config="key=project/terraform.tfstate" \
  -backend-config="region=us-east-2"
```

### Complete Example: Backend Setup

**File: `backend-setup/main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
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
  default = "us-east-2"
}

variable "state_bucket_name" {
  description = "S3 bucket for Terraform state"
  type        = string
}

variable "dynamodb_table_name" {
  description = "DynamoDB table for state locking"
  type        = string
  default     = "terraform-state-locks"
}

# S3 Bucket
resource "aws_s3_bucket" "terraform_state" {
  bucket = var.state_bucket_name
  
  lifecycle {
    prevent_destroy = true
  }
}

resource "aws_s3_bucket_versioning" "terraform_state" {
  bucket = aws_s3_bucket.terraform_state.id
  
  versioning_configuration {
    status = "Enabled"
  }
}

resource "aws_s3_bucket_server_side_encryption_configuration" "terraform_state" {
  bucket = aws_s3_bucket.terraform_state.id
  
  rule {
    apply_server_side_encryption_by_default {
      sse_algorithm = "AES256"
    }
  }
}

resource "aws_s3_bucket_public_access_block" "terraform_state" {
  bucket = aws_s3_bucket.terraform_state.id
  
  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}

# DynamoDB Table
resource "aws_dynamodb_table" "terraform_locks" {
  name         = var.dynamodb_table_name
  billing_mode = "PAY_PER_REQUEST"
  hash_key     = "LockID"
  
  attribute {
    name = "LockID"
    type = "S"
  }
}

output "bucket_name" {
  value = aws_s3_bucket.terraform_state.id
}

output "dynamodb_table_name" {
  value = aws_dynamodb_table.terraform_locks.id
}

output "backend_config" {
  value = <<-EOT
    terraform {
      backend "s3" {
        bucket         = "${aws_s3_bucket.terraform_state.id}"
        key            = "YOUR-PROJECT-NAME/terraform.tfstate"
        region         = "${var.aws_region}"
        encrypt        = true
        dynamodb_table = "${aws_dynamodb_table.terraform_locks.id}"
      }
    }
  EOT
}
```

**Deploy:**
```bash
terraform init
terraform apply -var="state_bucket_name=my-unique-bucket-name"
```

### Accessing Remote State from Other Projects

```hcl
data "terraform_remote_state" "network" {
  backend = "s3"
  
  config = {
    bucket = "my-state-bucket"
    key    = "network/terraform.tfstate"
    region = "us-east-2"
  }
}

# Use outputs from other project
resource "aws_instance" "web" {
  subnet_id = data.terraform_remote_state.network.outputs.public_subnet_id
}
```

### Key Takeaways

📌 **Remember:**
- S3 backend enables team collaboration
- DynamoDB provides state locking
- Always enable versioning on state bucket
- Encrypt state bucket
- Use different state files for different environments
- Block public access to state bucket
- Keep backend setup separate from main code

**Setup steps:**
```bash
1. Create S3 bucket with versioning + encryption
2. Create DynamoDB table for locking
3. Configure backend in project
4. Run terraform init to migrate state
```

---

## Section 19: State Locking with DynamoDB

### What You'll Learn
- State locking mechanism
- DynamoDB setup for locking
- Testing state locks
- Troubleshooting lock issues
- Force unlocking

### What is State Locking?

**State locking** prevents multiple users from modifying infrastructure simultaneously.

**Without Locking:**
```
User A: terraform apply (starts)
User B: terraform apply (starts at same time)
Result: ❌ Conflicting changes, corrupted state
```

**With Locking:**
```
User A: terraform apply (locks state)
User B: terraform apply (waits for lock)
Result: ✅ Sequential execution, safe
```

### How DynamoDB Locking Works

```
1. User runs terraform apply
2. Terraform creates lock record in DynamoDB
3. Other users must wait
4. After apply completes, lock is released
5. Next user can proceed
```

### DynamoDB Table Structure

```hcl
resource "aws_dynamodb_table" "terraform_locks" {
  name         = "terraform-state-locks"
  billing_mode = "PAY_PER_REQUEST"  # No upfront cost
  hash_key     = "LockID"           # Required name
  
  attribute {
    name = "LockID"
    type = "S"  # String
  }
  
  tags = {
    Name = "Terraform State Locks"
  }
}
```

**Lock Record:**
```json
{
  "LockID": "my-bucket/project/terraform.tfstate-md5",
  "Info": "{\"ID\":\"abc-123\",\"Operation\":\"OperationTypeApply\",\"Who\":\"user@example.com\",\"Version\":\"1.5.0\",\"Created\":\"2024-01-15T10:30:00Z\",\"Path\":\"project/terraform.tfstate\"}"
}
```

### Testing State Locking

**Terminal 1:**
```bash
terraform apply
# Starts and locks state
```

**Terminal 2 (while Terminal 1 is running):**
```bash
terraform apply

# Output:
# Error: Error acquiring the state lock
#
# Error message: ConditionalCheckFailedException: The conditional request failed
# Lock Info:
#   ID:        abc-123-def-456
#   Path:      project/terraform.tfstate
#   Operation: OperationTypeApply
#   Who:       user@hostname
#   Version:   1.5.0
#   Created:   2024-01-15 10:30:00
#
# Terraform acquires a state lock to protect the state from being written
# by multiple users at the same time. Please resolve the issue above and try
# again. For most commands, you can disable locking with the "-lock=false"
# flag, but this is not recommended.
```

### Manual Lock Management

**Force unlock (use carefully!):**
```bash
# Get Lock ID from error message
terraform force-unlock abc-123-def-456

# Confirm with: yes
```

**⚠️ Only force unlock when:**
- Process crashed and lock wasn't released
- You're absolutely sure no one else is running terraform
- Never force unlock during active operations

### Disable Locking (Not Recommended)

```bash
# Disable for specific command
terraform apply -lock=false

# ❌ Dangerous - only for emergencies
```

### Backend with Locking

```hcl
terraform {
  backend "s3" {
    bucket         = "my-state-bucket"
    key            = "project/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true
    dynamodb_table = "terraform-state-locks"  # Enables locking
  }
}
```

### Complete Setup Example

```hcl
# Step 1: Create DynamoDB table
resource "aws_dynamodb_table" "terraform_locks" {
  name         = "terraform-state-locks"
  billing_mode = "PAY_PER_REQUEST"
  hash_key     = "LockID"
  
  attribute {
    name = "LockID"
    type = "S"
  }
  
  point_in_time_recovery {
    enabled = true
  }
  
  tags = {
    Name = "Terraform State Locks"
  }
}

# Step 2: Configure backend
terraform {
  backend "s3" {
    bucket         = "my-state-bucket"
    key            = "project/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true
    dynamodb_table = aws_dynamodb_table.terraform_locks.name
  }
}
```

### Viewing Locks in AWS Console

1. Go to DynamoDB Console
2. Select "terraform-state-locks" table
3. Click "Explore table items"
4. See active locks

### Lock Timeout

Locks don't timeout automatically. If a process crashes:

```bash
# Check if lock exists in DynamoDB
aws dynamodb scan --table-name terraform-state-locks

# If stuck lock found, force unlock
terraform force-unlock <LOCK_ID>
```

### Key Takeaways

📌 **Remember:**
- State locking prevents concurrent modifications
- DynamoDB table required for S3 backend locking
- Hash key must be named "LockID"
- Use PAY_PER_REQUEST billing mode
- Only force unlock when absolutely necessary
- Locking is automatic with proper backend config

---

## Section 20: Migrating Local State to Remote

### What You'll Learn
- Migration process
- Testing migration
- Rollback procedures
- Best practices
- Common issues

### Migration Steps

**Current setup (local state):**
```
project/
├── main.tf
└── terraform.tfstate  ← Local state
```

**Goal (remote state):**
```
project/
├── main.tf
└── backend.tf

State stored in S3 →
```

### Step-by-Step Migration

#### Step 1: Backup Current State

```bash
# Create backup
cp terraform.tfstate terraform.tfstate.backup-$(date +%Y%m%d)

# Or
terraform state pull > state-backup.json
```

#### Step 2: Create Backend Resources

```hcl
# backend-setup.tf (separate project)
resource "aws_s3_bucket" "terraform_state" {
  bucket = "my-terraform-state-bucket"
}

resource "aws_s3_bucket_versioning" "terraform_state" {
  bucket = aws_s3_bucket.terraform_state.id
  versioning_configuration {
    status = "Enabled"
  }
}

resource "aws_dynamodb_table" "terraform_locks" {
  name         = "terraform-state-locks"
  billing_mode = "PAY_PER_REQUEST"
  hash_key     = "LockID"
  
  attribute {
    name = "LockID"
    type = "S"
  }
}
```

```bash
terraform init
terraform apply
```

#### Step 3: Add Backend Configuration

**File: `backend.tf`**
```hcl
terraform {
  backend "s3" {
    bucket         = "my-terraform-state-bucket"
    key            = "project/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true
    dynamodb_table = "terraform-state-locks"
  }
}
```

#### Step 4: Initialize Migration

```bash
terraform init

# Terraform will detect backend change and ask:
# 
# Initializing the backend...
# Do you want to copy existing state to the new backend?
#   Pre-existing state was found while migrating the previous "local" backend to the
#   newly configured "s3" backend. No existing state was found in the newly
#   configured "s3" backend. Do you want to copy this state to the new "s3"
#   backend? Enter "yes" to copy and "no" to start with an empty state.
#
#   Enter a value: yes

# Type: yes
```

#### Step 5: Verify Migration

```bash
# Check that state is in S3
aws s3 ls s3://my-terraform-state-bucket/project/

# Verify Terraform can read state
terraform plan

# Should show: No changes
```

#### Step 6: Clean Up Local State

```bash
# After confirming remote state works
rm terraform.tfstate
rm terraform.tfstate.backup

# Keep the dated backup for safety
# terraform.tfstate.backup-20240115
```

### Migration with Multiple Environments

**Before (local state):**
```
dev/
├── main.tf
└── terraform.tfstate

prod/
├── main.tf
└── terraform.tfstate
```

**After (remote state):**
```hcl
# dev/backend.tf
terraform {
  backend "s3" {
    bucket = "my-state-bucket"
    key    = "dev/terraform.tfstate"
    region = "us-east-2"
  }
}

# prod/backend.tf
terraform {
  backend "s3" {
    bucket = "my-state-bucket"
    key    = "prod/terraform.tfstate"
    region = "us-east-2"
  }
}
```

### Testing Migration

```bash
# 1. Plan should show no changes
terraform plan

# 2. Try a small change
# Add a tag to existing resource

# 3. Apply and verify
terraform apply

# 4. Check state in S3
aws s3 cp s3://my-state-bucket/project/terraform.tfstate - | head -20
```

### Rollback to Local State

**If something goes wrong:**

```bash
# 1. Remove backend configuration
# Comment out or delete backend.tf

# 2. Re-initialize with local backend
terraform init -migrate-state

# 3. Pull state from S3 manually
aws s3 cp s3://my-state-bucket/project/terraform.tfstate terraform.tfstate

# 4. Verify
terraform plan
```

### Partial Backend Configuration

**For flexibility:**

**File: `backend.tf`**
```hcl
terraform {
  backend "s3" {}
}
```

**File: `dev.backend.hcl`**
```hcl
bucket = "my-state-bucket"
key    = "dev/terraform.tfstate"
region = "us-east-2"
```

**File: `prod.backend.hcl`**
```hcl
bucket = "my-state-bucket"
key    = "prod/terraform.tfstate"
region = "us-east-2"
```

**Usage:**
```bash
# Dev
terraform init -backend-config=dev.backend.hcl

# Prod
terraform init -backend-config=prod.backend.hcl
```

### Common Issues and Solutions

#### Issue 1: "Backend configuration changed"

```bash
# Error: Backend configuration changed

# Solution: Reconfigure backend
terraform init -reconfigure
```

#### Issue 2: State already exists in S3

```bash
# Error: State already exists in the new backend

# Solution: Either use existing state or force copy
terraform init -migrate-state
```

#### Issue 3: Permission denied

```bash
# Error: AccessDenied: Access Denied

# Solution: Check IAM permissions
aws s3 ls s3://my-state-bucket/

# Required permissions:
# s3:ListBucket
# s3:GetObject
# s3:PutObject
# dynamodb:PutItem
# dynamodb:GetItem
# dynamodb:DeleteItem
```

### Complete Migration Script

```bash
#!/bin/bash
# migrate-to-remote.sh

set -e

echo "Starting state migration..."

# 1. Backup
echo "Creating backup..."
cp terraform.tfstate terraform.tfstate.backup-$(date +%Y%m%d-%H%M%S)

# 2. Verify S3 bucket exists
echo "Checking S3 bucket..."
aws s3 ls s3://my-state-bucket/ || {
  echo "Error: S3 bucket doesn't exist"
  exit 1
}

# 3. Add backend config
echo "Adding backend configuration..."
cat > backend.tf <<EOF
terraform {
  backend "s3" {
    bucket         = "my-state-bucket"
    key            = "project/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true
    dynamodb_table = "terraform-state-locks"
  }
}
EOF

# 4. Initialize migration
echo "Migrating state..."
terraform init -input=false

# 5. Verify
echo "Verifying migration..."
terraform plan -detailed-exitcode || {
  echo "Warning: Plan shows changes - review carefully"
}

echo "Migration complete!"
echo "Local state backed up to: terraform.tfstate.backup-*"
```

### Key Takeaways

📌 **Remember:**
- Always backup state before migration
- Test with non-critical environments first
- Verify state after migration with `terraform plan`
- Keep local state backup for rollback
- Migration is reversible
- Use `-reconfigure` if backend config changes

**Migration checklist:**
```
✅ Backup local state
✅ Create S3 bucket and DynamoDB table
✅ Add backend.tf
✅ Run terraform init
✅ Confirm migration (type "yes")
✅ Verify with terraform plan
✅ Test a small change
✅ Remove local state files
✅ Keep backup for 30 days
```

---

**🎉 Congratulations!** You've completed Part 4: State Management!

---

# Part 5: Advanced Resource Management

---

## Section 21: Meta-Arguments - Count

### What You'll Learn
- Using count to create multiple resources
- Accessing count.index
- Conditional resource creation
- Count limitations
- Best practices

### What is Count?

**Count** creates multiple identical resources.

```hcl
resource "aws_instance" "servers" {
  count = 3  # Creates 3 instances
  
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Name = "server-${count.index}"
  }
}
```

**Result:**
- server-0
- server-1
- server-2

### Basic Count Example

```hcl
resource "aws_instance" "web" {
  count = 2
  
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Name = "web-${count.index + 1}"
  }
}

# Creates:
# aws_instance.web[0] → "web-1"
# aws_instance.web[1] → "web-2"
```

### Accessing Created Resources

```hcl
# Reference specific instance
output "first_instance_ip" {
  value = aws_instance.web[0].public_ip
}

# Reference all instances
output "all_instance_ips" {
  value = aws_instance.web[*].public_ip
}
```

### Count with Variables

```hcl
variable "instance_count" {
  type    = number
  default = 3
}

resource "aws_instance" "servers" {
  count = var.instance_count
  
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Name = "server-${count.index + 1}"
  }
}
```

### Count with Lists

```hcl
variable "availability_zones" {
  type = list(string)
  default = [
    "us-east-2a",
    "us-east-2b",
    "us-east-2c"
  ]
}

resource "aws_subnet" "public" {
  count = length(var.availability_zones)
  
  vpc_id            = aws_vpc.main.id
  cidr_block        = cidrsubnet("10.0.0.0/16", 8, count.index)
  availability_zone = var.availability_zones[count.index]
  
  tags = {
    Name = "public-subnet-${count.index + 1}"
  }
}
```

### Conditional Creation with Count

```hcl
variable "create_database" {
  type    = bool
  default = true
}

resource "aws_db_instance" "database" {
  count = var.create_database ? 1 : 0
  
  identifier     = "mydb"
  engine         = "postgres"
  instance_class = "db.t3.micro"
  allocated_storage = 20
}

# Access conditionally created resource
output "database_endpoint" {
  value = var.create_database ? aws_db_instance.database[0].endpoint : "No database"
}
```

### Count with Different Values

```hcl
variable "instance_types" {
  type = list(string)
  default = ["t2.micro", "t2.small", "t2.medium"]
}

resource "aws_instance" "servers" {
  count = length(var.instance_types)
  
  ami           = "ami-12345"
  instance_type = var.instance_types[count.index]
  
  tags = {
    Name = "server-${var.instance_types[count.index]}"
  }
}
```

### Complete Count Example

```hcl
# variables.tf
variable "web_servers" {
  type    = number
  default = 3
}

variable "environment" {
  type    = string
  default = "dev"
}

# main.tf
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

resource "aws_instance" "web" {
  count = var.web_servers
  
  ami           = data.aws_ami.amazon_linux.id
  instance_type = "t2.micro"
  
  user_data = <<-EOF
              #!/bin/bash
              echo "Server ${count.index + 1}" > /var/www/html/index.html
              EOF
  
  tags = {
    Name        = "${var.environment}-web-${count.index + 1}"
    Environment = var.environment
    Index       = count.index
  }
}

resource "aws_eip" "web" {
  count    = var.web_servers
  instance = aws_instance.web[count.index].id
  
  tags = {
    Name = "${var.environment}-web-eip-${count.index + 1}"
  }
}

# outputs.tf
output "instance_ids" {
  value = aws_instance.web[*].id
}

output "public_ips" {
  value = aws_eip.web[*].public_ip
}

output "instance_details" {
  value = [
    for i, instance in aws_instance.web : {
      id         = instance.id
      public_ip  = aws_eip.web[i].public_ip
      index      = i
    }
  ]
}
```

### Count Limitations

#### Problem 1: Order Matters

```hcl
variable "servers" {
  type = list(string)
  default = ["web", "app", "db"]
}

resource "aws_instance" "servers" {
  count = length(var.servers)
  
  tags = {
    Name = var.servers[count.index]
  }
}

# If you remove "app":
# default = ["web", "db"]
# 
# Terraform will:
# ❌ Destroy "db" (was [2], now doesn't exist)
# ❌ Recreate "db" at [1]
# This is problematic!
```

#### Problem 2: Can't Use count with for_each

```hcl
# ❌ Error: Cannot use both count and for_each
resource "aws_instance" "servers" {
  count    = 3
  for_each = toset(["a", "b"])  # Error!
}
```

### When to Use Count

**✅ Use count when:**
- Creating identical resources
- Number of resources is a simple number
- Resources are interchangeable
- Order doesn't matter (or is acceptable)

**❌ Don't use count when:**
- Each resource is unique
- Need to add/remove from middle of list
- Resources have different configurations
- (Use for_each instead)

### Count Best Practices

#### 1. Use count.index for uniqueness

```hcl
# ✅ Good
resource "aws_instance" "web" {
  count = 3
  
  tags = {
    Name = "web-${count.index}"
  }
}
```

#### 2. Use splat expressions for outputs

```hcl
# ✅ Good
output "all_ips" {
  value = aws_instance.web[*].public_ip
}

# ❌ Bad (verbose)
output "all_ips" {
  value = [
    aws_instance.web[0].public_ip,
    aws_instance.web[1].public_ip,
    aws_instance.web[2].public_ip,
  ]
}
```

#### 3. Protect against empty lists

```hcl
# ✅ Good
resource "aws_instance" "web" {
  count = length(var.subnets) > 0 ? length(var.subnets) : 1
}

# ❌ Bad (could create 0 resources unexpectedly)
resource "aws_instance" "web" {
  count = length(var.subnets)
}
```

### Key Takeaways

📌 **Remember:**
- count creates multiple identical resources
- count.index starts at 0
- Use [*] to reference all resources
- Conditional: count = condition ? 1 : 0
- Order matters - removing from middle causes recreation
- Can't combine count and for_each
- For unique resources, use for_each instead

---

## Section 22: Meta-Arguments - For_Each

### What You'll Learn
- Using for_each with maps and sets
- Advantages over count
- Accessing each.key and each.value
- Complex for_each examples
- When to use for_each vs count

### What is for_each?

**for_each** creates resources based on map or set.

```hcl
resource "aws_instance" "servers" {
  for_each = {
    web = "t2.micro"
    app = "t2.small"
    db  = "t2.medium"
  }
  
  ami           = "ami-12345"
  instance_type = each.value
  
  tags = {
    Name = each.key
  }
}
```

**Result:**
- aws_instance.servers["web"]
- aws_instance.servers["app"]
- aws_instance.servers["db"]

### for_each with Map

```hcl
variable "instances" {
  type = map(string)
  default = {
    web = "t2.micro"
    app = "t2.small"
    db  = "t2.medium"
  }
}

resource "aws_instance" "servers" {
  for_each = var.instances
  
  ami           = "ami-12345"
  instance_type = each.value
  
  tags = {
    Name = each.key
    Type = each.value
  }
}

# Creates:
# aws_instance.servers["web"]
# aws_instance.servers["app"]
# aws_instance.servers["db"]
```

### for_each with Set

```hcl
variable "users" {
  type = set(string)
  default = ["alice", "bob", "charlie"]
}

resource "aws_iam_user" "users" {
  for_each = var.users
  
  name = each.value  # each.key == each.value for sets
}

# Creates:
# aws_iam_user.users["alice"]
# aws_iam_user.users["bob"]
# aws_iam_user.users["charlie"]
```

### Accessing Resources

```hcl
# Reference specific resource
output "web_instance_id" {
  value = aws_instance.servers["web"].id
}

# Reference all resources (map)
output "all_instance_ids" {
  value = {
    for k, v in aws_instance.servers : k => v.id
  }
}

# Convert to list
output "instance_id_list" {
  value = values(aws_instance.servers)[*].id
}
```

### for_each with toset()

```hcl
variable "availability_zones" {
  type = list(string)
  default = ["us-east-2a", "us-east-2b", "us-east-2c"]
}

resource "aws_subnet" "public" {
  for_each = toset(var.availability_zones)
  
  vpc_id            = aws_vpc.main.id
  cidr_block        = cidrsubnet("10.0.0.0/16", 8, index(var.availability_zones, each.value))
  availability_zone = each.value
  
  tags = {
    Name = "public-${each.value}"
  }
}
```

### Complex for_each with Objects

```hcl
variable "servers" {
  type = map(object({
    instance_type = string
    ami           = string
    disk_size     = number
  }))
  
  default = {
    web = {
      instance_type = "t2.micro"
      ami           = "ami-12345"
      disk_size     = 20
    }
    app = {
      instance_type = "t2.small"
      ami           = "ami-12345"
      disk_size     = 30
    }
    db = {
      instance_type = "t2.medium"
      ami           = "ami-67890"
      disk_size     = 50
    }
  }
}

resource "aws_instance" "servers" {
  for_each = var.servers
  
  ami           = each.value.ami
  instance_type = each.value.instance_type
  
  root_block_device {
    volume_size = each.value.disk_size
  }
  
  tags = {
    Name = each.key
  }
}
```

### for_each vs count

**Advantage of for_each:**

```hcl
# With count
variable "servers" {
  default = ["web", "app", "db"]
}

resource "aws_instance" "servers" {
  count = length(var.servers)
  
  tags = {
    Name = var.servers[count.index]
  }
}

# Remove "app" → default = ["web", "db"]
# ❌ Terraform destroys and recreates "db"
```

```hcl
# With for_each
variable "servers" {
  default = toset(["web", "app", "db"])
}

resource "aws_instance" "servers" {
  for_each = var.servers
  
  tags = {
    Name = each.value
  }
}

# Remove "app" → default = toset(["web", "db"])
# ✅ Terraform only destroys "app", keeps others unchanged
```

### Dynamic Security Group Rules

```hcl
variable "ingress_rules" {
  type = map(object({
    port        = number
    protocol    = string
    cidr_blocks = list(string)
    description = string
  }))
  
  default = {
    http = {
      port        = 80
      protocol    = "tcp"
      cidr_blocks = ["0.0.0.0/0"]
      description = "HTTP"
    }
    https = {
      port        = 443
      protocol    = "tcp"
      cidr_blocks = ["0.0.0.0/0"]
      description = "HTTPS"
    }
    ssh = {
      port        = 22
      protocol    = "tcp"
      cidr_blocks = ["10.0.0.0/8"]
      description = "SSH from private network"
    }
  }
}

resource "aws_security_group" "web" {
  name = "web-sg"
  
  dynamic "ingress" {
    for_each = var.ingress_rules
    
    content {
      description = ingress.value.description
      from_port   = ingress.value.port
      to_port     = ingress.value.port
      protocol    = ingress.value.protocol
      cidr_blocks = ingress.value.cidr_blocks
    }
  }
}
```

### Complete for_each Example

```hcl
# variables.tf
variable "environments" {
  type = map(object({
    instance_type = string
    min_size      = number
    max_size      = number
    tags          = map(string)
  }))
  
  default = {
    dev = {
      instance_type = "t2.micro"
      min_size      = 1
      max_size      = 2
      tags = {
        Environment = "dev"
        CostCenter  = "engineering"
      }
    }
    staging = {
      instance_type = "t2.small"
      min_size      = 2
      max_size      = 4
      tags = {
        Environment = "staging"
        CostCenter  = "engineering"
      }
    }
    prod = {
      instance_type = "t2.medium"
      min_size      = 3
      max_size      = 10
      tags = {
        Environment = "prod"
        CostCenter  = "operations"
      }
    }
  }
}

# main.tf
resource "aws_instance" "app" {
  for_each = var.environments
  
  ami           = data.aws_ami.amazon_linux.id
  instance_type = each.value.instance_type
  
  tags = merge(
    each.value.tags,
    { Name = "${each.key}-app-server" }
  )
}

resource "aws_autoscaling_group" "app" {
  for_each = var.environments
  
  name                = "${each.key}-asg"
  min_size            = each.value.min_size
  max_size            = each.value.max_size
  desired_capacity    = each.value.min_size
  vpc_zone_identifier = [aws_subnet.public[each.key].id]
  
  tag {
    key                 = "Environment"
    value               = each.key
    propagate_at_launch = true
  }
}

# outputs.tf
output "instance_details" {
  value = {
    for env, instance in aws_instance.app :
    env => {
      id         = instance.id
      public_ip  = instance.public_ip
      type       = instance.instance_type
    }
  }
}
```

### for_each with Multiple Resources

```hcl
locals {
  applications = {
    web = {
      port = 80
      health_check = "/health"
    }
    api = {
      port = 8080
      health_check = "/api/health"
    }
  }
}

resource "aws_lb_target_group" "app" {
  for_each = local.applications
  
  name     = "${each.key}-tg"
  port     = each.value.port
  protocol = "HTTP"
  vpc_id   = aws_vpc.main.id
  
  health_check {
    path = each.value.health_check
  }
}

resource "aws_lb_listener_rule" "app" {
  for_each = local.applications
  
  listener_arn = aws_lb_listener.main.arn
  priority     = 100 + index(keys(local.applications), each.key)
  
  action {
    type             = "forward"
    target_group_arn = aws_lb_target_group.app[each.key].arn
  }
  
  condition {
    path_pattern {
      values = ["/${each.key}/*"]
    }
  }
}
```

### Key Takeaways

📌 **Remember:**
- for_each works with maps and sets
- each.key and each.value to access items
- Better than count for unique resources
- Can add/remove from middle without recreation
- Use toset() to convert list to set
- Reference: resource["key"]
- Can't combine with count
- More flexible for complex scenarios

**When to use:**
- ✅ for_each: Unique resources, flexible addition/removal
- ✅ count: Identical resources, simple multiplier

---

## Section 23: Conditional Expressions

### What You'll Learn
- Ternary operator syntax
- Conditional resource creation
- Conditional values
- Complex conditionals
- Best practices

### Ternary Operator

**Syntax:**
```hcl
condition ? true_value : false_value
```

### Basic Conditionals

```hcl
variable "environment" {
  default = "prod"
}

resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = var.environment == "prod" ? "t2.large" : "t2.micro"
  
  tags = {
    Name = var.environment == "prod" ? "Production Server" : "Development Server"
  }
}
```

### Conditional Resource Creation

```hcl
variable "create_database" {
  type    = bool
  default = true
}

resource "aws_db_instance" "main" {
  count = var.create_database ? 1 : 0
  
  identifier     = "mydb"
  engine         = "postgres"
  instance_class = "db.t3.micro"
}

output "database_endpoint" {
  value = var.create_database ? aws_db_instance.main[0].endpoint : "No database"
}
```

### Multiple Conditions

```hcl
variable "environment" {
  type = string
}

variable "enable_backups" {
  type = bool
}

locals {
  backup_retention = var.environment == "prod" && var.enable_backups ? 30 : 7
  
  instance_type = var.environment == "prod" ? "t2.large" : 
                  var.environment == "staging" ? "t2.medium" : 
                  "t2.micro"
}
```

### Conditional Values in Maps

```hcl
variable "environment" {
  type = string
}

locals {
  instance_config = {
    prod = {
      type  = "t2.large"
      count = 3
    }
    staging = {
      type  = "t2.medium"
      count = 2
    }
    dev = {
      type  = "t2.micro"
      count = 1
    }
  }
  
  config = local.instance_config[var.environment]
}

resource "aws_instance" "app" {
  count = local.config.count
  
  ami           = "ami-12345"
  instance_type = local.config.type
}
```

### Conditional Blocks

```hcl
variable "enable_monitoring" {
  type    = bool
  default = false
}

resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  monitoring = var.enable_monitoring
  
  # Conditional EBS block
  dynamic "ebs_block_device" {
    for_each = var.enable_monitoring ? [1] : []
    
    content {
      device_name = "/dev/sdf"
      volume_size = 100
    }
  }
}
```

### Environment-Based Configuration

```hcl
variable "environment" {
  type = string
  
  validation {
    condition     = contains(["dev", "staging", "prod"], var.environment)
    error_message = "Environment must be dev, staging, or prod."
  }
}

locals {
  is_production = var.environment == "prod"
  is_dev        = var.environment == "dev"
}

resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = local.is_production ? "t2.large" : "t2.micro"
  
  root_block_device {
    volume_size = local.is_production ? 100 : 20
    encrypted   = local.is_production
  }
  
  monitoring = local.is_production
  
  tags = {
    Name        = "web-${var.environment}"
    Environment = var.environment
    Backup      = local.is_production ? "daily" : "weekly"
  }
}

# Conditional backup
resource "aws_backup_plan" "main" {
  count = local.is_production ? 1 : 0
  
  name = "production-backup"
  
  rule {
    rule_name         = "daily_backup"
    target_vault_name = "production"
    schedule          = "cron(0 2 * * ? *)"
  }
}
```

### Conditional with Lookup

```hcl
variable "environment" {
  type = string
}

variable "instance_types" {
  type = map(string)
  default = {
    dev     = "t2.micro"
    staging = "t2.small"
    prod    = "t2.large"
  }
}

resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = lookup(var.instance_types, var.environment, "t2.micro")
}
```

### Complete Conditional Example

```hcl
# variables.tf
variable "environment" {
  type = string
}

variable "enable_ha" {
  type        = bool
  default     = false
  description = "Enable high availability"
}

variable "enable_backups" {
  type    = bool
  default = false
}

# locals.tf
locals {
  is_production = var.environment == "prod"
  is_staging    = var.environment == "staging"
  is_dev        = var.environment == "dev"
  
  # Instance configuration
  instance_count = var.enable_ha ? 3 : 1
  instance_type  = local.is_production ? "t2.large" :
                   local.is_staging ? "t2.medium" : "t2.micro"
  
  # Storage configuration
  volume_size = local.is_production ? 100 : 20
  encrypted   = local.is_production || local.is_staging
  
  # Backup configuration
  backup_retention = local.is_production && var.enable_backups ? 30 :
                     local.is_staging && var.enable_backups ? 14 : 7
  
  # Tags
  common_tags = {
    Environment = var.environment
    ManagedBy   = "Terraform"
    HA          = var.enable_ha ? "enabled" : "disabled"
  }
}

# main.tf
resource "aws_instance" "app" {
  count = local.instance_count
  
  ami           = data.aws_ami.amazon_linux.id
  instance_type = local.instance_type
  
  monitoring = local.is_production
  
  root_block_device {
    volume_size = local.volume_size
    volume_type = local.is_production ? "gp3" : "gp2"
    encrypted   = local.encrypted
    iops        = local.is_production ? 3000 : null
  }
  
  tags = merge(
    local.common_tags,
    {
      Name  = "app-${var.environment}-${count.index + 1}"
      Index = count.index
    }
  )
}

# Conditional RDS
resource "aws_db_instance" "main" {
  count = local.is_production || local.is_staging ? 1 : 0
  
  identifier     = "${var.environment}-db"
  engine         = "postgres"
  instance_class = local.is_production ? "db.t3.large" : "db.t3.micro"
  
  allocated_storage     = local.is_production ? 100 : 20
  multi_az              = local.is_production && var.enable_ha
  backup_retention_period = local.backup_retention
  
  tags = local.common_tags
}

# Conditional Load Balancer
resource "aws_lb" "main" {
  count = var.enable_ha ? 1 : 0
  
  name               = "${var.environment}-lb"
  internal           = false
  load_balancer_type = "application"
  security_groups    = [aws_security_group.lb[0].id]
  subnets            = aws_subnet.public[*].id
  
  tags = local.common_tags
}

# outputs.tf
output "instance_details" {
  value = {
    count         = local.instance_count
    type          = local.instance_type
    ha_enabled    = var.enable_ha
    monitoring    = local.is_production
    database      = local.is_production || local.is_staging ? "created" : "not created"
    load_balancer = var.enable_ha ? "created" : "not created"
  }
}
```

### Key Takeaways

📌 **Remember:**
- Syntax: `condition ? true_val : false_val`
- Create resources: `count = condition ? 1 : 0`
- Chain conditions with nested ternary operators
- Use locals for complex conditional logic
- Validate conditions with validation blocks
- Combine with lookup() for map-based selection

---

## Section 24: Dependencies with Depends_On

### What You'll Learn
- Implicit vs explicit dependencies
- When to use depends_on
- Managing dependencies
- Dependency graphs
- Common patterns

### Implicit Dependencies

**Terraform automatically detects dependencies:**

```hcl
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"
}

resource "aws_subnet" "public" {
  vpc_id     = aws_vpc.main.id  # ← Implicit dependency
  cidr_block = "10.0.1.0/24"
}

# Terraform knows: Create VPC first, then subnet
```

### Explicit Dependencies with depends_on

**When implicit dependency isn't enough:**

```hcl
resource "aws_iam_role" "example" {
  name = "example-role"
  
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

resource "aws_iam_role_policy" "example" {
  role = aws_iam_role.example.name  # Implicit dependency
  
  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [{
      Effect   = "Allow"
      Action   = "s3:*"
      Resource = "*"
    }]
  })
}

resource "aws_iam_instance_profile" "example" {
  name = "example-profile"
  role = aws_iam_role.example.name
  
  # Need to wait for policy attachment to complete
  depends_on = [aws_iam_role_policy.example]  # Explicit dependency
}
```

### When to Use depends_on

**Use depends_on when:**
1. No direct resource reference
2. Hidden dependencies (API eventually consistent)
3. Module dependencies
4. Ordering requirements not captured by references

### Example: S3 Bucket and Policy

```hcl
resource "aws_s3_bucket" "example" {
  bucket = "my-bucket"
}

resource "aws_s3_bucket_public_access_block" "example" {
  bucket = aws_s3_bucket.example.id
  
  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}

resource "aws_s3_bucket_policy" "example" {
  bucket = aws_s3_bucket.example.id
  
  # Must wait for public access block
  depends_on = [aws_s3_bucket_public_access_block.example]
  
  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [{
      Sid       = "DenyInsecureTransport"
      Effect    = "Deny"
      Principal = "*"
      Action    = "s3:*"
      Resource = [
        aws_s3_bucket.example.arn,
        "${aws_s3_bucket.example.arn}/*"
      ]
      Condition = {
        Bool = {
          "aws:SecureTransport" = "false"
        }
      }
    }]
  })
}
```

### Multiple Dependencies

```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  depends_on = [
    aws_security_group.web,
    aws_iam_role.ec2_role,
    aws_s3_bucket.data
  ]
}
```

### Module Dependencies

```hcl
module "network" {
  source = "./modules/network"
}

module "compute" {
  source = "./modules/compute"
  
  vpc_id    = module.network.vpc_id
  subnet_id = module.network.subnet_id
  
  # Ensure network is fully created
  depends_on = [module.network]
}

module "database" {
  source = "./modules/database"
  
  # Wait for both network and compute
  depends_on = [
    module.network,
    module.compute
  ]
}
```

### Viewing Dependencies

```bash
# Generate dependency graph
terraform graph

# Visualize with graphviz
terraform graph | dot -Tpng > graph.png

# Or online: http://dreampuf.github.io/GraphvizOnline/
terraform graph | pbcopy  # Copy to clipboard (Mac)
```

### Example: IAM User and Policy

```hcl
resource "aws_iam_user" "developer" {
  name = "developer"
}

resource "aws_iam_user_policy" "developer" {
  name = "developer-policy"
  user = aws_iam_user.developer.name
  
  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [{
      Effect = "Allow"
      Action = [
        "ec2:Describe*",
        "s3:List*"
      ]
      Resource = "*"
    }]
  })
}

resource "aws_iam_access_key" "developer" {
  user = aws_iam_user.developer.name
  
  # Wait for policy to be attached
  depends_on = [aws_iam_user_policy.developer]
}

output "access_key" {
  value     = aws_iam_access_key.developer.id
  sensitive = true
}
```

### Complete Example with Dependencies

```hcl
# VPC
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"
}

# Internet Gateway (depends on VPC implicitly)
resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id
}

# Subnet (depends on VPC implicitly)
resource "aws_subnet" "public" {
  vpc_id     = aws_vpc.main.id
  cidr_block = "10.0.1.0/24"
}

# Route Table (depends on VPC implicitly)
resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id
}

# Route (depends on RT and IGW implicitly)
resource "aws_route" "public_internet" {
  route_table_id         = aws_route_table.public.id
  destination_cidr_block = "0.0.0.0/0"
  gateway_id             = aws_internet_gateway.main.id
}

# Route Table Association (depends on RT and Subnet implicitly)
resource "aws_route_table_association" "public" {
  subnet_id      = aws_subnet.public.id
  route_table_id = aws_route_table.public.id
}

# Security Group (depends on VPC implicitly)
resource "aws_security_group" "web" {
  vpc_id = aws_vpc.main.id
  
  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

# IAM Role
resource "aws_iam_role" "ec2_role" {
  name = "ec2-role"
  
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

# IAM Role Policy
resource "aws_iam_role_policy" "ec2_policy" {
  role = aws_iam_role.ec2_role.id
  
  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [{
      Effect   = "Allow"
      Action   = "s3:*"
      Resource = "*"
    }]
  })
}

# IAM Instance Profile
resource "aws_iam_instance_profile" "ec2_profile" {
  role = aws_iam_role.ec2_role.name
  
  # Explicit dependency: wait for policy attachment
  depends_on = [aws_iam_role_policy.ec2_policy]
}

# EC2 Instance
resource "aws_instance" "web" {
  ami                    = "ami-12345"
  instance_type          = "t2.micro"
  subnet_id              = aws_subnet.public.id
  vpc_security_group_ids = [aws_security_group.web.id]
  iam_instance_profile   = aws_iam_instance_profile.ec2_profile.name
  
  # Explicit dependencies: ensure network is ready
  depends_on = [
    aws_route_table_association.public,
    aws_internet_gateway.main,
    aws_iam_instance_profile.ec2_profile
  ]
  
  tags = {
    Name = "web-server"
  }
}
```

### Dependency Order

```
Creation Order:
1. aws_vpc.main
2. aws_internet_gateway.main (depends on VPC)
3. aws_subnet.public (depends on VPC)
4. aws_route_table.public (depends on VPC)
5. aws_security_group.web (depends on VPC)
6. aws_iam_role.ec2_role (independent)
7. aws_route.public_internet (depends on RT + IGW)
8. aws_iam_role_policy.ec2_policy (depends on role)
9. aws_route_table_association.public (depends on RT + Subnet)
10. aws_iam_instance_profile.ec2_profile (depends on policy)
11. aws_instance.web (depends on all above)

Destruction Order: Reverse of creation
```

### Best Practices

1. **Let Terraform handle implicit dependencies:**
   ```hcl
   # ✅ Good - automatic dependency
   subnet_id = aws_subnet.public.id
   
   # ❌ Bad - unnecessary depends_on
   depends_on = [aws_subnet.public]
   ```

2. **Use depends_on only when necessary:**
   ```hcl
   # ✅ Good - needed for hidden dependency
   depends_on = [aws_iam_role_policy.example]
   ```

3. **Document why depends_on is needed:**
   ```hcl
   resource "aws_instance" "web" {
     # ...
     
     # depends_on required because IAM is eventually consistent
     # and instance profile needs policies fully attached
     depends_on = [aws_iam_role_policy.ec2_policy]
   }
   ```

### Key Takeaways

📌 **Remember:**
- Terraform auto-detects implicit dependencies
- Use depends_on for hidden dependencies
- Common use case: IAM eventual consistency
- Multiple dependencies: `depends_on = [a, b, c]`
- Affects creation and destruction order
- Use `terraform graph` to visualize dependencies
- Only use when implicit dependencies aren't enough

---

## Section 25: Lifecycle Rules

### What You'll Learn
- Lifecycle meta-argument
- create_before_destroy
- prevent_destroy
- ignore_changes
- replace_triggered_by
- Common use cases

### Lifecycle Meta-Argument

**Controls resource behavior:**

```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  lifecycle {
    create_before_destroy = true
    prevent_destroy       = false
    ignore_changes        = []
  }
}
```

### create_before_destroy

**Default behavior (destroy then create):**
```
1. Destroy old resource
2. Create new resource
3. ❌ Downtime during replacement
```

**With create_before_destroy:**
```
1. Create new resource
2. Update dependencies
3. Destroy old resource
4. ✅ No downtime
```

```hcl
resource "aws_launch_template" "app" {
  name_prefix   = "app-"
  image_id      = "ami-12345"
  instance_type = "t2.micro"
  
  lifecycle {
    create_before_destroy = true
  }
}

resource "aws_autoscaling_group" "app" {
  launch_template {
    id      = aws_launch_template.app.id
    version = "$Latest"
  }
  
  min_size = 1
  max_size = 3
  
  lifecycle {
    create_before_destroy = true
  }
}
```

### prevent_destroy

**Protect critical resources from deletion:**

```hcl
resource "aws_s3_bucket" "important_data" {
  bucket = "critical-data-bucket"
  
  lifecycle {
    prevent_destroy = true
  }
}

# Attempting terraform destroy will fail:
# Error: Instance cannot be destroyed
```

**Use for:**
- Production databases
- State storage buckets
- Critical data stores

```hcl
resource "aws_db_instance" "production" {
  identifier     = "prod-db"
  engine         = "postgres"
  instance_class = "db.t3.large"
  
  lifecycle {
    prevent_destroy = true
  }
}
```

### ignore_changes

**Ignore specific attribute changes:**

```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Name = "web-server"
  }
  
  lifecycle {
    ignore_changes = [
      tags,           # Ignore all tag changes
      user_data,      # Ignore user_data changes
    ]
  }
}
```

**Ignore all changes:**
```hcl
resource "aws_instance" "managed_elsewhere" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  lifecycle {
    ignore_changes = all
  }
}
```

**Common use cases:**

1. **Auto-scaling group size:**
```hcl
resource "aws_autoscaling_group" "app" {
  desired_capacity = 2
  min_size         = 1
  max_size         = 10
  
  lifecycle {
    ignore_changes = [desired_capacity]  # Let ASG manage this
  }
}
```

2. **AMI updates:**
```hcl
resource "aws_instance" "web" {
  ami           = data.aws_ami.latest.id
  instance_type = "t2.micro"
  
  lifecycle {
    ignore_changes = [ami]  # Prevent replacement on AMI update
  }
}
```

3. **Tags managed by other systems:**
```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Name = "web-server"
  }
  
  lifecycle {
    ignore_changes = [
      tags["LastBackup"],    # Managed by backup system
      tags["UpdatedBy"],     # Managed by other tools
    ]
  }
}
```

### replace_triggered_by

**Force replacement when another resource changes:**

```hcl
resource "aws_ami_from_instance" "example" {
  name               = "app-ami-${timestamp()}"
  source_instance_id = aws_instance.example.id
}

resource "aws_instance" "app" {
  ami           = aws_ami_from_instance.example.id
  instance_type = "t2.micro"
  
  lifecycle {
    replace_triggered_by = [
      aws_ami_from_instance.example
    ]
  }
}
```

### Combining Lifecycle Rules

```hcl
resource "aws_launch_template" "app" {
  name_prefix   = "app-"
  image_id      = var.ami_id
  instance_type = var.instance_type
  
  lifecycle {
    create_before_destroy = true
    ignore_changes        = [image_id]  # Ignore AMI changes
  }
}
```

### Complete Example: Zero-Downtime Deployment

```hcl
# Launch Template with versioning
resource "aws_launch_template" "app" {
  name_prefix   = "app-"
  image_id      = data.aws_ami.latest.id
  instance_type = "t2.micro"
  
  user_data = base64encode(templatefile("user_data.sh", {
    version = var.app_version
  }))
  
  lifecycle {
    create_before_destroy = true
  }
}

# Auto Scaling Group
resource "aws_autoscaling_group" "app" {
  name = "app-asg-${aws_launch_template.app.latest_version}"
  
  launch_template {
    id      = aws_launch_template.app.id
    version = "$Latest"
  }
  
  min_size         = 2
  max_size         = 10
  desired_capacity = 2
  
  health_check_type         = "ELB"
  health_check_grace_period = 300
  
  vpc_zone_identifier = aws_subnet.private[*].id
  target_group_arns   = [aws_lb_target_group.app.arn]
  
  lifecycle {
    create_before_destroy = true
    ignore_changes        = [desired_capacity]  # Let ASG manage
  }
  
  instance_refresh {
    strategy = "Rolling"
    preferences {
      min_healthy_percentage = 50
    }
  }
}

# Load Balancer Target Group
resource "aws_lb_target_group" "app" {
  name     = "app-tg"
  port     = 80
  protocol = "HTTP"
  vpc_id   = aws_vpc.main.id
  
  health_check {
    path                = "/health"
    healthy_threshold   = 2
    unhealthy_threshold = 2
    timeout             = 5
    interval            = 30
  }
  
  lifecycle {
    create_before_destroy = true
  }
}
```

### Example: Protected Database

```hcl
resource "aws_db_instance" "production" {
  identifier     = "prod-db"
  engine         = "postgres"
  engine_version = "14.5"
  instance_class = "db.t3.large"
  
  allocated_storage = 100
  storage_encrypted = true
  
  username = "admin"
  password = var.db_password
  
  backup_retention_period = 30
  backup_window           = "03:00-04:00"
  maintenance_window      = "mon:04:00-mon:05:00"
  
  lifecycle {
    prevent_destroy = true
    
    ignore_changes = [
      password,  # Don't replace on password change
    ]
  }
}
```

### Example: Blue-Green Deployment

```hcl
variable "active_color" {
  type    = string
  default = "blue"
  
  validation {
    condition     = contains(["blue", "green"], var.active_color)
    error_message = "Must be 'blue' or 'green'."
  }
}

locals {
  blue_weight  = var.active_color == "blue" ? 100 : 0
  green_weight = var.active_color == "green" ? 100 : 0
}

# Blue environment
resource "aws_instance" "blue" {
  count = 2
  
  ami           = var.blue_ami
  instance_type = "t2.micro"
  
  lifecycle {
    create_before_destroy = true
    ignore_changes        = [ami]
  }
  
  tags = {
    Color = "blue"
  }
}

# Green environment
resource "aws_instance" "green" {
  count = 2
  
  ami           = var.green_ami
  instance_type = "t2.micro"
  
  lifecycle {
    create_before_destroy = true
    ignore_changes        = [ami]
  }
  
  tags = {
    Color = "green"
  }
}

# Load Balancer with weighted routing
resource "aws_lb_listener_rule" "blue" {
  listener_arn = aws_lb_listener.main.arn
  
  action {
    type             = "forward"
    target_group_arn = aws_lb_target_group.blue.arn
    forward {
      target_group {
        arn    = aws_lb_target_group.blue.arn
        weight = local.blue_weight
      }
      target_group {
        arn    = aws_lb_target_group.green.arn
        weight = local.green_weight
      }
    }
  }
  
  condition {
    path_pattern {
      values = ["/*"]
    }
  }
}
```

### Best Practices

1. **Use create_before_destroy for zero-downtime:**
   ```hcl
   lifecycle {
     create_before_destroy = true
   }
   ```

2. **Protect production resources:**
   ```hcl
   lifecycle {
     prevent_destroy = true
   }
   ```

3. **Ignore externally managed attributes:**
   ```hcl
   lifecycle {
     ignore_changes = [desired_capacity, tags]
   }
   ```

4. **Document lifecycle decisions:**
   ```hcl
   resource "aws_instance" "web" {
     # ...
     
     lifecycle {
       # Prevent downtime during AMI updates
       create_before_destroy = true
       
       # AMI updates are managed through separate process
       ignore_changes = [ami]
     }
   }
   ```

### Key Takeaways

📌 **Remember:**
- `create_before_destroy` = Zero downtime deployments
- `prevent_destroy` = Protect critical resources
- `ignore_changes` = Ignore specific attribute changes
- `replace_triggered_by` = Force replacement on dependency change
- Can combine multiple lifecycle rules
- Use for production safety and availability

---

**🎉 Congratulations!** You've completed Part 5: Advanced Resource Management!

---

# Part 6: Multi-Environment Management

---

## Section 26: Introduction to Workspaces

### What You'll Learn
- What are Terraform workspaces
- Default workspace
- Use cases for workspaces
- Workspace commands
- Alternatives to workspaces

### What are Workspaces?

**Workspace** = Separate state file for same configuration

**Analogy:**
- Code = House blueprint
- Workspaces = Different houses from same blueprint
- Each has its own state (furniture, colors, etc.)

### Default Workspace

```bash
# Check current workspace
terraform workspace show
# Output: default

# List all workspaces
terraform workspace list
# Output:
# * default
```

### Why Use Workspaces?

**Problem without workspaces:**
```
Need separate environments:
- dev/
  ├── main.tf
  └── terraform.tfstate
- staging/
  ├── main.tf  (duplicate code)
  └── terraform.tfstate
- prod/
  ├── main.tf  (duplicate code)
  └── terraform.tfstate
```

**Solution with workspaces:**
```
Single directory:
- main.tf (one set of code)
- terraform.tfstate.d/
  ├── dev/terraform.tfstate
  ├── staging/terraform.tfstate
  └── prod/terraform.tfstate
```

### Workspace Commands

```bash
# List workspaces
terraform workspace list

# Create new workspace
terraform workspace new dev

# Switch to workspace
terraform workspace select dev

# Show current workspace
terraform workspace show

# Delete workspace
terraform workspace delete dev
```

### Using Current Workspace in Code

```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  tags = {
    Name        = "web-${terraform.workspace}"
    Environment = terraform.workspace
  }
}

output "workspace" {
  value = terraform.workspace
}
```

### Workspace-Specific Configuration

```hcl
locals {
  workspace_config = {
    dev = {
      instance_type = "t2.micro"
      instance_count = 1
    }
    staging = {
      instance_type = "t2.small"
      instance_count = 2
    }
    prod = {
      instance_type = "t2.large"
      instance_count = 5
    }
  }
  
  config = local.workspace_config[terraform.workspace]
}

resource "aws_instance" "app" {
  count = local.config.instance_count
  
  ami           = "ami-12345"
  instance_type = local.config.instance_type
  
  tags = {
    Name = "${terraform.workspace}-app-${count.index + 1}"
  }
}
```

### Workspace Workflow

```bash
# 1. Create dev environment
terraform workspace new dev
terraform apply

# 2. Create staging environment
terraform workspace new staging
terraform apply

# 3. Create production environment
terraform workspace new prod
terraform apply

# 4. Switch between environments
terraform workspace select dev
terraform plan

terraform workspace select prod
terraform plan
```

### State Storage with Workspaces

**Local state:**
```
project/
├── main.tf
├── terraform.tfstate (default workspace)
└── terraform.tfstate.d/
    ├── dev/
    │   └── terraform.tfstate
    ├── staging/
    │   └── terraform.tfstate
    └── prod/
        └── terraform.tfstate
```

**Remote state (S3):**
```hcl
terraform {
  backend "s3" {
    bucket         = "my-state-bucket"
    key            = "project/terraform.tfstate"
    region         = "us-east-2"
    workspace_key_prefix = "workspaces"  # Optional
  }
}

# State file paths:
# workspaces/dev/project/terraform.tfstate
# workspaces/staging/project/terraform.tfstate
# workspaces/prod/project/terraform.tfstate
```

### Complete Workspace Example

```hcl
# variables.tf
variable "aws_region" {
  type    = string
  default = "us-east-2"
}

# locals.tf
locals {
  env_config = {
    dev = {
      instance_type  = "t2.micro"
      instance_count = 1
      db_instance    = "db.t3.micro"
      enable_backup  = false
    }
    staging = {
      instance_type  = "t2.small"
      instance_count = 2
      db_instance    = "db.t3.small"
      enable_backup  = true
    }
    prod = {
      instance_type  = "t2.large"
      instance_count = 5
      db_instance    = "db.t3.large"
      enable_backup  = true
    }
  }
  
  config = local.env_config[terraform.workspace]
  
  common_tags = {
    Environment = terraform.workspace
    ManagedBy   = "Terraform"
  }
}

# main.tf
provider "aws" {
  region = var.aws_region
  
  default_tags {
    tags = local.common_tags
  }
}

resource "aws_instance" "app" {
  count = local.config.instance_count
  
  ami           = data.aws_ami.amazon_linux.id
  instance_type = local.config.instance_type
  
  tags = {
    Name = "${terraform.workspace}-app-${count.index + 1}"
  }
}

resource "aws_db_instance" "main" {
  identifier     = "${terraform.workspace}-db"
  engine         = "postgres"
  instance_class = local.config.db_instance
  
  allocated_storage       = 20
  backup_retention_period = local.config.enable_backup ? 7 : 0
}

# outputs.tf
output "environment" {
  value = terraform.workspace
}

output "instance_count" {
  value = local.config.instance_count
}

output "instance_ips" {
  value = aws_instance.app[*].public_ip
}
```

### Usage

```bash
# Create and deploy to dev
terraform workspace new dev
terraform apply

# Create and deploy to staging
terraform workspace new staging
terraform apply

# Create and deploy to prod
terraform workspace new prod
terraform apply

# Check what's deployed
terraform workspace list
#   default
#   dev
#   staging
# * prod

# Switch to dev and make changes
terraform workspace select dev
terraform apply

# Destroy dev environment
terraform workspace select dev
terraform destroy

# Delete workspace (after destroying resources)
terraform workspace delete dev
```

### Workspace Limitations

**❌ Limitations:**
1. All workspaces share same backend
2. Can't have different configurations per workspace
3. Easy to accidentally work in wrong workspace
4. Not ideal for very different environments
5. Can't easily see which workspace is deployed

### Alternatives to Workspaces

#### 1. Separate Directories
```
environments/
├── dev/
│   ├── main.tf
│   ├── variables.tf
│   └── terraform.tfvars
├── staging/
│   ├── main.tf
│   ├── variables.tf
│   └── terraform.tfvars
└── prod/
    ├── main.tf
    ├── variables.tf
    └── terraform.tfvars
```

#### 2. Separate Branches
```bash
git checkout dev
terraform apply

git checkout staging
terraform apply

git checkout prod
terraform apply
```

#### 3. Terragrunt
```
Infrastructure-as-code tool that wraps Terraform
Better for complex multi-environment setups
```

### When to Use Workspaces

**✅ Use workspaces when:**
- Environments are very similar
- Same configuration, different scale
- Testing/development scenarios
- Small teams

**❌ Don't use workspaces when:**
- Environments very different
- Need different state backends
- Complex compliance requirements
- Large teams (easy to make mistakes)

### Key Takeaways

📌 **Remember:**
- Workspaces = Multiple state files, same code
- terraform.workspace = Current workspace name
- Each workspace has separate state
- Default workspace always exists
- Use for similar environments
- Consider alternatives for complex scenarios

---

## Section 27: Creating and Switching Workspaces

### What You'll Learn
- Creating workspaces
- Switching between workspaces
- Managing workspace state
- Best practices
- Common workflows

### Creating Workspaces

```bash
# Create new workspace
terraform workspace new dev

# Output:
# Created and switched to workspace "dev"!
#
# You're now on a new, empty workspace. Workspaces isolate their state,
# so if you run "terraform plan" Terraform will not see any existing state
# for this configuration.
```

### Switching Workspaces

```bash
# List all workspaces
terraform workspace list
# Output:
#   default
# * dev

# Switch to different workspace
terraform workspace select staging
# Output: Switched to workspace "staging"

# Try to switch to non-existent workspace
terraform workspace select nonexistent
# Error: Workspace "nonexistent" doesn't exist
```

### Create or Select Pattern

```bash
# Create if doesn't exist, otherwise switch
terraform workspace select dev 2>/dev/null || terraform workspace new dev
```

### Complete Workflow Example

**Step 1: Setup project**
```bash
mkdir terraform-workspaces
cd terraform-workspaces
```

**Step 2: Create configuration**

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
  
  default_tags {
    tags = {
      Environment = terraform.workspace
      ManagedBy   = "Terraform"
    }
  }
}

locals {
  config = {
    dev = {
      instance_type = "t2.micro"
      instance_count = 1
    }
    staging = {
      instance_type = "t2.small"
      instance_count = 2
    }
    prod = {
      instance_type = "t2.large"
      instance_count = 3
    }
  }
  
  current = local.config[terraform.workspace]
}

data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

resource "aws_instance" "app" {
  count = local.current.instance_count
  
  ami           = data.aws_ami.amazon_linux.id
  instance_type = local.current.instance_type
  
  tags = {
    Name = "${terraform.workspace}-app-${count.index + 1}"
  }
}

output "workspace" {
  value = terraform.workspace
}

output "instances" {
  value = {
    count = local.current.instance_count
    type  = local.current.instance_type
    ids   = aws_instance.app[*].id
    ips   = aws_instance.app[*].public_ip
  }
}
```

**Step 3: Deploy to dev**
```bash
# Initialize
terraform init

# Create dev workspace (auto-switches to it)
terraform workspace new dev

# Check current workspace
terraform workspace show
# Output: dev

# Plan
terraform plan
# Shows: 1 t2.micro instance to create

# Apply
terraform apply -auto-approve

# View outputs
terraform output
```

**Step 4: Deploy to staging**
```bash
# Create and switch to staging
terraform workspace new staging

# Check workspace
terraform workspace show
# Output: staging

# Apply
terraform apply -auto-approve
# Shows: 2 t2.small instances to create
```

**Step 5: Deploy to prod**
```bash
# Create and switch to prod
terraform workspace new prod

# Apply
terraform apply -auto-approve
# Shows: 3 t2.large instances to create
```

**Step 6: Manage environments**
```bash
# List all workspaces
terraform workspace list
# Output:
#   default
#   dev
#   staging
# * prod

# View prod resources
terraform workspace select prod
terraform state list

# View staging resources
terraform workspace select staging
terraform state list

# View dev resources
terraform workspace select dev
terraform state list
```

### Workspace Safety Checks

**Prevent accidental changes:**

```hcl
locals {
  allowed_workspaces = ["dev", "staging", "prod"]
}

# Validation
resource "null_resource" "workspace_validator" {
  count = contains(local.allowed_workspaces, terraform.workspace) ? 0 : 1
  
  triggers = {
    error = "ERROR: Invalid workspace '${terraform.workspace}'. Allowed: ${join(", ", local.allowed_workspaces)}"
  }
  
  lifecycle {
    precondition {
      condition     = contains(local.allowed_workspaces, terraform.workspace)
      error_message = "Workspace '${terraform.workspace}' is not allowed. Use: ${join(", ", local.allowed_workspaces)}"
    }
  }
}
```

### Workspace Prompt Setup

**Add to your shell profile:**

```bash
# ~/.bashrc or ~/.zshrc

# Show current Terraform workspace in prompt
tf_workspace() {
  if [ -d .terraform ]; then
    workspace=$(terraform workspace show 2>/dev/null)
    if [ -n "$workspace" ]; then
      echo "[tf:$workspace]"
    fi
  fi
}

# Update PS1
PS1='$(tf_workspace) '$PS1
```

**Result:**
```bash
[tf:prod] $ terraform apply
# Clear indicator you're in production!
```

### Scripted Workspace Management

**File: `deploy.sh`**
```bash
#!/bin/bash

set -e

WORKSPACE=$1

if [ -z "$WORKSPACE" ]; then
  echo "Usage: $0 <workspace>"
  echo "Example: $0 dev"
  exit 1
fi

# Allowed workspaces
ALLOWED_WORKSPACES=("dev" "staging" "prod")

if [[ ! " ${ALLOWED_WORKSPACES[@]} " =~ " ${WORKSPACE} " ]]; then
  echo "Error: Invalid workspace '$WORKSPACE'"
  echo "Allowed workspaces: ${ALLOWED_WORKSPACES[*]}"
  exit 1
fi

echo "Deploying to $WORKSPACE..."

# Create or select workspace
terraform workspace select "$WORKSPACE" 2>/dev/null || terraform workspace new "$WORKSPACE"

# Confirm with user for prod
if [ "$WORKSPACE" == "prod" ]; then
  read -p "Are you sure you want to deploy to PRODUCTION? (yes/no): " confirm
  if [ "$confirm" != "yes" ]; then
    echo "Deployment cancelled"
    exit 1
  fi
fi

# Plan
echo "Planning..."
terraform plan -out=tfplan

# Apply
echo "Applying..."
terraform apply tfplan

# Show outputs
echo "Deployment complete!"
terraform output

# Cleanup
rm tfplan
```

**Usage:**
```bash
chmod +x deploy.sh

# Deploy to dev
./deploy.sh dev

# Deploy to staging
./deploy.sh staging

# Deploy to prod (with confirmation)
./deploy.sh prod
```

### Workspace Best Practices

#### 1. Always Check Current Workspace

```bash
# Before any operation
terraform workspace show

# Or in scripts
CURRENT_WORKSPACE=$(terraform workspace show)
echo "Current workspace: $CURRENT_WORKSPACE"
```

#### 2. Use Workspace Validation

```hcl
variable "workspace_allowed" {
  type    = bool
  default = true
  
  validation {
    condition     = contains(["dev", "staging", "prod"], terraform.workspace)
    error_message = "Invalid workspace. Use: dev, staging, or prod"
  }
}
```

#### 3. Document Workspace Usage

```markdown
# README.md

## Workspaces

- `dev`: Development environment (1 t2.micro instance)
- `staging`: Staging environment (2 t2.small instances)
- `prod`: Production environment (3 t2.large instances)

### Deploy to environment

```bash
terraform workspace select <env>
terraform apply
```

### View environment

```bash
terraform workspace select <env>
terraform show
```
```

#### 4. Never Use Default Workspace

```bash
# Always create named workspaces
terraform workspace new dev

# Don't use:
# terraform apply  (in default workspace)
```

### Switching Workflow Patterns

#### Pattern 1: Manual Switching
```bash
terraform workspace select dev
terraform apply

terraform workspace select staging
terraform apply
```

#### Pattern 2: Script-Based
```bash
for env in dev staging prod; do
  terraform workspace select $env
  terraform plan
done
```

#### Pattern 3: CI/CD Pipeline
```yaml
# .github/workflows/terraform.yml
name: Terraform

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        workspace: [dev, staging]
    
    steps:
      - uses: actions/checkout@v2
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v1
      
      - name: Terraform Init
        run: terraform init
      
      - name: Select Workspace
        run: |
          terraform workspace select ${{ matrix.workspace }} || \
          terraform workspace new ${{ matrix.workspace }}
      
      - name: Terraform Plan
        run: terraform plan
      
      - name: Terraform Apply
        if: github.ref == 'refs/heads/main'
        run: terraform apply -auto-approve
```

### Deleting Workspaces

```bash
# 1. Switch away from workspace
terraform workspace select default

# 2. Destroy resources in workspace first
terraform workspace select dev
terraform destroy -auto-approve

# 3. Switch back and delete
terraform workspace select default
terraform workspace delete dev

# If resources still exist:
# Error: Workspace "dev" is not empty
```

**Force delete (dangerous!):**
```bash
# This deletes workspace state without destroying resources!
terraform workspace delete -force dev
```

### Key Takeaways

📌 **Remember:**
- Create: `terraform workspace new <name>`
- Switch: `terraform workspace select <name>`
- Show current: `terraform workspace show`
- List all: `terraform workspace list`
- Delete: `terraform workspace delete <name>` (after destroy)
- Always know which workspace you're in
- Use validation to prevent mistakes
- Add workspace to shell prompt
- Script deployments for safety

---

## Section 28: Environment-Specific Configurations

### What You'll Learn
- Structuring workspace configurations
- Environment-specific variables
- Using locals for configuration
- Workspace-based conditionals
- Best practices

### Configuration Structure

```hcl
locals {
  # Environment configurations
  environments = {
    dev = {
      # Infrastructure
      instance_type   = "t2.micro"
      instance_count  = 1
      db_instance     = "db.t3.micro"
      
      # Scaling
      min_size = 1
      max_size = 2
      
      # Features
      enable_backups     = false
      enable_monitoring  = false
      enable_encryption  = false
      
      # Costs
      backup_retention = 1
      
      # Network
      cidr_block = "10.0.0.0/16"
    }
    
    staging = {
      instance_type   = "t2.small"
      instance_count  = 2
      db_instance     = "db.t3.small"
      
      min_size = 2
      max_size = 4
      
      enable_backups     = true
      enable_monitoring  = true
      enable_encryption  = true
      
      backup_retention = 7
      
      cidr_block = "10.1.0.0/16"
    }
    
    prod = {
      instance_type   = "t2.large"
      instance_count  = 5
      db_instance     = "db.t3.large"
      
      min_size = 3
      max_size = 10
      
      enable_backups     = true
      enable_monitoring  = true
      enable_encryption  = true
      
      backup_retention = 30
      
      cidr_block = "10.2.0.0/16"
    }
  }
  
  # Get current environment config
  env = local.environments[terraform.workspace]
  
  # Common tags
  common_tags = {
    Environment = terraform.workspace
    ManagedBy   = "Terraform"
    Project     = "MyApp"
  }
}
```

### Complete Multi-Environment Example

**File: `locals.tf`**
```hcl
locals {
  environments = {
    dev = {
      # Compute
      instance_type  = "t2.micro"
      instance_count = 1
      
      # Database
      db_instance_class      = "db.t3.micro"
      db_allocated_storage   = 20
      db_multi_az            = false
      db_backup_retention    = 1
      
      # Network
      vpc_cidr           = "10.0.0.0/16"
      availability_zones = 2
      
      # Features
      enable_monitoring = false
      enable_backups    = false
      
      # Scaling
      asg_min = 1
      asg_max = 2
    }
    
    staging = {
      instance_type  = "t2.small"
      instance_count = 2
      
      db_instance_class      = "db.t3.small"
      db_allocated_storage   = 50
      db_multi_az            = false
      db_backup_retention    = 7
      
      vpc_cidr           = "10.1.0.0/16"
      availability_zones = 2
      
      enable_monitoring = true
      enable_backups    = true
      
      asg_min = 2
      asg_max = 4
    }
    
    prod = {
      instance_type  = "t2.large"
      instance_count = 5
      
      db_instance_class      = "db.t3.large"
      db_allocated_storage   = 100
      db_multi_az            = true
      db_backup_retention    = 30
      
      vpc_cidr           = "10.2.0.0/16"
      availability_zones = 3
      
      enable_monitoring = true
      enable_backups    = true
      
      asg_min = 3
      asg_max = 10
    }
  }
  
  env = local.environments[terraform.workspace]
  
  common_tags = {
    Environment = terraform.workspace
    ManagedBy   = "Terraform"
    Project     = "WebApp"
    CostCenter  = terraform.workspace == "prod" ? "Operations" : "Engineering"
  }
}
```

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
  
  backend "s3" {
    bucket         = "my-terraform-state"
    key            = "webapp/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true
    dynamodb_table = "terraform-locks"
  }
}

provider "aws" {
  region = "us-east-2"
  
  default_tags {
    tags = local.common_tags
  }
}

# Data Sources
data "aws_availability_zones" "available" {
  state = "available"
}

data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

# VPC
resource "aws_vpc" "main" {
  cidr_block           = local.env.vpc_cidr
  enable_dns_hostnames = true
  enable_dns_support   = true
  
  tags = {
    Name = "${terraform.workspace}-vpc"
  }
}

# Subnets
resource "aws_subnet" "public" {
  count = local.env.availability_zones
  
  vpc_id                  = aws_vpc.main.id
  cidr_block              = cidrsubnet(local.env.vpc_cidr, 8, count.index)
  availability_zone       = data.aws_availability_zones.available.names[count.index]
  map_public_ip_on_launch = true
  
  tags = {
    Name = "${terraform.workspace}-public-${count.index + 1}"
  }
}

# EC2 Instances
resource "aws_instance" "app" {
  count = local.env.instance_count
  
  ami           = data.aws_ami.amazon_linux.id
  instance_type = local.env.instance_type
  subnet_id     = element(aws_subnet.public[*].id, count.index)
  
  monitoring = local.env.enable_monitoring
  
  root_block_device {
    encrypted   = terraform.workspace == "prod"
    volume_size = terraform.workspace == "prod" ? 50 : 20
  }
  
  tags = {
    Name = "${terraform.workspace}-app-${count.index + 1}"
  }
}

# RDS Database
resource "aws_db_instance" "main" {
  identifier     = "${terraform.workspace}-db"
  engine         = "postgres"
  engine_version = "14.5"
  
  instance_class    = local.env.db_instance_class
  allocated_storage = local.env.db_allocated_storage
  storage_encrypted = terraform.workspace != "dev"
  
  multi_az               = local.env.db_multi_az
  backup_retention_period = local.env.db_backup_retention
  backup_window          = "03:00-04:00"
  maintenance_window     = "mon:04:00-mon:05:00"
  
  username = "admin"
  password = var.db_password
  
  skip_final_snapshot = terraform.workspace != "prod"
  
  tags = {
    Name = "${terraform.workspace}-database"
  }
}

# Auto Scaling Group (prod only)
resource "aws_launch_template" "app" {
  count = terraform.workspace == "prod" ? 1 : 0
  
  name_prefix   = "${terraform.workspace}-app-"
  image_id      = data.aws_ami.amazon_linux.id
  instance_type = local.env.instance_type
  
  monitoring {
    enabled = local.env.enable_monitoring
  }
}

resource "aws_autoscaling_group" "app" {
  count = terraform.workspace == "prod" ? 1 : 0
  
  name                = "${terraform.workspace}-asg"
  vpc_zone_identifier = aws_subnet.public[*].id
  
  min_size         = local.env.asg_min
  max_size         = local.env.asg_max
  desired_capacity = local.env.asg_min
  
  launch_template {
    id      = aws_launch_template.app[0].id
    version = "$Latest"
  }
  
  tag {
    key                 = "Name"
    value               = "${terraform.workspace}-asg-instance"
    propagate_at_launch = true
  }
}

# Backup (prod and staging only)
resource "aws_backup_plan" "main" {
  count = local.env.enable_backups ? 1 : 0
  
  name = "${terraform.workspace}-backup-plan"
  
  rule {
    rule_name         = "daily_backup"
    target_vault_name = "Default"
    schedule          = "cron(0 2 * * ? *)"
    
    lifecycle {
      delete_after = local.env.db_backup_retention
    }
  }
}
```

**File: `variables.tf`**
```hcl
variable "db_password" {
  description = "Database password"
  type        = string
  sensitive   = true
}
```

**File: `outputs.tf`**
```hcl
output "environment" {
  description = "Current environment"
  value       = terraform.workspace
}

output "vpc_id" {
  description = "VPC ID"
  value       = aws_vpc.main.id
}

output "vpc_cidr" {
  description = "VPC CIDR block"
  value       = aws_vpc.main.cidr_block
}

output "instance_count" {
  description = "Number of EC2 instances"
  value       = local.env.instance_count
}

output "instance_type" {
  description = "EC2 instance type"
  value       = local.env.instance_type
}

output "instance_ips" {
  description = "EC2 instance IPs"
  value       = aws_instance.app[*].public_ip
}

output "database_endpoint" {
  description = "Database endpoint"
  value       = aws_db_instance.main.endpoint
  sensitive   = true
}

output "features" {
  description = "Enabled features"
  value = {
    monitoring = local.env.enable_monitoring
    backups    = local.env.enable_backups
    multi_az   = local.env.db_multi_az
    encryption = terraform.workspace != "dev"
  }
}

output "configuration_summary" {
  description = "Environment configuration summary"
  value = {
    environment = terraform.workspace
    compute = {
      type  = local.env.instance_type
      count = local.env.instance_count
    }
    database = {
      class            = local.env.db_instance_class
      storage          = local.env.db_allocated_storage
      multi_az         = local.env.db_multi_az
      backup_retention = local.env.db_backup_retention
    }
    network = {
      vpc_cidr = local.env.vpc_cidr
      azs      = local.env.availability_zones
    }
  }
}
```

### Deployment

```bash
# Deploy to dev
terraform workspace new dev
terraform apply -var="db_password=devpass123"

# Deploy to staging
terraform workspace new staging
terraform apply -var="db_password=stagingpass456"

# Deploy to prod
terraform workspace new prod
terraform apply -var="db_password=prodpass789"

# View configuration
terraform workspace select dev
terraform output configuration_summary

terraform workspace select prod
terraform output configuration_summary
```

### Environment-Specific tfvars

**Alternative approach using tfvars files:**

**File: `dev.tfvars`**
```hcl
instance_type  = "t2.micro"
instance_count = 1
db_instance    = "db.t3.micro"
enable_backups = false
```

**File: `prod.tfvars`**
```hcl
instance_type  = "t2.large"
instance_count = 5
db_instance    = "db.t3.large"
enable_backups = true
```

**Usage:**
```bash
terraform workspace select dev
terraform apply -var-file="dev.tfvars"

terraform workspace select prod
terraform apply -var-file="prod.tfvars"
```

### Key Takeaways

📌 **Remember:**
- Use locals for environment configurations
- Access with `local.env.property`
- Different configs per workspace
- Conditionally create resources based on workspace
- Validate workspace before deployment
- Document environment differences
- Use consistent naming patterns

---

## Section 29: Workspace Best Practices

### What You'll Learn
- Workspace naming conventions
- Safety mechanisms
- Documentation
- CI/CD integration
- Common pitfalls

### Naming Conventions

**Good workspace names:**
```bash
✅ dev
✅ staging
✅ prod
✅ feature-new-api
✅ hotfix-bug-123
```

**Bad workspace names:**
```bash
❌ production (too long)
❌ John_test (personal names)
❌ temp123 (unclear purpose)
❌ PROD (inconsistent casing)
```

### Safety Mechanisms

#### 1. Workspace Validation

```hcl
locals {
  allowed_workspaces = ["dev", "staging", "prod"]
  
  # Validate workspace
  workspace_valid = contains(local.allowed_workspaces, terraform.workspace)
}

resource "null_resource" "workspace_check" {
  lifecycle {
    precondition {
      condition     = local.workspace_valid
      error_message = "Invalid workspace: ${terraform.workspace}. Allowed: ${join(", ", local.allowed_workspaces)}"
    }
  }
}
```

#### 2. Production Safeguards

```hcl
locals {
  is_production = terraform.workspace == "prod"
  
  # Require specific tags in production
  required_tags = local.is_production ? {
    CostCenter = "Operations"
    Owner      = "DevOps-Team"
    Compliance = "Required"
  } : {}
}

resource "aws_instance" "app" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
  
  # Prevent accidental termination in prod
  disable_api_termination = local.is_production
  
  tags = merge(
    local.required_tags,
    { Name = "${terraform.workspace}-app" }
  )
  
  lifecycle {
    # Protect prod resources
    prevent_destroy = local.is_production
  }
}
```

#### 3. Approval Requirements

**File: `terraform.sh`**
```bash
#!/bin/bash

WORKSPACE=$(terraform workspace show)

if [ "$WORKSPACE" == "prod" ]; then
  echo "⚠️  WARNING: Deploying to PRODUCTION"
  echo "Current workspace: $WORKSPACE"
  echo ""
  read -p "Type 'DEPLOY TO PRODUCTION' to continue: " confirm
  
  if [ "$confirm" != "DEPLOY TO PRODUCTION" ]; then
    echo "Deployment cancelled"
    exit 1
  fi
fi

terraform "$@"
```

### Documentation

**File: `README.md`**
```markdown
# Infrastructure - Workspaces

## Available Environments

| Workspace | Purpose | Instance Type | Count | Database |
|-----------|---------|---------------|-------|----------|
| dev       | Development | t2.micro | 1 | db.t3.micro |
| staging   | Pre-production | t2.small | 2 | db.t3.small |
| prod      | Production | t2.large | 5 | db.t3.large |

## Usage

### Switch to environment
```bash
terraform workspace select <env>
```

### View current workspace
```bash
terraform workspace show
```

### Deploy to environment
```bash
# Dev
terraform workspace select dev
terraform apply -auto-approve

# Staging (requires approval)
terraform workspace select staging
terraform apply

# Production (requires manual approval)
terraform workspace select prod
terraform plan
# Review plan carefully
terraform apply
```

## Safety Features

- ✅ Workspace validation
- ✅ Production safeguards
- ✅ Prevent destroy in production
- ✅ Required approval for prod changes

## State Management

- Backend: S3 (my-terraform-state)
- Locking: DynamoDB (terraform-locks)
- Encryption: Enabled
- Versioning: Enabled
```

### CI/CD Integration

**File: `.github/workflows/terraform.yml`**
```yaml
name: Terraform

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

env:
  AWS_REGION: us-east-2

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v1
      
      - name: Terraform Format Check
        run: terraform fmt -check -recursive
      
      - name: Terraform Init
        run: terraform init
      
      - name: Terraform Validate
        run: terraform validate

  plan-dev:
    needs: validate
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/develop'
    steps:
      - uses: actions/checkout@v2
      
      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ env.AWS_REGION }}
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v1
      
      - name: Terraform Init
        run: terraform init
      
      - name: Select Workspace
        run: terraform workspace select dev || terraform workspace new dev
      
      - name: Terraform Plan
        run: terraform plan -out=tfplan
      
      - name: Upload Plan
        uses: actions/upload-artifact@v2
        with:
          name: tfplan-dev
          path: tfplan

  apply-dev:
    needs: plan-dev
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/develop'
    environment: development
    steps:
      - uses: actions/checkout@v2
      
      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ env.AWS_REGION }}
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v1
      
      - name: Terraform Init
        run: terraform init
      
      - name: Select Workspace
        run: terraform workspace select dev
      
      - name: Download Plan
        uses: actions/download-artifact@v2
        with:
          name: tfplan-dev
      
      - name: Terraform Apply
        run: terraform apply tfplan

  plan-prod:
    needs: validate
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
      - uses: actions/checkout@v2
      
      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ env.AWS_REGION }}
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v1
      
      - name: Terraform Init
        run: terraform init
      
      - name: Select Workspace
        run: terraform workspace select prod || terraform workspace new prod
      
      - name: Terraform Plan
        run: terraform plan -out=tfplan
      
      - name: Upload Plan
        uses: actions/upload-artifact@v2
        with:
          name: tfplan-prod
          path: tfplan

  apply-prod:
    needs: plan-prod
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    environment: production  # Requires manual approval
    steps:
      - uses: actions/checkout@v2
      
      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ env.AWS_REGION }}
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v1
      
      - name: Terraform Init
        run: terraform init
      
      - name: Select Workspace
        run: terraform workspace select prod
      
      - name: Download Plan
        uses: actions/download-artifact@v2
        with:
          name: tfplan-prod
      
      - name: Terraform Apply
        run: terraform apply tfplan
```

### Common Pitfalls

#### Pitfall 1: Forgetting Current Workspace

```bash
# ❌ Bad - no check
terraform destroy

# ✅ Good - check first
terraform workspace show
terraform destroy
```

#### Pitfall 2: Using Default Workspace

```bash
# ❌ Bad - using default
terraform apply

# ✅ Good - use named workspace
terraform workspace select dev
terraform apply
```

#### Pitfall 3: Not Validating Workspace

```hcl
# ❌ Bad - no validation
locals {
  config = local.environments[terraform.workspace]
}

# ✅ Good - with validation
locals {
  allowed_workspaces = ["dev", "staging", "prod"]
}

resource "null_resource" "validate" {
  lifecycle {
    precondition {
      condition     = contains(local.allowed_workspaces, terraform.workspace)
      error_message = "Invalid workspace!"
    }
  }
}
```

### Monitoring and Alerts

**Add tags for monitoring:**

```hcl
locals {
  common_tags = {
    Environment = terraform.workspace
    ManagedBy   = "Terraform"
    AlertEmail  = terraform.workspace == "prod" ? "ops@company.com" : "dev@company.com"
    AlertLevel  = terraform.workspace == "prod" ? "critical" : "warning"
  }
}
```

### Key Takeaways

📌 **Remember:**
- Use consistent naming (dev, staging, prod)
- Validate workspaces before operations
- Add safeguards for production
- Document all workspaces
- Integrate with CI/CD
- Always check current workspace
- Never use default workspace in production
- Add approval gates for prod changes

---

## Section 30: Alternative - Directory-Based Environments

### What You'll Learn
- Directory structure for environments
- Advantages over workspaces
- Shared modules
- When to use each approach
- Migration strategies

### Directory Structure

```
terraform/
├── modules/
│   ├── networking/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   └── outputs.tf
│   └── compute/
│       ├── main.tf
│       ├── variables.tf
│       └── outputs.tf
├── environments/
│   ├── dev/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   ├── terraform.tfvars
│   │   └── backend.tf
│   ├── staging/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   ├── terraform.tfvars
│   │   └── backend.tf
│   └── prod/
│       ├── main.tf
│       ├── variables.tf
│       ├── terraform.tfvars
│       └── backend.tf
└── README.md
```

### Shared Modules

**File: `modules/networking/main.tf`**
```hcl
resource "aws_vpc" "main" {
  cidr_block           = var.vpc_cidr
  enable_dns_hostnames = true
  enable_dns_support   = true
  
  tags = merge(
    var.common_tags,
    { Name = "${var.environment}-vpc" }
  )
}

resource "aws_subnet" "public" {
  count = var.az_count
  
  vpc_id                  = aws_vpc.main.id
  cidr_block              = cidrsubnet(var.vpc_cidr, 8, count.index)
  availability_zone       = data.aws_availability_zones.available.names[count.index]
  map_public_ip_on_launch = true
  
  tags = merge(
    var.common_tags,
    { Name = "${var.environment}-public-${count.index + 1}" }
  )
}

data "aws_availability_zones" "available" {
  state = "available"
}
```

**File: `modules/networking/variables.tf`**
```hcl
variable "environment" {
  type = string
}

variable "vpc_cidr" {
  type = string
}

variable "az_count" {
  type    = number
  default = 2
}

variable "common_tags" {
  type = map(string)
}
```

**File: `modules/networking/outputs.tf`**
```hcl
output "vpc_id" {
  value = aws_vpc.main.id
}

output "public_subnet_ids" {
  value = aws_subnet.public[*].id
}
```

### Environment-Specific Configuration

**File: `environments/dev/main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = var.aws_region
  
  default_tags {
    tags = local.common_tags
  }
}

locals {
  environment = "dev"
  
  common_tags = {
    Environment = local.environment
    ManagedBy   = "Terraform"
    Project     = "WebApp"
  }
}

module "networking" {
  source = "../../modules/networking"
  
  environment  = local.environment
  vpc_cidr     = "10.0.0.0/16"
  az_count     = 2
  common_tags  = local.common_tags
}

module "compute" {
  source = "../../modules/compute"
  
  environment       = local.environment
  instance_type     = "t2.micro"
  instance_count    = 1
  vpc_id            = module.networking.vpc_id
  subnet_ids        = module.networking.public_subnet_ids
  common_tags       = local.common_tags
}
```

**File: `environments/dev/variables.tf`**
```hcl
variable "aws_region" {
  type    = string
  default = "us-east-2"
}
```

**File: `environments/dev/terraform.tfvars`**
```hcl
aws_region = "us-east-2"
```

**File: `environments/dev/backend.tf`**
```hcl
terraform {
  backend "s3" {
    bucket         = "my-terraform-state"
    key            = "dev/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true
    dynamodb_table = "terraform-locks"
  }
}
```

**File: `environments/prod/main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = var.aws_region
  
  default_tags {
    tags = local.common_tags
  }
}

locals {
  environment = "prod"
  
  common_tags = {
    Environment = local.environment
    ManagedBy   = "Terraform"
    Project     = "WebApp"
    CostCenter  = "Operations"
  }
}

module "networking" {
  source = "../../modules/networking"
  
  environment  = local.environment
  vpc_cidr     = "10.2.0.0/16"
  az_count     = 3
  common_tags  = local.common_tags
}

module "compute" {
  source = "../../modules/compute"
  
  environment       = local.environment
  instance_type     = "t2.large"
  instance_count    = 5
  vpc_id            = module.networking.vpc_id
  subnet_ids        = module.networking.public_subnet_ids
  common_tags       = local.common_tags
}
```

### Deployment

```bash
# Deploy to dev
cd environments/dev
terraform init
terraform apply

# Deploy to prod
cd environments/prod
terraform init
terraform apply
```

### Comparison: Workspaces vs Directories

| Feature | Workspaces | Directories |
|---------|-----------|-------------|
| Same code | ✅ Yes | ❌ No (can use modules) |
| Separate state | ✅ Yes | ✅ Yes |
| Different configs | Limited | ✅ Full flexibility |
| Accidentally apply wrong env | ⚠️ Easy | ✅ Harder (different dirs) |
| CI/CD integration | Medium | ✅ Easy |
| Code duplication | ✅ None | ⚠️ Some |
| Complexity | ✅ Simple | ⚠️ More complex |
| Best for | Similar envs | Different envs |

### When to Use Each

**Use Workspaces when:**
- ✅ Environments are very similar
- ✅ Same configuration, different scale
- ✅ Simple setup preferred
- ✅ Small team

**Use Directories when:**
- ✅ Environments significantly different
- ✅ Need different providers/versions
- ✅ Strict separation required
- ✅ Large team
- ✅ Complex compliance requirements
- ✅ Production needs extra protection

### Hybrid Approach

```
terraform/
├── modules/           # Shared modules
├── environments/
│   ├── dev/          # Dev directory
│   │   └── ...       # Uses workspaces internally
│   └── prod/         # Prod directory (strictly separated)
│       └── ...
```

### Key Takeaways

📌 **Remember:**
- Directories = Complete separation
- Workspaces = Same code, different state
- Use modules to share code
- Directories safer for production
- Workspaces simpler for similar environments
- Can combine both approaches
- Choose based on team size and requirements

---

**🎉 Congratulations!** You've completed Part 6: Multi-Environment Management!

---

## Part 7: Modules

---

## Section 31: Understanding Terraform Modules

### What You'll Learn
- What modules are and why use them
- Module structure
- Root vs child modules
- Module benefits
- Real-world use cases

### What Are Modules?

**Simple Analogy:**
Think of modules like Lego sets:
- 🧱 Each set (module) contains pieces that work together
- 📦 You can reuse the same set to build multiple things
- 🔧 Sets can be combined to build bigger projects

### Module Benefits

**1. Reusability**
```
Without modules:
- Copy-paste code for each environment
- 1000 lines × 3 environments = 3000 lines

With modules:
- Write once, use everywhere
- 1000 lines + 50 lines config × 3 = 1150 lines
```

**2. Consistency**
```
Without modules:
- Dev: t2.micro, staging: t2.small, prod: t2.large
- Each configured slightly different
- Hard to maintain consistency

With modules:
- Same base configuration
- Only variables change
- Consistent across all environments
```

**3. Encapsulation**
```
Module hides complexity:
- Input: instance_type = "t2.micro"
- Module handles: security groups, networking, monitoring, backups
- Output: instance_id, public_ip
```

### Module Structure

**Basic module:**
```
module/
├── main.tf        # Resources
├── variables.tf   # Input variables
├── outputs.tf     # Output values
└── README.md      # Documentation
```

**Complete module:**
```
module/
├── main.tf
├── variables.tf
├── outputs.tf
├── versions.tf    # Provider requirements
├── README.md
├── examples/      # Usage examples
│   ├── basic/
│   └── complete/
└── tests/         # Module tests
```

### Root vs Child Modules

```
project/
├── main.tf        ← Root module (your main config)
├── variables.tf
├── outputs.tf
└── modules/
    └── web-server/  ← Child module
        ├── main.tf
        ├── variables.tf
        └── outputs.tf
```

**Root Module:**
- Your main Terraform configuration
- Calls other modules
- Entry point for `terraform apply`

**Child Module:**
- Reusable component
- Called by root or other modules
- Isolated functionality

### Simple Module Example

**File: `modules/web-server/main.tf`**
```hcl
# Input comes from variables.tf
resource "aws_instance" "web" {
  ami           = var.ami_id
  instance_type = var.instance_type
  
  tags = {
    Name = var.server_name
  }
}

resource "aws_security_group" "web" {
  name = "${var.server_name}-sg"
  
  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

**File: `modules/web-server/variables.tf`**
```hcl
variable "ami_id" {
  type        = string
  description = "AMI ID for the instance"
}

variable "instance_type" {
  type        = string
  description = "Instance type"
  default     = "t2.micro"
}

variable "server_name" {
  type        = string
  description = "Name for the server"
}
```

**File: `modules/web-server/outputs.tf`**
```hcl
output "instance_id" {
  value       = aws_instance.web.id
  description = "ID of the EC2 instance"
}

output "public_ip" {
  value       = aws_instance.web.public_ip
  description = "Public IP address"
}
```

### Using the Module

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

# Call the module
module "dev_server" {
  source = "./modules/web-server"
  
  ami_id        = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  server_name   = "dev-web"
}

module "prod_server" {
  source = "./modules/web-server"
  
  ami_id        = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.large"
  server_name   = "prod-web"
}

# Use module outputs
output "dev_ip" {
  value = module.dev_server.public_ip
}

output "prod_ip" {
  value = module.prod_server.public_ip
}
```

### Workflow

```bash
# Initialize (downloads modules)
terraform init

# Outputs:
# Initializing modules...
# - dev_server in modules/web-server
# - prod_server in modules/web-server

# Plan
terraform plan

# Apply
terraform apply

# View outputs
terraform output dev_ip
terraform output prod_ip
```

### Module Data Flow

```
┌─────────────────────────────────┐
│ Root Module (main.tf)           │
│                                 │
│ module "web" {                  │
│   source = "./modules/web"      │
│   ────────────────────────────► │
│   instance_type = "t2.micro" ◄─┐│
│   server_name = "my-server"    ││
│ }                               ││
│                                 ││
│ output "ip" {                   ││
│   value = module.web.public_ip◄─┘│
│ }                               │
└─────────────────────────────────┘
          │           ▲
          │ Input     │ Output
          ▼           │
┌─────────────────────────────────┐
│ Child Module (modules/web)      │
│                                 │
│ variable "instance_type" {} ◄───┤
│ variable "server_name" {}       │
│                                 │
│ resource "aws_instance" "web" { │
│   instance_type = var.instance_type
│   ...                           │
│ }                               │
│                                 │
│ output "public_ip" { ────────────►
│   value = aws_instance.web.public_ip
│ }                               │
└─────────────────────────────────┘
```

### Real-World Use Cases

#### 1. VPC Module
```hcl
module "vpc" {
  source = "./modules/vpc"
  
  name     = "production"
  cidr     = "10.0.0.0/16"
  azs      = ["us-east-2a", "us-east-2b"]
  public_subnets = ["10.0.1.0/24", "10.0.2.0/24"]
}
```

#### 2. RDS Module
```hcl
module "database" {
  source = "./modules/rds"
  
  identifier        = "myapp-db"
  engine            = "postgres"
  instance_class    = "db.t3.micro"
  allocated_storage = 20
}
```

#### 3. ALB Module
```hcl
module "load_balancer" {
  source = "./modules/alb"
  
  name     = "app-lb"
  vpc_id   = module.vpc.vpc_id
  subnets  = module.vpc.public_subnets
}
```

### Key Takeaways

📌 **Remember:**
- Modules = Reusable Terraform code
- Structure: main.tf, variables.tf, outputs.tf
- Call modules with `module` block
- Pass inputs via variables
- Get outputs via `module.<name>.<output>`
- Use modules for consistency and reusability

---

## Section 32: Using Pre-Built Modules from Registry

### What You'll Learn
- Terraform Registry overview
- Finding modules
- Using public modules
- Module versioning
- Best practices

### Terraform Registry

**URL:** https://registry.terraform.io

```
Registry contains:
- 📦 Official HashiCorp modules
- 🌟 Verified partner modules  
- 👥 Community modules
- 📚 Documentation and examples
```

### Finding Modules

**Search for "VPC":**
1. Go to registry.terraform.io
2. Search "vpc"
3. Filter by provider (AWS)
4. Look for verified badge ✓

**Popular AWS modules:**
- terraform-aws-modules/vpc/aws
- terraform-aws-modules/ec2-instance/aws
- terraform-aws-modules/rds/aws
- terraform-aws-modules/security-group/aws

### Using Registry Modules

**Example 1: VPC Module**

```hcl
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "5.1.2"
  
  name = "my-vpc"
  cidr = "10.0.0.0/16"
  
  azs             = ["us-east-2a", "us-east-2b", "us-east-2c"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24", "10.0.103.0/24"]
  
  enable_nat_gateway = true
  enable_vpn_gateway = false
  
  tags = {
    Environment = "dev"
    Terraform   = "true"
  }
}
```

**Deploy:**
```bash
terraform init    # Downloads module from registry
terraform apply
```

### Complete Example with Multiple Registry Modules

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

# VPC Module from Registry
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "5.1.2"
  
  name = "webapp-vpc"
  cidr = "10.0.0.0/16"
  
  azs             = ["us-east-2a", "us-east-2b"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24"]
  
  enable_nat_gateway   = true
  single_nat_gateway   = true
  enable_dns_hostnames = true
  
  tags = {
    Environment = "dev"
  }
}

# Security Group Module from Registry
module "web_sg" {
  source  = "terraform-aws-modules/security-group/aws"
  version = "5.1.0"
  
  name        = "web-server-sg"
  description = "Security group for web servers"
  vpc_id      = module.vpc.vpc_id
  
  ingress_cidr_blocks = ["0.0.0.0/0"]
  ingress_rules       = ["http-80-tcp", "https-443-tcp"]
  egress_rules        = ["all-all"]
}

# EC2 Instance Module from Registry
module "ec2_instance" {
  source  = "terraform-aws-modules/ec2-instance/aws"
  version = "5.5.0"
  
  name = "webapp-server"
  
  ami                    = "ami-0c55b159cbfafe1f0"
  instance_type          = "t2.micro"
  subnet_id              = module.vpc.public_subnets[0]
  vpc_security_group_ids = [module.web_sg.security_group_id]
  
  tags = {
    Environment = "dev"
  }
}

# RDS Module from Registry
module "rds" {
  source  = "terraform-aws-modules/rds/aws"
  version = "6.3.0"
  
  identifier = "webapp-db"
  
  engine            = "postgres"
  engine_version    = "14.7"
  instance_class    = "db.t3.micro"
  allocated_storage = 20
  
  db_name  = "webapp"
  username = "admin"
  password = var.db_password
  
  vpc_security_group_ids = [module.web_sg.security_group_id]
  db_subnet_group_name   = module.vpc.database_subnet_group_name
  
  family = "postgres14"
  
  skip_final_snapshot = true
}

# Outputs
output "vpc_id" {
  value = module.vpc.vpc_id
}

output "ec2_public_ip" {
  value = module.ec2_instance.public_ip
}

output "rds_endpoint" {
  value     = module.rds.db_instance_endpoint
  sensitive = true
}
```

**File: `variables.tf`**
```hcl
variable "db_password" {
  type      = string
  sensitive = true
}
```

### Module Versioning

**Version constraints:**
```hcl
# Exact version
version = "5.1.2"

# Greater than or equal
version = ">= 5.1.0"

# Compatible with (same major version)
version = "~> 5.1"    # Allows 5.1.x, 5.2.x, but not 6.0.0

# Version range
version = ">= 5.0.0, < 6.0.0"
```

**Best practice:**
```hcl
# ✅ Good - specific version
version = "5.1.2"

# ⚠️ Acceptable - minor version range
version = "~> 5.1"

# ❌ Bad - no version constraint
# (uses latest, may break)
```

### Upgrading Modules

```bash
# Show currently installed modules
terraform version

# Check for updates
terraform init -upgrade

# Output:
# Upgrading modules...
# - vpc from 5.1.0 to 5.1.2
```

### Module Documentation

**Every module has:**
1. **README** - Overview and usage
2. **Inputs** - Required and optional variables
3. **Outputs** - Available outputs
4. **Examples** - Working examples
5. **Resources** - What it creates

**Reading module docs:**
```
On registry.terraform.io:
1. Click module name
2. View "Inputs" tab - see all variables
3. View "Outputs" tab - see all outputs
4. View "Resources" tab - see what it creates
5. Check examples folder
```

### Exercise: Deploy Complete Infrastructure

**Task:** Use registry modules to create VPC + EC2 + RDS

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

# Data source for AMI
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

# VPC
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "~> 5.0"
  
  name = "tutorial-vpc"
  cidr = "10.0.0.0/16"
  
  azs              = ["us-east-2a", "us-east-2b"]
  public_subnets   = ["10.0.1.0/24", "10.0.2.0/24"]
  database_subnets = ["10.0.21.0/24", "10.0.22.0/24"]
  
  create_database_subnet_group = true
  enable_dns_hostnames         = true
  enable_dns_support           = true
}

# Security Groups
module "web_sg" {
  source  = "terraform-aws-modules/security-group/aws"
  version = "~> 5.0"
  
  name   = "web-sg"
  vpc_id = module.vpc.vpc_id
  
  ingress_cidr_blocks = ["0.0.0.0/0"]
  ingress_rules       = ["http-80-tcp", "ssh-tcp"]
  egress_rules        = ["all-all"]
}

module "db_sg" {
  source  = "terraform-aws-modules/security-group/aws"
  version = "~> 5.0"
  
  name   = "db-sg"
  vpc_id = module.vpc.vpc_id
  
  computed_ingress_with_source_security_group_id = [
    {
      rule                     = "postgresql-tcp"
      source_security_group_id = module.web_sg.security_group_id
    }
  ]
  number_of_computed_ingress_with_source_security_group_id = 1
  
  egress_rules = ["all-all"]
}

# EC2 Instance
module "web_server" {
  source  = "terraform-aws-modules/ec2-instance/aws"
  version = "~> 5.0"
  
  name = "web-server"
  
  ami                    = data.aws_ami.amazon_linux.id
  instance_type          = "t2.micro"
  subnet_id              = module.vpc.public_subnets[0]
  vpc_security_group_ids = [module.web_sg.security_group_id]
  
  associate_public_ip_address = true
  
  user_data = <<-EOF
              #!/bin/bash
              yum update -y
              yum install -y httpd
              systemctl start httpd
              systemctl enable httpd
              echo "<h1>Hello from Terraform!</h1>" > /var/www/html/index.html
              EOF
  
  tags = {
    Name = "WebServer"
  }
}

# RDS Database
module "database" {
  source  = "terraform-aws-modules/rds/aws"
  version = "~> 6.0"
  
  identifier = "tutorial-db"
  
  engine               = "postgres"
  engine_version       = "14"
  family               = "postgres14"
  major_engine_version = "14"
  instance_class       = "db.t3.micro"
  
  allocated_storage = 20
  
  db_name  = "mydb"
  username = "dbadmin"
  password = "change-me-12345"  # In production, use variables!
  
  vpc_security_group_ids = [module.db_sg.security_group_id]
  db_subnet_group_name   = module.vpc.database_subnet_group_name
  
  skip_final_snapshot = true
  
  tags = {
    Name = "TutorialDB"
  }
}

# Outputs
output "web_server_public_ip" {
  description = "Public IP of web server"
  value       = module.web_server.public_ip
}

output "web_url" {
  description = "URL to access web server"
  value       = "http://${module.web_server.public_ip}"
}

output "database_endpoint" {
  description = "Database connection endpoint"
  value       = module.database.db_instance_endpoint
  sensitive   = true
}

output "vpc_id" {
  description = "VPC ID"
  value       = module.vpc.vpc_id
}
```

**Deploy:**
```bash
terraform init
terraform apply -auto-approve

# Test web server
curl $(terraform output -raw web_server_public_ip)
# Output: <h1>Hello from Terraform!</h1>
```

### Key Takeaways

📌 **Remember:**
- Registry: https://registry.terraform.io
- Source format: `namespace/name/provider`
- Always specify version
- Read module documentation
- Check examples
- Use verified modules when possible
- Test before production

---

## Section 33: Creating Custom Modules

### What You'll Learn
- Module design principles
- Creating reusable modules
- Input validation
- Documentation
- Testing modules

### Module Design Principles

**1. Single Responsibility**
```
❌ Bad: "infrastructure" module that creates everything
✅ Good: Separate modules for VPC, compute, database
```

**2. Reusability**
```
❌ Bad: Hardcoded values
✅ Good: Variables for everything that might change
```

**3. Self-Contained**
```
❌ Bad: Depends on external resources
✅ Good: Creates all needed resources internally
```

### Creating a VPC Module

**Directory structure:**
```
modules/
└── vpc/
    ├── main.tf
    ├── variables.tf
    ├── outputs.tf
    ├── versions.tf
    ├── README.md
    └── examples/
        └── basic/
            └── main.tf
```

**File: `modules/vpc/versions.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = ">= 5.0"
    }
  }
}
```

**File: `modules/vpc/variables.tf`**
```hcl
variable "name" {
  description = "Name prefix for all resources"
  type        = string
}

variable "cidr_block" {
  description = "CIDR block for VPC"
  type        = string
  
  validation {
    condition     = can(cidrhost(var.cidr_block, 0))
    error_message = "Must be valid IPv4 CIDR block."
  }
}

variable "availability_zones" {
  description = "List of availability zones"
  type        = list(string)
  
  validation {
    condition     = length(var.availability_zones) >= 2
    error_message = "At least 2 availability zones required."
  }
}

variable "public_subnet_cidrs" {
  description = "CIDR blocks for public subnets"
  type        = list(string)
}

variable "private_subnet_cidrs" {
  description = "CIDR blocks for private subnets"
  type        = list(string)
}

variable "enable_nat_gateway" {
  description = "Enable NAT gateway for private subnets"
  type        = bool
  default     = true
}

variable "single_nat_gateway" {
  description = "Use single NAT gateway for all private subnets"
  type        = bool
  default     = false
}

variable "tags" {
  description = "Tags to apply to all resources"
  type        = map(string)
  default     = {}
}
```

**File: `modules/vpc/main.tf`**
```hcl
locals {
  common_tags = merge(
    var.tags,
    { ManagedBy = "Terraform" }
  )
}

# VPC
resource "aws_vpc" "main" {
  cidr_block           = var.cidr_block
  enable_dns_hostnames = true
  enable_dns_support   = true
  
  tags = merge(
    local.common_tags,
    { Name = "${var.name}-vpc" }
  )
}

# Internet Gateway
resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id
  
  tags = merge(
    local.common_tags,
    { Name = "${var.name}-igw" }
  )
}

# Public Subnets
resource "aws_subnet" "public" {
  count = length(var.public_subnet_cidrs)
  
  vpc_id                  = aws_vpc.main.id
  cidr_block              = var.public_subnet_cidrs[count.index]
  availability_zone       = var.availability_zones[count.index]
  map_public_ip_on_launch = true
  
  tags = merge(
    local.common_tags,
    {
      Name = "${var.name}-public-${count.index + 1}"
      Type = "public"
    }
  )
}

# Private Subnets
resource "aws_subnet" "private" {
  count = length(var.private_subnet_cidrs)
  
  vpc_id            = aws_vpc.main.id
  cidr_block        = var.private_subnet_cidrs[count.index]
  availability_zone = var.availability_zones[count.index]
  
  tags = merge(
    local.common_tags,
    {
      Name = "${var.name}-private-${count.index + 1}"
      Type = "private"
    }
  )
}

# Elastic IPs for NAT Gateways
resource "aws_eip" "nat" {
  count = var.enable_nat_gateway ? (var.single_nat_gateway ? 1 : length(var.private_subnet_cidrs)) : 0
  
  domain = "vpc"
  
  tags = merge(
    local.common_tags,
    { Name = "${var.name}-nat-eip-${count.index + 1}" }
  )
  
  depends_on = [aws_internet_gateway.main]
}

# NAT Gateways
resource "aws_nat_gateway" "main" {
  count = var.enable_nat_gateway ? (var.single_nat_gateway ? 1 : length(var.private_subnet_cidrs)) : 0
  
  allocation_id = aws_eip.nat[count.index].id
  subnet_id     = aws_subnet.public[count.index].id
  
  tags = merge(
    local.common_tags,
    { Name = "${var.name}-nat-${count.index + 1}" }
  )
  
  depends_on = [aws_internet_gateway.main]
}

# Public Route Table
resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id
  
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.main.id
  }
  
  tags = merge(
    local.common_tags,
    { Name = "${var.name}-public-rt" }
  )
}

# Public Route Table Associations
resource "aws_route_table_association" "public" {
  count = length(var.public_subnet_cidrs)
  
  subnet_id      = aws_subnet.public[count.index].id
  route_table_id = aws_route_table.public.id
}

# Private Route Tables
resource "aws_route_table" "private" {
  count = var.enable_nat_gateway ? (var.single_nat_gateway ? 1 : length(var.private_subnet_cidrs)) : length(var.private_subnet_cidrs)
  
  vpc_id = aws_vpc.main.id
  
  tags = merge(
    local.common_tags,
    { Name = "${var.name}-private-rt-${count.index + 1}" }
  )
}

# Private Routes
resource "aws_route" "private_nat_gateway" {
  count = var.enable_nat_gateway ? (var.single_nat_gateway ? 1 : length(var.private_subnet_cidrs)) : 0
  
  route_table_id         = aws_route_table.private[count.index].id
  destination_cidr_block = "0.0.0.0/0"
  nat_gateway_id         = aws_nat_gateway.main[count.index].id
}

# Private Route Table Associations
resource "aws_route_table_association" "private" {
  count = length(var.private_subnet_cidrs)
  
  subnet_id      = aws_subnet.private[count.index].id
  route_table_id = var.enable_nat_gateway ? (var.single_nat_gateway ? aws_route_table.private[0].id : aws_route_table.private[count.index].id) : aws_route_table.private[count.index].id
}
```

**File: `modules/vpc/outputs.tf`**
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

output "private_subnet_ids" {
  description = "IDs of private subnets"
  value       = aws_subnet.private[*].id
}

output "public_subnet_cidrs" {
  description = "CIDR blocks of public subnets"
  value       = aws_subnet.public[*].cidr_block
}

output "private_subnet_cidrs" {
  description = "CIDR blocks of private subnets"
  value       = aws_subnet.private[*].cidr_block
}

output "nat_gateway_ids" {
  description = "IDs of NAT gateways"
  value       = aws_nat_gateway.main[*].id
}

output "internet_gateway_id" {
  description = "ID of the Internet Gateway"
  value       = aws_internet_gateway.main.id
}
```

**File: `modules/vpc/README.md`**
```markdown
# VPC Module

Creates a VPC with public and private subnets across multiple availability zones.

## Features

- VPC with custom CIDR
- Public and private subnets
- Internet Gateway
- NAT Gateways (optional, one per AZ or single)
- Route tables and associations

## Usage

```hcl
module "vpc" {
  source = "./modules/vpc"
  
  name               = "my-vpc"
  cidr_block         = "10.0.0.0/16"
  availability_zones = ["us-east-2a", "us-east-2b"]
  
  public_subnet_cidrs  = ["10.0.1.0/24", "10.0.2.0/24"]
  private_subnet_cidrs = ["10.0.11.0/24", "10.0.12.0/24"]
  
  enable_nat_gateway = true
  single_nat_gateway = false
  
  tags = {
    Environment = "dev"
  }
}
```

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|----------|
| name | Name prefix | string | - | yes |
| cidr_block | VPC CIDR | string | - | yes |
| availability_zones | AZs | list(string) | - | yes |
| public_subnet_cidrs | Public subnet CIDRs | list(string) | - | yes |
| private_subnet_cidrs | Private subnet CIDRs | list(string) | - | yes |
| enable_nat_gateway | Enable NAT Gateway | bool | true | no |
| single_nat_gateway | Single NAT Gateway | bool | false | no |
| tags | Tags | map(string) | {} | no |

## Outputs

| Name | Description |
|------|-------------|
| vpc_id | VPC ID |
| public_subnet_ids | Public subnet IDs |
| private_subnet_ids | Private subnet IDs |
```

**File: `modules/vpc/examples/basic/main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

module "vpc" {
  source = "../.."
  
  name               = "example-vpc"
  cidr_block         = "10.0.0.0/16"
  availability_zones = ["us-east-2a", "us-east-2b"]
  
  public_subnet_cidrs  = ["10.0.1.0/24", "10.0.2.0/24"]
  private_subnet_cidrs = ["10.0.11.0/24", "10.0.12.0/24"]
  
  enable_nat_gateway = true
  single_nat_gateway = true
  
  tags = {
    Environment = "example"
  }
}

output "vpc_id" {
  value = module.vpc.vpc_id
}
```

### Using Your Custom Module

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

module "dev_vpc" {
  source = "./modules/vpc"
  
  name               = "dev"
  cidr_block         = "10.0.0.0/16"
  availability_zones = ["us-east-2a", "us-east-2b"]
  
  public_subnet_cidrs  = ["10.0.1.0/24", "10.0.2.0/24"]
  private_subnet_cidrs = ["10.0.11.0/24", "10.0.12.0/24"]
  
  enable_nat_gateway = false  # Save costs in dev
  
  tags = {
    Environment = "development"
  }
}

module "prod_vpc" {
  source = "./modules/vpc"
  
  name               = "prod"
  cidr_block         = "10.1.0.0/16"
  availability_zones = ["us-east-2a", "us-east-2b", "us-east-2c"]
  
  public_subnet_cidrs  = ["10.1.1.0/24", "10.1.2.0/24", "10.1.3.0/24"]
  private_subnet_cidrs = ["10.1.11.0/24", "10.1.12.0/24", "10.1.13.0/24"]
  
  enable_nat_gateway = true
  single_nat_gateway = false  # High availability
  
  tags = {
    Environment = "production"
  }
}

output "dev_vpc_id" {
  value = module.dev_vpc.vpc_id
}

output "prod_vpc_id" {
  value = module.prod_vpc.vpc_id
}
```

### Key Takeaways

📌 **Remember:**
- Single responsibility per module
- Use variables for flexibility
- Add input validation
- Document everything
- Provide examples
- Test with different configurations
- Use meaningful outputs

---

## Section 34: Module Versioning and Sources

### What You'll Learn
- Module source types
- Version constraints
- Publishing modules
- Module caching
- Best practices

### Module Source Types

**1. Local Path**
```hcl
module "vpc" {
  source = "./modules/vpc"
}

module "vpc" {
  source = "../shared-modules/vpc"
}
```

**2. Terraform Registry**
```hcl
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "5.1.2"
}
```

**3. GitHub**
```hcl
# HTTPS
module "vpc" {
  source = "github.com/your-org/terraform-modules//vpc"
}

# SSH
module "vpc" {
  source = "git@github.com:your-org/terraform-modules.git//vpc"
}

# Specific branch
module "vpc" {
  source = "github.com/your-org/terraform-modules//vpc?ref=main"
}

# Specific tag
module "vpc" {
  source = "github.com/your-org/terraform-modules//vpc?ref=v1.0.0"
}

# Specific commit
module "vpc" {
  source = "github.com/your-org/terraform-modules//vpc?ref=abc123"
}
```

**4. Git (Generic)**
```hcl
module "vpc" {
  source = "git::https://git.example.com/terraform-modules.git//vpc"
}
```

**5. HTTP URLs**
```hcl
module "vpc" {
  source = "https://example.com/vpc-module.zip"
}
```

**6. S3 Bucket**
```hcl
module "vpc" {
  source = "s3::https://s3.amazonaws.com/my-bucket/vpc-module.zip"
}
```

### Complete Example with Different Sources

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

# Local module
module "local_vpc" {
  source = "./modules/vpc"
  
  name       = "local-vpc"
  cidr_block = "10.0.0.0/16"
  # ...
}

# Registry module with version
module "registry_vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "~> 5.0"
  
  name = "registry-vpc"
  cidr = "10.1.0.0/16"
  # ...
}

# GitHub module with tag
module "github_vpc" {
  source = "github.com/myorg/terraform-modules//vpc?ref=v1.2.0"
  
  name       = "github-vpc"
  cidr_block = "10.2.0.0/16"
  # ...
}
```

### Versioning Strategies

#### Semantic Versioning

```
Version format: MAJOR.MINOR.PATCH

Examples:
- 1.0.0 → Initial release
- 1.0.1 → Bug fix (backward compatible)
- 1.1.0 → New feature (backward compatible)
- 2.0.0 → Breaking change
```

#### Version Constraints

```hcl
# Exact version
version = "1.2.3"

# Greater than or equal
version = ">= 1.0.0"

# Pessimistic constraint (recommended)
version = "~> 1.2"    # Allows 1.2.x, 1.3.x, but not 2.0.0
version = "~> 1.2.3"  # Allows 1.2.3, 1.2.4, but not 1.3.0

# Range
version = ">= 1.0.0, < 2.0.0"

# Multiple constraints
version = ">= 1.2.0, != 1.2.1, < 2.0.0"
```

**Best practices:**
```hcl
# ✅ Production - pin exact version
version = "1.2.3"

# ✅ Development - allow patch updates
version = "~> 1.2.3"

# ⚠️ Be careful - allows any minor version
version = "~> 1.2"

# ❌ Avoid - no version constraint
# (defaults to latest, can break things)
```

### Publishing Modules to Registry

**Step 1: Create GitHub repo**
```bash
# Naming convention: terraform-<PROVIDER>-<NAME>
# Example: terraform-aws-vpc

# Structure:
terraform-aws-vpc/
├── main.tf
├── variables.tf
├── outputs.tf
├── versions.tf
├── README.md
├── LICENSE
└── examples/
    └── basic/
        └── main.tf
```

**Step 2: Tag release**
```bash
git tag -a v1.0.0 -m "Initial release"
git push origin v1.0.0
```

**Step 3: Publish to registry**
1. Go to registry.terraform.io
2. Sign in with GitHub
3. Click "Publish" → "Module"
4. Select repository
5. Terraform automatically detects tags

**Step 4: Use published module**
```hcl
module "vpc" {
  source  = "your-org/vpc/aws"
  version = "1.0.0"
  
  # ...
}
```

### Module Caching

**Location:**
```bash
# Modules cached in:
.terraform/modules/

# Structure:
.terraform/
└── modules/
    ├── modules.json
    ├── vpc/
    ├── ec2/
    └── rds/
```

**Cache management:**
```bash
# Install/update modules
terraform init

# Update specific module
terraform init -upgrade

# Force reinstall
rm -rf .terraform/modules/
terraform init

# View installed modules
terraform version
```

### Git Reference Examples

```hcl
# Branch
module "vpc" {
  source = "github.com/myorg/modules//vpc?ref=develop"
}

# Tag
module "vpc" {
  source = "github.com/myorg/modules//vpc?ref=v2.0.0"
}

# Commit SHA
module "vpc" {
  source = "github.com/myorg/modules//vpc?ref=abc123def456"
}

# With subdirectory
module "vpc" {
  source = "github.com/myorg/modules//networking/vpc?ref=v1.0.0"
}
```

### Complete Example: Multi-Source Setup

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-2"
}

# Official registry module
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "5.1.2"
  
  name = "main-vpc"
  cidr = "10.0.0.0/16"
  
  azs             = ["us-east-2a", "us-east-2b"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24"]
  
  enable_nat_gateway = true
}

# Company private module from GitHub
module "app_server" {
  source = "github.com/mycompany/terraform-modules//app-server?ref=v2.1.0"
  
  name       = "web-app"
  vpc_id     = module.vpc.vpc_id
  subnet_ids = module.vpc.private_subnets
}

# Local custom module
module "monitoring" {
  source = "./modules/monitoring"
  
  resources_to_monitor = [
    module.app_server.instance_id
  ]
}
```

### Key Takeaways

📌 **Remember:**
- Use version constraints in production
- Pin exact versions for stability
- Tag releases with semantic versioning
- Modules are cached in `.terraform/modules/`
- Use `?ref=` for Git sources
- Registry modules: `source + version`
- Local modules: just `source`

---

## Section 35: Module Best Practices

### What You'll Learn
- Module design patterns
- Error handling
- Testing strategies
- Documentation
- Maintenance

### Module Design Patterns

#### 1. Input Validation

```hcl
variable "environment" {
  type = string
  
  validation {
    condition     = contains(["dev", "staging", "prod"], var.environment)
    error_message = "Environment must be dev, staging, or prod."
  }
}

variable "instance_count" {
  type = number
  
  validation {
    condition     = var.instance_count > 0 && var.instance_count <= 10
    error_message = "Instance count must be between 1 and 10."
  }
}

variable "cidr_block" {
  type = string
  
  validation {
    condition     = can(cidrhost(var.cidr_block, 0))
    error_message = "Must be valid IPv4 CIDR block."
  }
}
```

#### 2. Sensible Defaults

```hcl
variable "instance_type" {
  type        = string
  description = "EC2 instance type"
  default     = "t2.micro"
}

variable "enable_monitoring" {
  type        = bool
  description = "Enable detailed monitoring"
  default     = false
}

variable "backup_retention_days" {
  type        = number
  description = "Number of days to retain backups"
  default     = 7
}

variable "tags" {
  type        = map(string)
  description = "Tags to apply to resources"
  default     = {}
}
```

#### 3. Computed Defaults

```hcl
locals {
  # Default name if not provided
  name = var.name != "" ? var.name : "default-${random_id.this.hex}"
  
  # Environment-specific defaults
  instance_count = var.instance_count != null ? var.instance_count : (
    var.environment == "prod" ? 3 : 1
  )
  
  # Merge provided tags with defaults
  tags = merge(
    {
      ManagedBy   = "Terraform"
      Environment = var.environment
    },
    var.tags
  )
}
```

#### 4. Feature Flags

```hcl
variable "enable_backup" {
  type    = bool
  default = false
}

variable "enable_monitoring" {
  type    = bool
  default = false
}

# Conditionally create resources
resource "aws_backup_plan" "this" {
  count = var.enable_backup ? 1 : 0
  
  name = "${var.name}-backup-plan"
  # ...
}

resource "aws_cloudwatch_metric_alarm" "this" {
  count = var.enable_monitoring ? 1 : 0
  
  alarm_name = "${var.name}-alarm"
  # ...
}
```

### Error Handling

#### 1. Preconditions

```hcl
resource "aws_instance" "this" {
  ami           = var.ami_id
  instance_type = var.instance_type
  
  lifecycle {
    precondition {
      condition     = var.environment == "prod" ? var.instance_type != "t2.micro" : true
      error_message = "Production instances cannot use t2.micro."
    }
    
    precondition {
      condition     = length(var.subnet_ids) >= 2
      error_message = "At least 2 subnets required for high availability."
    }
  }
}
```

#### 2. Postconditions

```hcl
resource "aws_instance" "this" {
  ami           = var.ami_id
  instance_type = var.instance_type
  
  lifecycle {
    postcondition {
      condition     = self.public_ip != ""
      error_message = "Instance must have a public IP."
    }
  }
}
```

#### 3. Check Blocks

```hcl
check "instance_running" {
  data "aws_instance" "check" {
    instance_id = aws_instance.this.id
  }
  
  assert {
    condition     = data.aws_instance.check.instance_state == "running"
    error_message = "Instance is not running."
  }
}
```

### Testing Strategies

#### 1. Example Configurations

```
modules/
└── vpc/
    ├── main.tf
    ├── variables.tf
    ├── outputs.tf
    └── examples/
        ├── basic/
        │   └── main.tf
        ├── complete/
        │   └── main.tf
        └── minimal/
            └── main.tf
```

**File: `examples/basic/main.tf`**
```hcl
provider "aws" {
  region = "us-east-2"
}

module "vpc" {
  source = "../.."
  
  name               = "test-vpc"
  cidr_block         = "10.0.0.0/16"
  availability_zones = ["us-east-2a", "us-east-2b"]
  
  public_subnet_cidrs  = ["10.0.1.0/24", "10.0.2.0/24"]
  private_subnet_cidrs = ["10.0.11.0/24", "10.0.12.0/24"]
}

output "vpc_id" {
  value = module.vpc.vpc_id
}
```

#### 2. Automated Tests (Terratest)

**File: `test/vpc_test.go`**
```go
package test

import (
    "testing"
    "github.com/gruntwork-io/terratest/modules/terraform"
    "github.com/stretchr/testify/assert"
)

func TestVPCModule(t *testing.T) {
    terraformOptions := &terraform.Options{
        TerraformDir: "../examples/basic",
    }
    
    defer terraform.Destroy(t, terraformOptions)
    
    terraform.InitAndApply(t, terraformOptions)
    
    vpcID := terraform.Output(t, terraformOptions, "vpc_id")
    assert.NotEmpty(t, vpcID)
}
```

### Documentation Best Practices

**File: `README.md`**
```markdown
# VPC Module

## Description

Creates a highly available VPC with public and private subnets across multiple AZs.

## Features

- ✅ VPC with custom CIDR
- ✅ Public and private subnets
- ✅ Internet Gateway
- ✅ NAT Gateways (configurable)
- ✅ Route tables
- ✅ Subnet tags for EKS/ELB

## Usage

### Basic Example

```hcl
module "vpc" {
  source  = "myorg/vpc/aws"
  version = "1.0.0"
  
  name       = "my-vpc"
  cidr_block = "10.0.0.0/16"
  
  availability_zones = ["us-east-2a", "us-east-2b"]
  
  public_subnet_cidrs  = ["10.0.1.0/24", "10.0.2.0/24"]
  private_subnet_cidrs = ["10.0.11.0/24", "10.0.12.0/24"]
}
```

### Complete Example

See [examples/complete](examples/complete) for a full example.

## Requirements

| Name | Version |
|------|---------|
| terraform | >= 1.0 |
| aws | >= 5.0 |

## Providers

| Name | Version |
|------|---------|
| aws | >= 5.0 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| name | Name prefix | `string` | n/a | yes |
| cidr_block | VPC CIDR | `string` | n/a | yes |
| availability_zones | List of AZs | `list(string)` | n/a | yes |
| public_subnet_cidrs | Public subnet CIDRs | `list(string)` | n/a | yes |
| private_subnet_cidrs | Private subnet CIDRs | `list(string)` | n/a | yes |
| enable_nat_gateway | Enable NAT Gateway | `bool` | `true` | no |
| single_nat_gateway | Use single NAT Gateway | `bool` | `false` | no |

## Outputs

| Name | Description |
|------|-------------|
| vpc_id | VPC ID |
| vpc_cidr | VPC CIDR block |
| public_subnet_ids | List of public subnet IDs |
| private_subnet_ids | List of private subnet IDs |

## Examples

- [Basic](examples/basic) - Minimal configuration
- [Complete](examples/complete) - All features enabled
- [Minimal](examples/minimal) - Minimal resources

## Notes

- NAT Gateway incurs costs (~$32/month per gateway)
- Use `single_nat_gateway = true` for cost savings in dev
- Requires at least 2 availability zones for HA

## License

MIT
```

### Maintenance Best Practices

#### 1. Changelog

**File: `CHANGELOG.md`**
```markdown
# Changelog

## [2.0.0] - 2024-01-15

### Breaking Changes
- Changed `azs` variable to `availability_zones`
- Removed `enable_dns` variable (always enabled now)

### Added
- Support for IPv6
- Database subnet group

### Fixed
- NAT Gateway tags
- Route table associations

## [1.1.0] - 2023-12-01

### Added
- VPC Flow Logs support
- Additional subnet tags

### Fixed
- Single NAT Gateway routing

## [1.0.0] - 2023-11-01

### Added
- Initial release
```

#### 2. Version File

**File: `versions.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = ">= 5.0, < 6.0"
    }
  }
}
```

#### 3. Examples for Every Feature

```
examples/
├── basic/              # Minimal working example
├── complete/           # All features enabled
├── minimal/            # Absolute minimum
├── with-nat-gateway/   # NAT Gateway configuration
└── without-nat-gateway/ # No NAT Gateway
```

### Module Checklist

**Before publishing a module:**

- [ ] README.md with usage examples
- [ ] Input validation for all variables
- [ ] Meaningful output values
- [ ] At least one working example
- [ ] CHANGELOG.md
- [ ] LICENSE file
- [ ] versions.tf with constraints
- [ ] Semantic version tags
- [ ] Tests (if possible)
- [ ] CI/CD for validation

### Key Takeaways

📌 **Remember:**
- Validate all inputs
- Provide sensible defaults
- Document everything
- Include examples
- Use semantic versioning
- Add preconditions/postconditions
- Test thoroughly
- Maintain changelog

---

**🎉 Congratulations!** You've completed Part 7: Modules!

---

## Part 8: Real-World Projects

---

## Section 36: Project 1 - Static Website with S3 and CloudFront

### What You'll Learn
- Hosting static websites on S3
- CloudFront CDN setup
- SSL certificates
- DNS configuration
- Complete deployment

### Architecture

```
┌─────────┐
│ User    │
└────┬────┘
     │ HTTPS
     ▼
┌─────────────────┐
│  CloudFront CDN │ (Global Edge Locations)
└────┬────────────┘
     │
     ▼
┌──────────────┐
│  S3 Bucket   │ (Private)
│  Website     │
└──────────────┘
```

### Project Structure

```
static-website/
├── website/
│   ├── index.html
│   ├── error.html
│   ├── style.css
│   └── images/
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│   └── terraform.tfvars
└── README.md
```

### Step 1: Create Website Files

**File: `website/index.html`**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Static Website</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>🚀 Welcome to My Static Website!</h1>
        <p>Hosted on AWS S3 + CloudFront</p>
        <p>Deployed with Terraform</p>
    </div>
</body>
</html>
```

**File: `website/error.html`**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>404 - Page Not Found</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>404 - Page Not Found</h1>
        <p><a href="/">Go back home</a></p>
    </div>
</body>
</html>
```

**File: `website/style.css`**
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
}

.container {
    background: white;
    padding: 3rem;
    border-radius: 10px;
    box-shadow: 0 10px 40px rgba(0,0,0,0.2);
    text-align: center;
}

h1 {
    color: #333;
    margin-bottom: 1rem;
}

p {
    color: #666;
    margin-bottom: 0.5rem;
}
```

### Step 2: Terraform Configuration

**File: `terraform/main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
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

# S3 Bucket for website
resource "aws_s3_bucket" "website" {
  bucket = var.bucket_name
  
  tags = {
    Name        = var.bucket_name
    Environment = var.environment
  }
}

# Bucket ownership controls
resource "aws_s3_bucket_ownership_controls" "website" {
  bucket = aws_s3_bucket.website.id
  
  rule {
    object_ownership = "BucketOwnerPreferred"
  }
}

# Block public access (CloudFront will access privately)
resource "aws_s3_bucket_public_access_block" "website" {
  bucket = aws_s3_bucket.website.id
  
  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}

# Enable versioning
resource "aws_s3_bucket_versioning" "website" {
  bucket = aws_s3_bucket.website.id
  
  versioning_configuration {
    status = "Enabled"
  }
}

# Website configuration
resource "aws_s3_bucket_website_configuration" "website" {
  bucket = aws_s3_bucket.website.id
  
  index_document {
    suffix = "index.html"
  }
  
  error_document {
    key = "error.html"
  }
}

# CloudFront Origin Access Identity
resource "aws_cloudfront_origin_access_identity" "website" {
  comment = "OAI for ${var.bucket_name}"
}

# S3 bucket policy for CloudFront
resource "aws_s3_bucket_policy" "website" {
  bucket = aws_s3_bucket.website.id
  
  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Sid    = "AllowCloudFrontAccess"
        Effect = "Allow"
        Principal = {
          AWS = aws_cloudfront_origin_access_identity.website.iam_arn
        }
        Action   = "s3:GetObject"
        Resource = "${aws_s3_bucket.website.arn}/*"
      }
    ]
  })
}

# CloudFront distribution
resource "aws_cloudfront_distribution" "website" {
  enabled             = true
  is_ipv6_enabled     = true
  default_root_object = "index.html"
  price_class         = var.cloudfront_price_class
  
  origin {
    domain_name = aws_s3_bucket.website.bucket_regional_domain_name
    origin_id   = "S3-${var.bucket_name}"
    
    s3_origin_config {
      origin_access_identity = aws_cloudfront_origin_access_identity.website.cloudfront_access_identity_path
    }
  }
  
  default_cache_behavior {
    allowed_methods  = ["GET", "HEAD", "OPTIONS"]
    cached_methods   = ["GET", "HEAD"]
    target_origin_id = "S3-${var.bucket_name}"
    
    forwarded_values {
      query_string = false
      
      cookies {
        forward = "none"
      }
    }
    
    viewer_protocol_policy = "redirect-to-https"
    min_ttl                = 0
    default_ttl            = 3600
    max_ttl                = 86400
    compress               = true
  }
  
  restrictions {
    geo_restriction {
      restriction_type = "none"
    }
  }
  
  viewer_certificate {
    cloudfront_default_certificate = true
  }
  
  custom_error_response {
    error_code            = 404
    response_code         = 404
    response_page_path    = "/error.html"
    error_caching_min_ttl = 300
  }
  
  tags = {
    Name        = "${var.bucket_name}-cdn"
    Environment = var.environment
  }
}

# Upload website files
resource "aws_s3_object" "website_files" {
  for_each = fileset("${path.module}/../website", "**/*")
  
  bucket       = aws_s3_bucket.website.id
  key          = each.value
  source       = "${path.module}/../website/${each.value}"
  etag         = filemd5("${path.module}/../website/${each.value}")
  content_type = lookup(local.content_types, regex("\\.[^.]+$", each.value), "application/octet-stream")
}

# Content type mapping
locals {
  content_types = {
    ".html" = "text/html"
    ".css"  = "text/css"
    ".js"   = "application/javascript"
    ".json" = "application/json"
    ".png"  = "image/png"
    ".jpg"  = "image/jpeg"
    ".jpeg" = "image/jpeg"
    ".gif"  = "image/gif"
    ".svg"  = "image/svg+xml"
  }
}
```

**File: `terraform/variables.tf`**
```hcl
variable "aws_region" {
  description = "AWS region"
  type        = string
  default     = "us-east-2"
}

variable "bucket_name" {
  description = "S3 bucket name (must be globally unique)"
  type        = string
}

variable "environment" {
  description = "Environment name"
  type        = string
  default     = "production"
}

variable "cloudfront_price_class" {
  description = "CloudFront price class"
  type        = string
  default     = "PriceClass_100"  # US, Canada, Europe
}
```

**File: `terraform/outputs.tf`**
```hcl
output "s3_bucket_name" {
  description = "Name of the S3 bucket"
  value       = aws_s3_bucket.website.id
}

output "s3_bucket_arn" {
  description = "ARN of the S3 bucket"
  value       = aws_s3_bucket.website.arn
}

output "cloudfront_domain_name" {
  description = "CloudFront distribution domain name"
  value       = aws_cloudfront_distribution.website.domain_name
}

output "cloudfront_distribution_id" {
  description = "CloudFront distribution ID"
  value       = aws_cloudfront_distribution.website.id
}

output "website_url" {
  description = "URL to access the website"
  value       = "https://${aws_cloudfront_distribution.website.domain_name}"
}
```

**File: `terraform/terraform.tfvars`**
```hcl
bucket_name  = "my-static-website-12345"  # Change to unique name
environment  = "production"
aws_region   = "us-east-2"
```

### Step 3: Deploy

```bash
cd terraform

# Initialize
terraform init

# Plan
terraform plan

# Apply
terraform apply -auto-approve

# Get website URL
terraform output website_url
# Output: https://d1234567890.cloudfront.net
```

### Step 4: Access Website

```bash
# Get the URL
URL=$(terraform output -raw website_url)

# Open in browser
echo "Visit: $URL"

# Or test with curl
curl $URL
```

### Step 5: Update Website

**Update `website/index.html`:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Static Website - Updated!</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>🎉 Website Updated!</h1>
        <p>This is version 2.0</p>
    </div>
</body>
</html>
```

**Re-deploy:**
```bash
terraform apply -auto-approve

# Invalidate CloudFront cache
aws cloudfront create-invalidation \
  --distribution-id $(terraform output -raw cloudfront_distribution_id) \
  --paths "/*"
```

### Enhancements

#### Add Custom Domain

**File: `terraform/main.tf` (add)**
```hcl
# ACM Certificate (must be in us-east-1 for CloudFront)
provider "aws" {
  alias  = "us_east_1"
  region = "us-east-1"
}

resource "aws_acm_certificate" "website" {
  provider = aws.us_east_1
  
  domain_name       = var.domain_name
  validation_method = "DNS"
  
  lifecycle {
    create_before_destroy = true
  }
}

# Update CloudFront distribution
resource "aws_cloudfront_distribution" "website" {
  # ... existing configuration ...
  
  aliases = [var.domain_name]
  
  viewer_certificate {
    acm_certificate_arn      = aws_acm_certificate.website.arn
    ssl_support_method       = "sni-only"
    minimum_protocol_version = "TLSv1.2_2021"
  }
}

# Route 53 record
resource "aws_route53_record" "website" {
  zone_id = var.route53_zone_id
  name    = var.domain_name
  type    = "A"
  
  alias {
    name                   = aws_cloudfront_distribution.website.domain_name
    zone_id                = aws_cloudfront_distribution.website.hosted_zone_id
    evaluate_target_health = false
  }
}
```

### Key Takeaways

📌 **Remember:**
- S3 for storage (private)
- CloudFront for CDN and HTTPS
- OAI for secure S3 access
- Cache invalidation after updates
- Cost: ~$1-5/month for small sites

---

## Section 37: Project 2 - Web Application with ALB and ASG

### What You'll Learn
- Application Load Balancer setup
- Auto Scaling Groups
- Launch Templates
- Health checks
- Complete HA web application

### Architecture

```
Internet
   │
   ▼
┌──────────────────┐
│ Application Load │
│    Balancer      │
└────────┬─────────┘
         │
    ┌────┴────┐
    │         │
    ▼         ▼
┌────────┐ ┌────────┐
│  EC2   │ │  EC2   │
│ (Auto  │ │ (Auto  │
│ Scale) │ │ Scale) │
└────────┘ └────────┘
```

### Complete Project Code

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
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

# Data Sources
data "aws_availability_zones" "available" {
  state = "available"
}

data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

# VPC
resource "aws_vpc" "main" {
  cidr_block           = var.vpc_cidr
  enable_dns_hostnames = true
  enable_dns_support   = true
  
  tags = {
    Name = "${var.project_name}-vpc"
  }
}

# Internet Gateway
resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id
  
  tags = {
    Name = "${var.project_name}-igw"
  }
}

# Public Subnets
resource "aws_subnet" "public" {
  count = 2
  
  vpc_id                  = aws_vpc.main.id
  cidr_block              = cidrsubnet(var.vpc_cidr, 8, count.index)
  availability_zone       = data.aws_availability_zones.available.names[count.index]
  map_public_ip_on_launch = true
  
  tags = {
    Name = "${var.project_name}-public-${count.index + 1}"
  }
}

# Route Table
resource "aws_route_table" "public" {
  vpc_id = aws_vpc.main.id
  
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.main.id
  }
  
  tags = {
    Name = "${var.project_name}-public-rt"
  }
}

# Route Table Associations
resource "aws_route_table_association" "public" {
  count = 2
  
  subnet_id      = aws_subnet.public[count.index].id
  route_table_id = aws_route_table.public.id
}

# Security Group for ALB
resource "aws_security_group" "alb" {
  name        = "${var.project_name}-alb-sg"
  description = "Security group for ALB"
  vpc_id      = aws_vpc.main.id
  
  ingress {
    description = "HTTP from Internet"
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  tags = {
    Name = "${var.project_name}-alb-sg"
  }
}

# Security Group for EC2
resource "aws_security_group" "web" {
  name        = "${var.project_name}-web-sg"
  description = "Security group for web servers"
  vpc_id      = aws_vpc.main.id
  
  ingress {
    description     = "HTTP from ALB"
    from_port       = 80
    to_port         = 80
    protocol        = "tcp"
    security_groups = [aws_security_group.alb.id]
  }
  
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  tags = {
    Name = "${var.project_name}-web-sg"
  }
}

# Application Load Balancer
resource "aws_lb" "main" {
  name               = "${var.project_name}-alb"
  internal           = false
  load_balancer_type = "application"
  security_groups    = [aws_security_group.alb.id]
  subnets            = aws_subnet.public[*].id
  
  tags = {
    Name = "${var.project_name}-alb"
  }
}

# Target Group
resource "aws_lb_target_group" "main" {
  name     = "${var.project_name}-tg"
  port     = 80
  protocol = "HTTP"
  vpc_id   = aws_vpc.main.id
  
  health_check {
    enabled             = true
    healthy_threshold   = 2
    unhealthy_threshold = 2
    timeout             = 5
    interval            = 30
    path                = "/"
    matcher             = "200"
  }
  
  tags = {
    Name = "${var.project_name}-tg"
  }
}

# ALB Listener
resource "aws_lb_listener" "main" {
  load_balancer_arn = aws_lb.main.arn
  port              = "80"
  protocol          = "HTTP"
  
  default_action {
    type             = "forward"
    target_group_arn = aws_lb_target_group.main.arn
  }
}

# Launch Template
resource "aws_launch_template" "main" {
  name_prefix   = "${var.project_name}-"
  image_id      = data.aws_ami.amazon_linux.id
  instance_type = var.instance_type
  
  vpc_security_group_ids = [aws_security_group.web.id]
  
  user_data = base64encode(<<-EOF
              #!/bin/bash
              yum update -y
              yum install -y httpd
              systemctl start httpd
              systemctl enable httpd
              
              # Get instance metadata
              INSTANCE_ID=$(ec2-metadata --instance-id | cut -d " " -f 2)
              AVAILABILITY_ZONE=$(ec2-metadata --availability-zone | cut -d " " -f 2)
              
              # Create web page
              cat > /var/www/html/index.html <<HTML
              <!DOCTYPE html>
              <html>
              <head>
                  <title>Auto Scaling Demo</title>
                  <style>
                      body {
                          font-family: Arial, sans-serif;
                          background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
                          color: white;
                          padding: 50px;
                          text-align: center;
                      }
                      .info {
                          background: rgba(255,255,255,0.1);
                          padding: 20px;
                          border-radius: 10px;
                          margin: 20px auto;
                          max-width: 600px;
                      }
                  </style>
              </head>
              <body>
                  <h1>🚀 Auto Scaling Web Application</h1>
                  <div class="info">
                      <h2>Instance Information</h2>
                      <p><strong>Instance ID:</strong> $INSTANCE_ID</p>
                      <p><strong>Availability Zone:</strong> $AVAILABILITY_ZONE</p>
                      <p><strong>Deployed with:</strong> Terraform</p>
                  </div>
              </body>
              </html>
HTML
              EOF
  )
  
  tag_specifications {
    resource_type = "instance"
    tags = {
      Name = "${var.project_name}-instance"
    }
  }
}

# Auto Scaling Group
resource "aws_autoscaling_group" "main" {
  name                = "${var.project_name}-asg"
  vpc_zone_identifier = aws_subnet.public[*].id
  target_group_arns   = [aws_lb_target_group.main.arn]
  health_check_type   = "ELB"
  health_check_grace_period = 300
  
  min_size         = var.asg_min_size
  max_size         = var.asg_max_size
  desired_capacity = var.asg_desired_capacity
  
  launch_template {
    id      = aws_launch_template.main.id
    version = "$Latest"
  }
  
  tag {
    key                 = "Name"
    value               = "${var.project_name}-asg-instance"
    propagate_at_launch = true
  }
}

# Auto Scaling Policy - Scale Up
resource "aws_autoscaling_policy" "scale_up" {
  name                   = "${var.project_name}-scale-up"
  autoscaling_group_name = aws_autoscaling_group.main.name
  adjustment_type        = "ChangeInCapacity"
  scaling_adjustment     = 1
  cooldown               = 300
}

# CloudWatch Alarm - High CPU
resource "aws_cloudwatch_metric_alarm" "high_cpu" {
  alarm_name          = "${var.project_name}-high-cpu"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 2
  metric_name         = "CPUUtilization"
  namespace           = "AWS/EC2"
  period              = 120
  statistic           = "Average"
  threshold           = 70
  
  dimensions = {
    AutoScalingGroupName = aws_autoscaling_group.main.name
  }
  
  alarm_actions = [aws_autoscaling_policy.scale_up.arn]
}

# Auto Scaling Policy - Scale Down
resource "aws_autoscaling_policy" "scale_down" {
  name                   = "${var.project_name}-scale-down"
  autoscaling_group_name = aws_autoscaling_group.main.name
  adjustment_type        = "ChangeInCapacity"
  scaling_adjustment     = -1
  cooldown               = 300
}

# CloudWatch Alarm - Low CPU
resource "aws_cloudwatch_metric_alarm" "low_cpu" {
  alarm_name          = "${var.project_name}-low-cpu"
  comparison_operator = "LessThanThreshold"
  evaluation_periods  = 2
  metric_name         = "CPUUtilization"
  namespace           = "AWS/EC2"
  period              = 120
  statistic           = "Average"
  threshold           = 30
  
  dimensions = {
    AutoScalingGroupName = aws_autoscaling_group.main.name
  }
  
  alarm_actions = [aws_autoscaling_policy.scale_down.arn]
}
```

**File: `variables.tf`**
```hcl
variable "aws_region" {
  description = "AWS region"
  type        = string
  default     = "us-east-2"
}

variable "project_name" {
  description = "Project name"
  type        = string
  default     = "webapp"
}

variable "vpc_cidr" {
  description = "VPC CIDR block"
  type        = string
  default     = "10.0.0.0/16"
}

variable "instance_type" {
  description = "EC2 instance type"
  type        = string
  default     = "t2.micro"
}

variable "asg_min_size" {
  description = "Minimum number of instances"
  type        = number
  default     = 2
}

variable "asg_max_size" {
  description = "Maximum number of instances"
  type        = number
  default     = 4
}

variable "asg_desired_capacity" {
  description = "Desired number of instances"
  type        = number
  default     = 2
}
```

**File: `outputs.tf`**
```hcl
output "alb_dns_name" {
  description = "DNS name of the load balancer"
  value       = aws_lb.main.dns_name
}

output "alb_url" {
  description = "URL to access the application"
  value       = "http://${aws_lb.main.dns_name}"
}

output "asg_name" {
  description = "Name of the Auto Scaling Group"
  value       = aws_autoscaling_group.main.name
}
```

### Deploy and Test

```bash
# Initialize
terraform init

# Deploy
terraform apply -auto-approve

# Get URL
ALB_URL=$(terraform output -raw alb_url)
echo "Application URL: $ALB_URL"

# Wait for instances to be healthy (2-3 minutes)
sleep 180

# Test the application
curl $ALB_URL

# Refresh multiple times to see different instances
for i in {1..10}; do
  curl -s $ALB_URL | grep "Instance ID"
  sleep 1
done
```

### Test Auto Scaling

```bash
# Generate load to trigger scale-up
for i in {1..1000}; do
  curl -s $ALB_URL > /dev/null &
done

# Watch instances scale
watch -n 5 'aws autoscaling describe-auto-scaling-groups \
  --auto-scaling-group-names $(terraform output -raw asg_name) \
  --query "AutoScalingGroups[0].Instances[*].[InstanceId,HealthStatus]" \
  --output table'
```

### Key Takeaways

📌 **Remember:**
- ALB distributes traffic across AZs
- ASG maintains desired capacity
- Health checks ensure reliability
- Auto scaling based on CPU metrics
- Cost: ~$30-50/month

---

## Section 38: Project 3 - Three-Tier Application

### What You'll Learn
- Multi-tier architecture
- Private/public subnet design
- Database tier with RDS
- NAT Gateway configuration
- Complete production setup

### Architecture

```
Internet
   │
   ▼
┌──────────┐
│   ALB    │ (Public Subnet)
└────┬─────┘
     │
     ▼
┌──────────┐
│   EC2    │ (Private Subnet - App Tier)
│   ASG    │
└────┬─────┘
     │
     ▼
┌──────────┐
│   RDS    │ (Private Subnet - DB Tier)
└──────────┘
```

This architecture implements a classic three-tier design with web (ALB), application (EC2), and database (RDS) tiers, each in separate security zones.

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
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

# Use VPC module
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "~> 5.0"
  
  name = "${var.project_name}-vpc"
  cidr = var.vpc_cidr
  
  azs              = ["${var.aws_region}a", "${var.aws_region}b"]
  public_subnets   = [cidrsubnet(var.vpc_cidr, 8, 0), cidrsubnet(var.vpc_cidr, 8, 1)]
  private_subnets  = [cidrsubnet(var.vpc_cidr, 8, 10), cidrsubnet(var.vpc_cidr, 8, 11)]
  database_subnets = [cidrsubnet(var.vpc_cidr, 8, 20), cidrsubnet(var.vpc_cidr, 8, 21)]
  
  enable_nat_gateway   = true
  single_nat_gateway   = var.environment == "prod" ? false : true
  enable_dns_hostnames = true
  
  create_database_subnet_group = true
  
  tags = {
    Environment = var.environment
  }
}

# Application Load Balancer
module "alb" {
  source  = "terraform-aws-modules/alb/aws"
  version = "~> 8.0"
  
  name = "${var.project_name}-alb"
  
  load_balancer_type = "application"
  vpc_id             = module.vpc.vpc_id
  subnets            = module.vpc.public_subnets
  security_groups    = [module.alb_sg.security_group_id]
  
  target_groups = [
    {
      name             = "${var.project_name}-tg"
      backend_protocol = "HTTP"
      backend_port     = 80
      target_type      = "instance"
      health_check = {
        enabled             = true
        interval            = 30
        path                = "/health"
        port                = "traffic-port"
        healthy_threshold   = 2
        unhealthy_threshold = 2
        timeout             = 5
        protocol            = "HTTP"
        matcher             = "200"
      }
    }
  ]
  
  http_tcp_listeners = [
    {
      port               = 80
      protocol           = "HTTP"
      target_group_index = 0
    }
  ]
}

# Security Groups
module "alb_sg" {
  source  = "terraform-aws-modules/security-group/aws"
  version = "~> 5.0"
  
  name        = "${var.project_name}-alb-sg"
  description = "Security group for ALB"
  vpc_id      = module.vpc.vpc_id
  
  ingress_cidr_blocks = ["0.0.0.0/0"]
  ingress_rules       = ["http-80-tcp"]
  egress_rules        = ["all-all"]
}

module "app_sg" {
  source  = "terraform-aws-modules/security-group/aws"
  version = "~> 5.0"
  
  name        = "${var.project_name}-app-sg"
  description = "Security group for app servers"
  vpc_id      = module.vpc.vpc_id
  
  computed_ingress_with_source_security_group_id = [
    {
      rule                     = "http-80-tcp"
      source_security_group_id = module.alb_sg.security_group_id
    }
  ]
  number_of_computed_ingress_with_source_security_group_id = 1
  
  egress_rules = ["all-all"]
}

module "db_sg" {
  source  = "terraform-aws-modules/security-group/aws"
  version = "~> 5.0"
  
  name        = "${var.project_name}-db-sg"
  description = "Security group for database"
  vpc_id      = module.vpc.vpc_id
  
  computed_ingress_with_source_security_group_id = [
    {
      rule                     = "postgresql-tcp"
      source_security_group_id = module.app_sg.security_group_id
    }
  ]
  number_of_computed_ingress_with_source_security_group_id = 1
  
  egress_rules = ["all-all"]
}

# RDS Database
module "db" {
  source  = "terraform-aws-modules/rds/aws"
  version = "~> 6.0"
  
  identifier = "${var.project_name}-db"
  
  engine               = "postgres"
  engine_version       = "14"
  family               = "postgres14"
  major_engine_version = "14"
  instance_class       = var.db_instance_class
  
  allocated_storage     = var.db_allocated_storage
  max_allocated_storage = var.db_allocated_storage * 2
  
  db_name  = var.db_name
  username = var.db_username
  password = var.db_password
  port     = 5432
  
  multi_az               = var.environment == "prod"
  db_subnet_group_name   = module.vpc.database_subnet_group_name
  vpc_security_group_ids = [module.db_sg.security_group_id]
  
  backup_retention_period = var.environment == "prod" ? 30 : 7
  backup_window           = "03:00-04:00"
  maintenance_window      = "mon:04:00-mon:05:00"
  
  enabled_cloudwatch_logs_exports = ["postgresql", "upgrade"]
  
  skip_final_snapshot = var.environment != "prod"
  deletion_protection = var.environment == "prod"
  
  tags = {
    Environment = var.environment
  }
}

# Auto Scaling Group
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

resource "aws_launch_template" "app" {
  name_prefix   = "${var.project_name}-"
  image_id      = data.aws_ami.amazon_linux.id
  instance_type = var.instance_type
  
  vpc_security_group_ids = [module.app_sg.security_group_id]
  
  user_data = base64encode(templatefile("${path.module}/user_data.sh", {
    db_endpoint = module.db.db_instance_endpoint
    db_name     = var.db_name
    db_username = var.db_username
    db_password = var.db_password
  }))
  
  tag_specifications {
    resource_type = "instance"
    tags = {
      Name = "${var.project_name}-app-instance"
    }
  }
}

resource "aws_autoscaling_group" "app" {
  name                = "${var.project_name}-asg"
  vpc_zone_identifier = module.vpc.private_subnets
  target_group_arns   = module.alb.target_group_arns
  health_check_type   = "ELB"
  health_check_grace_period = 300
  
  min_size         = var.asg_min_size
  max_size         = var.asg_max_size
  desired_capacity = var.asg_desired_capacity
  
  launch_template {
    id      = aws_launch_template.app.id
    version = "$Latest"
  }
  
  tag {
    key                 = "Name"
    value               = "${var.project_name}-app-instance"
    propagate_at_launch = true
  }
  
  tag {
    key                 = "Environment"
    value               = var.environment
    propagate_at_launch = true
  }
}
```

**File: `user_data.sh`**
```bash
#!/bin/bash
set -e

# Update system
yum update -y

# Install packages
yum install -y httpd postgresql15

# Install Node.js (for app server)
curl -sL https://rpm.nodesource.com/setup_18.x | bash -
yum install -y nodejs

# Create application directory
mkdir -p /var/www/app
cd /var/www/app

# Create simple Node.js app
cat > server.js <<'NODEJS'
const http = require('http');
const { Client } = require('pg');

const port = 80;
const dbConfig = {
  host: '${db_endpoint}'.split(':')[0],
  database: '${db_name}',
  user: '${db_username}',
  password: '${db_password}',
  port: 5432
};

const server = http.createServer(async (req, res) => {
  if (req.url === '/health') {
    res.writeHead(200);
    res.end('OK');
    return;
  }
  
  const client = new Client(dbConfig);
  
  try {
    await client.connect();
    const result = await client.query('SELECT version()');
    const instanceId = await fetch('http://169.254.169.254/latest/meta-data/instance-id').then(r => r.text());
    
    res.writeHead(200, { 'Content-Type': 'text/html' });
    res.end(`
      <html>
        <head><title>Three-Tier App</title></head>
        <body style="font-family: Arial; padding: 50px; text-align: center;">
          <h1>🏗️ Three-Tier Application</h1>
          <div style="background: #f0f0f0; padding: 20px; border-radius: 10px; margin: 20px;">
            <h2>Instance: $${instanceId}</h2>
            <h3>Database Connected ✅</h3>
            <p>$${result.rows[0].version}</p>
          </div>
        </body>
      </html>
    `);
  } catch (error) {
    res.writeHead(500);
    res.end('Database connection failed: ' + error.message);
  } finally {
    await client.end();
  }
});

server.listen(port, () => {
  console.log('Server running on port ' + port);
});
NODEJS

# Install dependencies
npm init -y
npm install pg

# Create systemd service
cat > /etc/systemd/system/webapp.service <<'SERVICE'
[Unit]
Description=Web Application
After=network.target

[Service]
Type=simple
User=root
WorkingDirectory=/var/www/app
ExecStart=/usr/bin/node server.js
Restart=always

[Install]
WantedBy=multi-user.target
SERVICE

# Start service
systemctl daemon-reload
systemctl enable webapp
systemctl start webapp
```

**File: `variables.tf`**
```hcl
variable "aws_region" {
  description = "AWS region"
  type        = string
  default     = "us-east-2"
}

variable "project_name" {
  description = "Project name"
  type        = string
  default     = "three-tier-app"
}

variable "environment" {
  description = "Environment (dev/prod)"
  type        = string
  default     = "dev"
}

variable "vpc_cidr" {
  description = "VPC CIDR"
  type        = string
  default     = "10.0.0.0/16"
}

variable "instance_type" {
  description = "EC2 instance type"
  type        = string
  default     = "t2.micro"
}

variable "asg_min_size" {
  description = "ASG minimum size"
  type        = number
  default     = 2
}

variable "asg_max_size" {
  description = "ASG maximum size"
  type        = number
  default     = 4
}

variable "asg_desired_capacity" {
  description = "ASG desired capacity"
  type        = number
  default     = 2
}

variable "db_instance_class" {
  description = "RDS instance class"
  type        = string
  default     = "db.t3.micro"
}

variable "db_allocated_storage" {
  description = "RDS allocated storage (GB)"
  type        = number
  default     = 20
}

variable "db_name" {
  description = "Database name"
  type        = string
  default     = "appdb"
}

variable "db_username" {
  description = "Database username"
  type        = string
  default     = "dbadmin"
}

variable "db_password" {
  description = "Database password"
  type        = string
  sensitive   = true
}
```

**File: `outputs.tf`**
```hcl
output "alb_dns_name" {
  description = "ALB DNS name"
  value       = module.alb.lb_dns_name
}

output "alb_url" {
  description = "Application URL"
  value       = "http://${module.alb.lb_dns_name}"
}

output "db_endpoint" {
  description = "Database endpoint"
  value       = module.db.db_instance_endpoint
  sensitive   = true
}
```

### Deploy

```bash
terraform init
terraform apply -var="db_password=YourSecurePassword123!"

# Wait for deployment (5-10 minutes)
# Test application
curl $(terraform output -raw alb_url)
```

### Key Takeaways

📌 **Remember:**
- Three tiers: Web, App, Database
- Public subnets for ALB only
- Private subnets for app and database
- NAT Gateway for outbound internet
- Security groups limit access between tiers
- Cost: ~$100-150/month in production

---

## Section 39: Project 4 - Multi-Region Infrastructure

### What You'll Learn
- Multi-region deployment
- Global infrastructure
- Disaster recovery
- Cross-region replication
- DNS failover

This project demonstrates deploying the same infrastructure across multiple AWS regions for high availability and disaster recovery.

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

# Primary Region
provider "aws" {
  alias  = "primary"
  region = var.primary_region
}

# Secondary Region
provider "aws" {
  alias  = "secondary"
  region = var.secondary_region
}

# Primary Region Infrastructure
module "primary_infrastructure" {
  source = "./modules/regional-infrastructure"
  
  providers = {
    aws = aws.primary
  }
  
  region       = var.primary_region
  project_name = var.project_name
  environment  = var.environment
  is_primary   = true
}

# Secondary Region Infrastructure
module "secondary_infrastructure" {
  source = "./modules/regional-infrastructure"
  
  providers = {
    aws = aws.secondary
  }
  
  region       = var.secondary_region
  project_name = var.project_name
  environment  = var.environment
  is_primary   = false
}

# Route 53 Health Checks
resource "aws_route53_health_check" "primary" {
  provider = aws.primary
  
  fqdn              = module.primary_infrastructure.alb_dns_name
  port              = 80
  type              = "HTTP"
  resource_path     = "/health"
  failure_threshold = 3
  request_interval  = 30
  
  tags = {
    Name = "${var.project_name}-primary-health-check"
  }
}

resource "aws_route53_health_check" "secondary" {
  provider = aws.secondary
  
  fqdn              = module.secondary_infrastructure.alb_dns_name
  port              = 80
  type              = "HTTP"
  resource_path     = "/health"
  failure_threshold = 3
  request_interval  = 30
  
  tags = {
    Name = "${var.project_name}-secondary-health-check"
  }
}

# Route 53 DNS with Failover
resource "aws_route53_zone" "main" {
  name = var.domain_name
}

resource "aws_route53_record" "primary" {
  zone_id = aws_route53_zone.main.zone_id
  name    = var.domain_name
  type    = "A"
  
  set_identifier  = "primary"
  health_check_id = aws_route53_health_check.primary.id
  
  failover_routing_policy {
    type = "PRIMARY"
  }
  
  alias {
    name                   = module.primary_infrastructure.alb_dns_name
    zone_id                = module.primary_infrastructure.alb_zone_id
    evaluate_target_health = true
  }
}

resource "aws_route53_record" "secondary" {
  zone_id = aws_route53_zone.main.zone_id
  name    = var.domain_name
  type    = "A"
  
  set_identifier  = "secondary"
  health_check_id = aws_route53_health_check.secondary.id
  
  failover_routing_policy {
    type = "SECONDARY"
  }
  
  alias {
    name                   = module.secondary_infrastructure.alb_dns_name
    zone_id                = module.secondary_infrastructure.alb_zone_id
    evaluate_target_health = true
  }
}
```

**File: `modules/regional-infrastructure/main.tf`**
```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

data "aws_availability_zones" "available" {
  state = "available"
}

# VPC
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "~> 5.0"
  
  name = "${var.project_name}-${var.region}-vpc"
  cidr = var.is_primary ? "10.0.0.0/16" : "10.1.0.0/16"
  
  azs            = slice(data.aws_availability_zones.available.names, 0, 2)
  public_subnets = var.is_primary ? ["10.0.1.0/24", "10.0.2.0/24"] : ["10.1.1.0/24", "10.1.2.0/24"]
  
  enable_dns_hostnames = true
  
  tags = {
    Region = var.region
  }
}

# Application Load Balancer
module "alb" {
  source  = "terraform-aws-modules/alb/aws"
  version = "~> 8.0"
  
  name = "${var.project_name}-${var.region}-alb"
  
  load_balancer_type = "application"
  vpc_id             = module.vpc.vpc_id
  subnets            = module.vpc.public_subnets
  security_groups    = [module.alb_sg.security_group_id]
  
  target_groups = [
    {
      name             = "${var.project_name}-${var.region}-tg"
      backend_protocol = "HTTP"
      backend_port     = 80
      target_type      = "instance"
      health_check = {
        path = "/health"
      }
    }
  ]
  
  http_tcp_listeners = [
    {
      port               = 80
      protocol           = "HTTP"
      target_group_index = 0
    }
  ]
}

# Security Group
module "alb_sg" {
  source  = "terraform-aws-modules/security-group/aws"
  version = "~> 5.0"
  
  name   = "${var.project_name}-${var.region}-alb-sg"
  vpc_id = module.vpc.vpc_id
  
  ingress_cidr_blocks = ["0.0.0.0/0"]
  ingress_rules       = ["http-80-tcp"]
  egress_rules        = ["all-all"]
}

# EC2 Instances for demo
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*-x86_64-gp2"]
  }
}

module "ec2_instances" {
  source  = "terraform-aws-modules/ec2-instance/aws"
  version = "~> 5.0"
  
  count = 2
  
  name = "${var.project_name}-${var.region}-${count.index + 1}"
  
  ami                         = data.aws_ami.amazon_linux.id
  instance_type               = "t2.micro"
  subnet_id                   = module.vpc.public_subnets[count.index]
  vpc_security_group_ids      = [module.alb_sg.security_group_id]
  associate_public_ip_address = true
  
  user_data = <<-EOF
              #!/bin/bash
              yum update -y
              yum install -y httpd
              systemctl start httpd
              systemctl enable httpd
              
              echo "<h1>Region: ${var.region}</h1>" > /var/www/html/index.html
              echo "<h2>Instance: $(ec2-metadata --instance-id | cut -d' ' -f2)</h2>" >> /var/www/html/index.html
              
              echo "OK" > /var/www/html/health
              EOF
}

# Attach instances to target group
resource "aws_lb_target_group_attachment" "this" {
  count = 2
  
  target_group_arn = module.alb.target_group_arns[0]
  target_id        = module.ec2_instances[count.index].id
  port             = 80
}
```

**File: `modules/regional-infrastructure/outputs.tf`**
```hcl
output "alb_dns_name" {
  value = module.alb.lb_dns_name
}

output "alb_zone_id" {
  value = module.alb.lb_zone_id
}

output "vpc_id" {
  value = module.vpc.vpc_id
}
```

### Deploy Multi-Region

```bash
terraform init
terraform apply -auto-approve

# Test primary region
curl http://$(terraform output -raw primary_alb_dns_name)

# Test secondary region
curl http://$(terraform output -raw secondary_alb_dns_name)

# Test DNS failover (requires domain setup)
curl http://yourdomain.com
```

### Key Takeaways

📌 **Remember:**
- Deploy to multiple regions for HA
- Use Route 53 for DNS failover
- Health checks monitor availability
- Automatic failover on region failure
- Cost: 2x single-region cost

---

## Section 40: Project 5 - Complete EKS Cluster

### What You'll Learn
- Amazon EKS deployment
- Kubernetes on AWS
- Node groups
- IRSA (IAM Roles for Service Accounts)
- Complete container platform

**File: `main.tf`**
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
    kubernetes = {
      source  = "hashicorp/kubernetes"
      version = "~> 2.20"
    }
  }
}

provider "aws" {
  region = var.aws_region
}

data "aws_availability_zones" "available" {}

# VPC for EKS
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "~> 5.0"
  
  name = "${var.cluster_name}-vpc"
  cidr = "10.0.0.0/16"
  
  azs             = slice(data.aws_availability_zones.available.names, 0, 3)
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24", "10.0.103.0/24"]
  
  enable_nat_gateway   = true
  single_nat_gateway   = false
  enable_dns_hostnames = true
  
  public_subnet_tags = {
    "kubernetes.io/role/elb" = 1
  }
  
  private_subnet_tags = {
    "kubernetes.io/role/internal-elb" = 1
  }
}

# EKS Cluster
module "eks" {
  source  = "terraform-aws-modules/eks/aws"
  version = "~> 19.0"
  
  cluster_name    = var.cluster_name
  cluster_version = "1.28"
  
  vpc_id                         = module.vpc.vpc_id
  subnet_ids                     = module.vpc.private_subnets
  cluster_endpoint_public_access = true
  
  eks_managed_node_group_defaults = {
    ami_type = "AL2_x86_64"
  }
  
  eks_managed_node_groups = {
    general = {
      name = "general-node-group"
      
      instance_types = ["t3.medium"]
      
      min_size     = 2
      max_size     = 4
      desired_size = 2
    }
  }
  
  tags = {
    Environment = var.environment
  }
}

# Configure kubectl
provider "kubernetes" {
  host                   = module.eks.cluster_endpoint
  cluster_ca_certificate = base64decode(module.eks.cluster_certificate_authority_data)
  
  exec {
    api_version = "client.authentication.k8s.io/v1beta1"
    command     = "aws"
    args = [
      "eks",
      "get-token",
      "--cluster-name",
      module.eks.cluster_name
    ]
  }
}

# Sample application deployment
resource "kubernetes_namespace" "demo" {
  metadata {
    name = "demo-app"
  }
}

resource "kubernetes_deployment" "demo" {
  metadata {
    name      = "demo-deployment"
    namespace = kubernetes_namespace.demo.metadata[0].name
  }
  
  spec {
    replicas = 3
    
    selector {
      match_labels = {
        app = "demo"
      }
    }
    
    template {
      metadata {
        labels = {
          app = "demo"
        }
      }
      
      spec {
        container {
          image = "nginx:latest"
          name  = "nginx"
          
          port {
            container_port = 80
          }
        }
      }
    }
  }
}

resource "kubernetes_service" "demo" {
  metadata {
    name      = "demo-service"
    namespace = kubernetes_namespace.demo.metadata[0].name
  }
  
  spec {
    selector = {
      app = "demo"
    }
    
    port {
      port        = 80
      target_port = 80
    }
    
    type = "LoadBalancer"
  }
}
```

**File: `variables.tf`**
```hcl
variable "aws_region" {
  description = "AWS region"
  type        = string
  default     = "us-east-2"
}

variable "cluster_name" {
  description = "EKS cluster name"
  type        = string
  default     = "my-eks-cluster"
}

variable "environment" {
  description = "Environment"
  type        = string
  default     = "dev"
}
```

**File: `outputs.tf`**
```hcl
output "cluster_endpoint" {
  description = "EKS cluster endpoint"
  value       = module.eks.cluster_endpoint
}

output "cluster_name" {
  description = "EKS cluster name"
  value       = module.eks.cluster_name
}

output "configure_kubectl" {
  description = "Command to configure kubectl"
  value       = "aws eks update-kubeconfig --region ${var.aws_region} --name ${module.eks.cluster_name}"
}
```

### Deploy EKS

```bash
# Deploy (takes 15-20 minutes)
terraform init
terraform apply -auto-approve

# Configure kubectl
aws eks update-kubeconfig --region us-east-2 --name my-eks-cluster

# Verify cluster
kubectl get nodes

# Check demo application
kubectl get pods -n demo-app
kubectl get svc -n demo-app

# Get LoadBalancer URL
kubectl get svc demo-service -n demo-app -o jsonpath='{.status.loadBalancer.ingress[0].hostname}'
```

### Key Takeaways

📌 **Remember:**
- EKS = Managed Kubernetes on AWS
- Node groups = EC2 instances for pods
- Use VPC with private/public subnets
- Takes 15-20 minutes to deploy
- Cost: ~$150-200/month minimum

---

## Part 9: Best Practices

---

## Section 41: Code Organization and Structure

### What You'll Learn
- Project structure best practices
- File organization
- Naming conventions
- Module organization
- Repository structure

### Recommended Project Structure

```
terraform-project/
├── .gitignore
├── README.md
├── .terraform-version
├── environments/
│   ├── dev/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   ├── terraform.tfvars
│   │   ├── backend.tf
│   │   └── outputs.tf
│   ├── staging/
│   │   └── ...
│   └── prod/
│       └── ...
├── modules/
│   ├── networking/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   ├── outputs.tf
│   │   ├── versions.tf
│   │   └── README.md
│   ├── compute/
│   │   └── ...
│   └── database/
│       └── ...
├── scripts/
│   ├── deploy.sh
│   ├── destroy.sh
│   └── validate.sh
└── docs/
    ├── architecture.md
    └── runbooks/
```

### File Organization Best Practices

#### 1. Separate Files by Purpose

**main.tf** - Core resources
```hcl
# Main infrastructure resources
resource "aws_vpc" "main" {
  # ...
}

resource "aws_subnet" "public" {
  # ...
}
```

**variables.tf** - All input variables
```hcl
variable "environment" {
  description = "Environment name"
  type        = string
}

variable "vpc_cidr" {
  description = "VPC CIDR block"
  type        = string
  default     = "10.0.0.0/16"
}
```

**outputs.tf** - All outputs
```hcl
output "vpc_id" {
  description = "VPC ID"
  value       = aws_vpc.main.id
}
```

**locals.tf** - Local values and computations
```hcl
locals {
  common_tags = {
    Environment = var.environment
    ManagedBy   = "Terraform"
    Project     = var.project_name
  }
  
  availability_zones = slice(data.aws_availability_zones.available.names, 0, var.az_count)
}
```

**data.tf** - Data sources
```hcl
data "aws_availability_zones" "available" {
  state = "available"
}

data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  # ...
}
```

**versions.tf** - Terraform and provider versions
```hcl
terraform {
  required_version = ">= 1.0"
  
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}
```

**backend.tf** - Backend configuration
```hcl
terraform {
  backend "s3" {
    bucket         = "my-terraform-state"
    key            = "prod/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true
    dynamodb_table = "terraform-locks"
  }
}
```

#### 2. Group Related Resources

**networking.tf**
```hcl
# VPC
resource "aws_vpc" "main" { }

# Subnets
resource "aws_subnet" "public" { }
resource "aws_subnet" "private" { }

# Internet Gateway
resource "aws_internet_gateway" "main" { }

# NAT Gateway
resource "aws_nat_gateway" "main" { }

# Route Tables
resource "aws_route_table" "public" { }
resource "aws_route_table" "private" { }
```

**compute.tf**
```hcl
# Launch Template
resource "aws_launch_template" "app" { }

# Auto Scaling Group
resource "aws_autoscaling_group" "app" { }

# Scaling Policies
resource "aws_autoscaling_policy" "scale_up" { }
resource "aws_autoscaling_policy" "scale_down" { }
```

**security.tf**
```hcl
# Security Groups
resource "aws_security_group" "alb" { }
resource "aws_security_group" "app" { }
resource "aws_security_group" "db" { }

# Security Group Rules
resource "aws_security_group_rule" "alb_ingress" { }
```

### Naming Conventions

#### Resource Names

```hcl
# ✅ Good - Descriptive and consistent
resource "aws_vpc" "main" { }
resource "aws_subnet" "public" { }
resource "aws_subnet" "private" { }
resource "aws_security_group" "web_server" { }
resource "aws_instance" "app_server" { }

# ❌ Bad - Unclear or inconsistent
resource "aws_vpc" "vpc1" { }
resource "aws_subnet" "sn" { }
resource "aws_security_group" "sg" { }
```

#### Variable Names

```hcl
# ✅ Good
variable "vpc_cidr_block" { }
variable "instance_type" { }
variable "enable_monitoring" { }
variable "backup_retention_days" { }

# ❌ Bad
variable "cidr" { }
variable "type" { }
variable "monitoring" { }
variable "days" { }
```

#### Tag Names

```hcl
# ✅ Good
tags = {
  Name        = "${var.project_name}-${var.environment}-vpc"
  Environment = var.environment
  ManagedBy   = "Terraform"
  CostCenter  = "Engineering"
}

# ❌ Bad
tags = {
  name = "vpc"
  env  = "prod"
}
```

### Module Organization

```
modules/
├── vpc/
│   ├── main.tf          # VPC, subnets, gateways
│   ├── variables.tf     # Input variables
│   ├── outputs.tf       # Output values
│   ├── versions.tf      # Provider requirements
│   ├── README.md        # Documentation
│   └── examples/
│       ├── basic/
│       └── complete/
├── eks-cluster/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│   ├── versions.tf
│   ├── iam.tf          # IAM roles and policies
│   ├── security.tf     # Security groups
│   └── README.md
```

### Git Repository Structure

```
.
├── .gitignore
├── .terraform-version
├── .pre-commit-config.yaml
├── README.md
├── CHANGELOG.md
├── LICENSE
├── Makefile
├── environments/
├── modules/
├── scripts/
├── docs/
└── tests/
```

**.gitignore**
```
# Terraform
.terraform/
*.tfstate
*.tfstate.*
.terraform.lock.hcl

# Sensitive
*.tfvars
!terraform.tfvars.example
secrets/

# OS
.DS_Store
Thumbs.db

# IDE
.idea/
.vscode/
*.swp
```

**README.md Template**
```markdown
# Project Name

## Description
Brief description of infrastructure

## Architecture
![Architecture Diagram](docs/architecture.png)

## Prerequisites
- Terraform >= 1.0
- AWS CLI configured
- Access to AWS account

## Usage

### Deploy to Dev
```bash
cd environments/dev
terraform init
terraform plan
terraform apply
```

### Deploy to Production
```bash
cd environments/prod
terraform init
terraform plan
# Review carefully
terraform apply
```

## Environments

| Environment | Purpose | VPC CIDR | Instance Type |
|-------------|---------|----------|---------------|
| dev | Development | 10.0.0.0/16 | t2.micro |
| staging | Pre-prod | 10.1.0.0/16 | t2.small |
| prod | Production | 10.2.0.0/16 | t2.large |

## Modules

- `vpc` - VPC with public/private subnets
- `eks-cluster` - EKS cluster setup
- `rds` - RDS database

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md)

## License
MIT
```

### Makefile for Common Tasks

**Makefile**
```makefile
.PHONY: help init plan apply destroy fmt validate

ENV ?= dev

help:
	@echo "Available targets:"
	@echo "  init      - Initialize Terraform"
	@echo "  plan      - Run terraform plan"
	@echo "  apply     - Run terraform apply"
	@echo "  destroy   - Run terraform destroy"
	@echo "  fmt       - Format code"
	@echo "  validate  - Validate configuration"
	@echo ""
	@echo "Usage: make <target> ENV=<environment>"
	@echo "Example: make plan ENV=prod"

init:
	cd environments/$(ENV) && terraform init

plan: init
	cd environments/$(ENV) && terraform plan

apply: init
	cd environments/$(ENV) && terraform apply

destroy: init
	cd environments/$(ENV) && terraform destroy

fmt:
	terraform fmt -recursive

validate: init
	cd environments/$(ENV) && terraform validate

clean:
	find . -type d -name ".terraform" -exec rm -rf {} +
	find . -type f -name "*.tfstate*" -delete
```

### Key Takeaways

📌 **Remember:**
- Separate files by purpose
- Group related resources
- Use consistent naming
- Organize modules logically
- Document everything
- Use .gitignore properly

---

## Section 42: Naming Conventions

### What You'll Learn
- Resource naming patterns
- Tag standards
- Variable naming
- Module naming
- Consistency rules

### Resource Naming Pattern

**Format:** `{project}-{environment}-{resource-type}-{purpose}`

```hcl
# VPC
resource "aws_vpc" "main" {
  tags = {
    Name = "myapp-prod-vpc"
  }
}

# Subnets
resource "aws_subnet" "public" {
  count = 2
  tags = {
    Name = "myapp-prod-subnet-public-${count.index + 1}"
  }
}

# Security Groups
resource "aws_security_group" "web" {
  name = "myapp-prod-sg-web"
  tags = {
    Name = "myapp-prod-sg-web"
  }
}

# EC2 Instances
resource "aws_instance" "app" {
  tags = {
    Name = "myapp-prod-ec2-app"
  }
}

# Load Balancer
resource "aws_lb" "main" {
  name = "myapp-prod-alb"
}

# RDS Database
resource "aws_db_instance" "main" {
  identifier = "myapp-prod-db-postgres"
}
```

### Standard Tags

**Required tags for all resources:**

```hcl
locals {
  common_tags = {
    # Required
    Name        = "${var.project_name}-${var.environment}-${var.resource_name}"
    Environment = var.environment
    ManagedBy   = "Terraform"
    
    # Recommended
    Project     = var.project_name
    Owner       = var.owner_email
    CostCenter  = var.cost_center
    
    # Optional
    CreatedBy   = data.aws_caller_identity.current.user_id
    CreatedAt   = timestamp()
    Repository  = var.repository_url
  }
}

# Apply to resources
resource "aws_instance" "app" {
  # ...
  tags = merge(
    local.common_tags,
    {
      Role = "application-server"
    }
  )
}
```

### Variable Naming

```hcl
# ✅ Good - Clear and descriptive
variable "vpc_cidr_block" {
  description = "CIDR block for VPC"
  type        = string
}

variable "instance_type" {
  description = "EC2 instance type"
  type        = string
}

variable "enable_monitoring" {
  description = "Enable detailed monitoring"
  type        = bool
}

variable "backup_retention_days" {
  description = "Number of days to retain backups"
  type        = number
}

variable "allowed_cidr_blocks" {
  description = "List of CIDR blocks allowed to access"
  type        = list(string)
}

# ❌ Bad - Unclear
variable "cidr" { }
variable "type" { }
variable "monitoring" { }
variable "days" { }
variable "cidrs" { }
```

### Module Naming

```hcl
# ✅ Good - Descriptive module names
module "vpc" {
  source = "./modules/vpc"
}

module "eks_cluster" {
  source = "./modules/eks-cluster"
}

module "rds_database" {
  source = "./modules/rds"
}

# ❌ Bad - Unclear
module "network" { }
module "k8s" { }
module "db" { }
```

### File Naming

```
✅ Good:
- main.tf
- variables.tf
- outputs.tf
- versions.tf
- backend.tf
- locals.tf
- data.tf
- networking.tf
- compute.tf
- security.tf
- iam.tf

❌ Bad:
- config.tf
- stuff.tf
- test.tf
- temp.tf
```

### Output Naming

```hcl
# ✅ Good
output "vpc_id" {
  description = "ID of the VPC"
  value       = aws_vpc.main.id
}

output "public_subnet_ids" {
  description = "IDs of public subnets"
  value       = aws_subnet.public[*].id
}

output "alb_dns_name" {
  description = "DNS name of the load balancer"
  value       = aws_lb.main.dns_name
}

# ❌ Bad
output "id" { }
output "subnets" { }
output "dns" { }
```

### Key Takeaways

📌 **Remember:**
- Use consistent naming patterns
- Include project, environment, and type
- Apply standard tags to all resources
- Make variable names descriptive
- Use kebab-case for AWS resources
- Use snake_case for Terraform identifiers

---

## Section 43: Security Best Practices

### What You'll Learn
- Secrets management
- IAM best practices
- Network security
- Encryption
- Access control

### Secrets Management

**❌ Never do this:**
```hcl
# DON'T hardcode secrets!
resource "aws_db_instance" "main" {
  username = "admin"
  password = "MyPassword123"  # ❌ WRONG!
}
```

**✅ Use variables and external sources:**

```hcl
# variables.tf
variable "db_password" {
  description = "Database password"
  type        = string
  sensitive   = true
}

# main.tf
resource "aws_db_instance" "main" {
  username = "admin"
  password = var.db_password
}
```

**Deploy with environment variables:**
```bash
export TF_VAR_db_password="SecurePassword123!"
terraform apply
```

**Or use AWS Secrets Manager:**
```hcl
data "aws_secretsmanager_secret_version" "db_password" {
  secret_id = "prod/database/password"
}

resource "aws_db_instance" "main" {
  username = "admin"
  password = jsondecode(data.aws_secretsmanager_secret_version.db_password.secret_string)["password"]
}
```

### IAM Best Practices

```hcl
# Principle of Least Privilege
resource "aws_iam_role_policy" "app" {
  role = aws_iam_role.app.id
  
  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Effect = "Allow"
        Action = [
          "s3:GetObject",
          "s3:PutObject"
        ]
        Resource = [
          "${aws_s3_bucket.app.arn}/*"
        ]
      }
    ]
  })
}

# Use IAM roles, not access keys
resource "aws_iam_instance_profile" "app" {
  name = "app-instance-profile"
  role = aws_iam_role.app.name
}

resource "aws_instance" "app" {
  # ...
  iam_instance_profile = aws_iam_instance_profile.app.name
  # No access keys needed!
}
```

### Network Security

```hcl
# Restrict security group rules
resource "aws_security_group" "web" {
  name        = "web-sg"
  description = "Security group for web servers"
  vpc_id      = aws_vpc.main.id
  
  # ✅ Good - Specific sources
  ingress {
    description = "HTTPS from ALB"
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"
    security_groups = [aws_security_group.alb.id]
  }
  
  # ❌ Bad - Too open
  # ingress {
  #   from_port   = 0
  #   to_port     = 65535
  #   protocol    = "tcp"
  #   cidr_blocks = ["0.0.0.0/0"]
  # }
  
  # ✅ Good - Specific egress
  egress {
    description = "HTTPS to internet"
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

# Private subnets for databases
resource "aws_subnet" "database" {
  vpc_id            = aws_vpc.main.id
  cidr_block        = "10.0.20.0/24"
  # No public IPs
  map_public_ip_on_launch = false
}

resource "aws_db_instance" "main" {
  # ...
  publicly_accessible = false
  db_subnet_group_name = aws_db_subnet_group.main.name
}
```

### Encryption

```hcl
# S3 encryption
resource "aws_s3_bucket" "data" {
  bucket = "my-data-bucket"
}

resource "aws_s3_bucket_server_side_encryption_configuration" "data" {
  bucket = aws_s3_bucket.data.id
  
  rule {
    apply_server_side_encryption_by_default {
      sse_algorithm     = "aws:kms"
      kms_master_key_id = aws_kms_key.s3.arn
    }
  }
}

# RDS encryption
resource "aws_db_instance" "main" {
  storage_encrypted = true
  kms_key_id        = aws_kms_key.rds.arn
}

# EBS encryption
resource "aws_instance" "app" {
  # ...
  
  root_block_device {
    encrypted   = true
    kms_key_id  = aws_kms_key.ebs.arn
  }
}

# KMS key
resource "aws_kms_key" "main" {
  description             = "KMS key for encryption"
  deletion_window_in_days = 30
  enable_key_rotation     = true
}
```

### State File Security

**backend.tf**
```hcl
terraform {
  backend "s3" {
    bucket         = "my-terraform-state"
    key            = "prod/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true  # ✅ Enable encryption
    kms_key_id     = "arn:aws:kms:us-east-2:123456789012:key/..."
    dynamodb_table = "terraform-locks"
    
    # ✅ Restrict access
    acl = "private"
  }
}
```

**S3 bucket policy:**
```hcl
resource "aws_s3_bucket_policy" "terraform_state" {
  bucket = aws_s3_bucket.terraform_state.id
  
  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Effect = "Deny"
        Principal = "*"
        Action = "s3:*"
        Resource = [
          aws_s3_bucket.terraform_state.arn,
          "${aws_s3_bucket.terraform_state.arn}/*"
        ]
        Condition = {
          Bool = {
            "aws:SecureTransport" = "false"
          }
        }
      }
    ]
  })
}
```

### Access Control

```hcl
# Bucket - Block public access
resource "aws_s3_bucket_public_access_block" "data" {
  bucket = aws_s3_bucket.data.id
  
  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}

# RDS - Restrict access
resource "aws_db_instance" "main" {
  # ...
  publicly_accessible    = false
  backup_retention_period = 30  # ✅ Enable backups
  deletion_protection    = true  # ✅ Prevent accidental deletion
  
  enabled_cloudwatch_logs_exports = ["postgresql", "upgrade"]  # ✅ Enable logging
}

# Enable MFA delete for S3
resource "aws_s3_bucket_versioning" "data" {
  bucket = aws_s3_bucket.data.id
  
  versioning_configuration {
    status     = "Enabled"
    mfa_delete = "Enabled"
  }
}
```

### Key Takeaways

📌 **Remember:**
- Never hardcode secrets
- Use IAM roles, not access keys
- Encrypt everything (data at rest and in transit)
- Apply least privilege principle
- Enable logging and monitoring
- Use private subnets for sensitive resources
- Enable backup and versioning

---

## Section 44: Version Control Strategies

### What You'll Learn
- Git workflow for Terraform
- Branching strategies
- Pull request process
- CI/CD integration
- Code reviews

### Git Workflow

**Recommended branch structure:**
```
main (production)
├── develop (integration)
│   ├── feature/new-vpc
│   ├── feature/add-monitoring
│   └── bugfix/sg-rules
└── hotfix/critical-security-patch
```

### .gitignore for Terraform

```gitignore
# Local .terraform directories
**/.terraform/*

# .tfstate files
*.tfstate
*.tfstate.*

# Crash log files
crash.log
crash.*.log

# Exclude all .tfvars files
*.tfvars
*.tfvars.json

# Keep example tfvars
!terraform.tfvars.example

# Ignore override files
override.tf
override.tf.json
*_override.tf
*_override.tf.json

# CLI configuration files
.terraformrc
terraform.rc

# Sensitive files
secrets/
*.pem
*.key

# IDE
.idea/
.vscode/
*.swp
*.swo

# OS
.DS_Store
Thumbs.db
```

### Pre-commit Hooks

**.pre-commit-config.yaml**
```yaml
repos:
  - repo: https://github.com/antonbabenko/pre-commit-terraform
    rev: v1.83.5
    hooks:
      - id: terraform_fmt
      - id: terraform_validate
      - id: terraform_docs
      - id: terraform_tflint
      - id: terraform_tfsec
```

**Install:**
```bash
pip install pre-commit
pre-commit install
```

### Pull Request Template

**.github/pull_request_template.md**
```markdown
## Description
Brief description of changes

## Type of Change
- [ ] New feature
- [ ] Bug fix
- [ ] Breaking change
- [ ] Documentation update

## Checklist
- [ ] Code follows style guidelines
- [ ] Ran `terraform fmt`
- [ ] Ran `terraform validate`
- [ ] Tested in dev environment
- [ ] Updated documentation
- [ ] No sensitive data in code

## Testing
Describe how you tested these changes

## Terraform Plan Output
```
Paste terraform plan output here
```

## Screenshots (if applicable)
```

### Branching Strategy

**Feature workflow:**
```bash
# Create feature branch
git checkout develop
git pull origin develop
git checkout -b feature/add-monitoring

# Make changes
# Edit files...

# Commit
git add .
git commit -m "feat: add CloudWatch monitoring"

# Push
git push origin feature/add-monitoring

# Create pull request to develop
```

**Release workflow:**
```bash
# Create release branch from develop
git checkout develop
git pull origin develop
git checkout -b release/v1.2.0

# Update version numbers, changelog
# Test thoroughly

# Merge to main
git checkout main
git merge release/v1.2.0
git tag -a v1.2.0 -m "Release v1.2.0"
git push origin main --tags

# Merge back to develop
git checkout develop
git merge release/v1.2.0
git push origin develop
```

### Commit Message Convention

**Format:** `<type>(<scope>): <subject>`

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation
- `style`: Formatting
- `refactor`: Code refactoring
- `test`: Tests
- `chore`: Maintenance

**Examples:**
```bash
git commit -m "feat(vpc): add NAT gateway for private subnets"
git commit -m "fix(security): restrict security group ingress rules"
git commit -m "docs(readme): update deployment instructions"
git commit -m "refactor(modules): reorganize VPC module structure"
```

### CI/CD Pipeline

**.github/workflows/terraform.yml**
```yaml
name: Terraform CI/CD

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main, develop]

env:
  TF_VERSION: 1.6.0

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v2
        with:
          terraform_version: ${{ env.TF_VERSION }}
      
      - name: Terraform Format Check
        run: terraform fmt -check -recursive
      
      - name: Terraform Init
        run: terraform init -backend=false
      
      - name: Terraform Validate
        run: terraform validate
  
  security:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Run tfsec
        uses: aquasecurity/tfsec-action@v1.0.0
  
  plan:
    needs: [validate, security]
    runs-on: ubuntu-latest
    if: github.event_name == 'pull_request'
    steps:
      - uses: actions/checkout@v3
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v2
        with:
          terraform_version: ${{ env.TF_VERSION }}
      
      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v2
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: us-east-2
      
      - name: Terraform Init
        run: terraform init
      
      - name: Terraform Plan
        run: terraform plan -no-color
        continue-on-error: true
      
      - name: Comment PR
        uses: actions/github-script@v6
        with:
          script: |
            github.rest.issues.createComment({
              issue_number: context.issue.number,
              owner: context.repo.owner,
              repo: context.repo.repo,
              body: '## Terraform Plan\n```\n' + process.env.PLAN_OUTPUT + '\n```'
            })
  
  apply:
    needs: [validate, security]
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main' && github.event_name == 'push'
    steps:
      - uses: actions/checkout@v3
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v2
        with:
          terraform_version: ${{ env.TF_VERSION }}
      
      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v2
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: us-east-2
      
      - name: Terraform Init
        run: terraform init
      
      - name: Terraform Apply
        run: terraform apply -auto-approve
```

### Key Takeaways

📌 **Remember:**
- Use feature branches
- Write descriptive commit messages
- Use pre-commit hooks
- Require code reviews
- Automate with CI/CD
- Never commit secrets
- Keep main branch protected

---

## Section 45: Documentation Standards

### What You'll Learn
- Documentation best practices
- README templates
- Inline comments
- Architecture diagrams
- Runbooks

### README.md Template

```markdown
# Project Name

[![Terraform](https://img.shields.io/badge/Terraform-1.6+-purple)](https://www.terraform.io/)
[![AWS](https://img.shields.io/badge/AWS-Provider-orange)](https://registry.terraform.io/providers/hashicorp/aws)

## Overview

Brief description of what this infrastructure does.

## Architecture

```
┌──────────────┐
│   Internet   │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│     ALB      │
└──────┬───────┘
       │
   ┌───┴───┐
   │       │
   ▼       ▼
┌─────┐ ┌─────┐
│ EC2 │ │ EC2 │
└──┬──┘ └──┬──┘
   │       │
   └───┬───┘
       ▼
   ┌────────┐
   │  RDS   │
   └────────┘
```

## Prerequisites

- Terraform >= 1.6.0
- AWS CLI configured
- AWS Account with appropriate permissions

## Quick Start

```bash
# Clone repository
git clone https://github.com/org/repo.git
cd repo

# Initialize
terraform init

# Plan
terraform plan

# Apply
terraform apply
```

## Environments

| Environment | AWS Account | Region | VPC CIDR |
|-------------|-------------|--------|----------|
| dev         | 123456789012 | us-east-2 | 10.0.0.0/16 |
| staging     | 234567890123 | us-east-2 | 10.1.0.0/16 |
| prod        | 345678901234 | us-east-2 | 10.2.0.0/16 |

## Modules

### VPC Module
Creates VPC with public and private subnets.

[Documentation](modules/vpc/README.md)

### EKS Module
Deploys managed Kubernetes cluster.

[Documentation](modules/eks/README.md)

## Usage Examples

### Deploy to Development

```bash
cd environments/dev
terraform init
terraform apply
```

### Deploy to Production

```bash
cd environments/prod
terraform init
terraform plan -out=tfplan

# Review plan carefully
terraform show tfplan

# Apply
terraform apply tfplan
```

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| project_name | Project name | `string` | - | yes |
| environment | Environment name | `string` | - | yes |
| vpc_cidr | VPC CIDR block | `string` | `10.0.0.0/16` | no |

## Outputs

| Name | Description |
|------|-------------|
| vpc_id | VPC ID |
| alb_dns_name | Load balancer DNS name |
| db_endpoint | Database endpoint |

## Cost Estimation

Approximate monthly costs (us-east-2):

- **Development**: ~$50/month
  - 2x t2.micro EC2: $15
  - 1x NAT Gateway: $32
  - RDS db.t3.micro: $15
  
- **Production**: ~$500/month
  - 4x t2.large EC2: $300
  - 2x NAT Gateway: $64
  - RDS db.t3.large Multi-AZ: $300

## Security

- All data encrypted at rest
- Private subnets for application tier
- Security groups with least privilege
- No hardcoded secrets
- MFA required for production

## Disaster Recovery

- RDS automated backups: 30 days
- Cross-region replication enabled
- Infrastructure as Code in git
- RTO: 1 hour
- RPO: 5 minutes

## Troubleshooting

### Issue: Terraform state locked

**Solution:**
```bash
terraform force-unlock <LOCK_ID>
```

### Issue: Cannot destroy resources

**Solution:**
Check for lifecycle `prevent_destroy` rules.

## Contributing

1. Fork the repository
2. Create feature branch
3. Commit changes
4. Push to branch
5. Create pull request

## License

MIT License - see [LICENSE](LICENSE)

## Contact

- Team: DevOps Team
- Email: devops@company.com
- Slack: #infrastructure
```

### Module README Template

**modules/vpc/README.md**
```markdown
# VPC Module

Creates a VPC with public and private subnets across multiple availability zones.

## Features

- ✅ VPC with custom CIDR
- ✅ Public and private subnets
- ✅ Internet Gateway
- ✅ NAT Gateways (configurable)
- ✅ Route tables
- ✅ VPC Flow Logs

## Usage

```hcl
module "vpc" {
  source = "./modules/vpc"
  
  name               = "my-vpc"
  cidr_block         = "10.0.0.0/16"
  availability_zones = ["us-east-2a", "us-east-2b"]
  
  public_subnet_cidrs  = ["10.0.1.0/24", "10.0.2.0/24"]
  private_subnet_cidrs = ["10.0.11.0/24", "10.0.12.0/24"]
  
  enable_nat_gateway = true
  single_nat_gateway = false
}
```

## Inputs

[Full input table]

## Outputs

[Full output table]

## Examples

- [Basic](examples/basic) - Minimal configuration
- [Complete](examples/complete) - All features

## Notes

- NAT Gateway costs ~$32/month per gateway
- Use `single_nat_gateway = true` for dev to save costs
```

### Inline Comments

**Good commenting:**
```hcl
# Security group for web servers
# Allows HTTP/HTTPS from ALB only
resource "aws_security_group" "web" {
  name        = "${var.project_name}-web-sg"
  description = "Security group for web application servers"
  vpc_id      = aws_vpc.main.id
  
  # Allow HTTP from ALB
  ingress {
    description     = "HTTP from ALB"
    from_port       = 80
    to_port         = 80
    protocol        = "tcp"
    security_groups = [aws_security_group.alb.id]
  }
  
  # Allow all outbound traffic
  # Required for package updates and external API calls
  egress {
    description = "All outbound traffic"
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

### CHANGELOG.md

```markdown
# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased]

## [2.0.0] - 2024-01-15

### Breaking Changes
- Changed VPC module variable `azs` to `availability_zones`
- Removed `enable_dns` variable (always enabled now)

### Added
- Multi-region support
- CloudWatch dashboards
- VPC Flow Logs

### Changed
- Updated AWS provider to 5.0
- Improved security group rules

### Fixed
- NAT Gateway routing issue
- RDS backup window conflict

## [1.0.0] - 2023-12-01

### Added
- Initial release
- VPC module
- EKS module
- RDS module
```

### Architecture Documentation

**docs/architecture.md**
```markdown
# Architecture Overview

## High-Level Architecture

[Diagram]

## Network Architecture

### VPC Design
- CIDR: 10.0.0.0/16
- 3 Availability Zones
- Public subnets: 10.0.1.0/24, 10.0.2.0/24, 10.0.3.0/24
- Private subnets: 10.0.11.0/24, 10.0.12.0/24, 10.0.13.0/24

### Security Layers

1. **Internet Gateway** - Entry point
2. **Application Load Balancer** - Public subnet
3. **Application Servers** - Private subnet
4. **Database** - Private subnet, no internet access

## Data Flow

1. User → CloudFront → ALB
2. ALB → EC2 (round-robin)
3. EC2 → RDS (private connection)
4. EC2 → Internet (via NAT Gateway)

## Disaster Recovery

- RTO: 1 hour
- RPO: 5 minutes
- Multi-AZ deployment
- Automated backups
- Cross-region replication
```

### Key Takeaways

📌 **Remember:**
- Document everything
- Use templates
- Include examples
- Add architecture diagrams
- Maintain changelog
- Write clear comments
- Keep docs updated

---

## Part 10: Operations

---

## Section 46: Complete Terraform Commands Reference

### What You'll Learn
- All terraform commands
- Command options
- Common use cases
- Tips and tricks

### Essential Commands

#### terraform init
```bash
# Basic initialization
terraform init

# Upgrade providers
terraform init -upgrade

# Reconfigure backend
terraform init -reconfigure

# Don't download plugins (use cache)
terraform init -plugin-dir=./terraform-plugins

# Migrate state
terraform init -migrate-state
```

#### terraform plan
```bash
# Basic plan
terraform plan

# Save plan to file
terraform plan -out=tfplan

# Target specific resource
terraform plan -target=aws_instance.web

# Show detailed changes
terraform plan -detailed-exitcode

# Refresh state before planning
terraform plan -refresh=true

# Use specific var file
terraform plan -var-file="prod.tfvars"

# Set variable
terraform plan -var="instance_type=t2.large"

# Destroy plan
terraform plan -destroy
```

#### terraform apply
```bash
# Basic apply (with approval prompt)
terraform apply

# Auto approve
terraform apply -auto-approve

# Apply saved plan
terraform apply tfplan

# Target specific resource
terraform apply -target=aws_instance.web

# Apply with variables
terraform apply -var="environment=prod"

# Parallelism (default 10)
terraform apply -parallelism=20

# Apply without refresh
terraform apply -refresh=false
```

#### terraform destroy
```bash
# Destroy all resources
terraform destroy

# Auto approve
terraform destroy -auto-approve

# Target specific resource
terraform destroy -target=aws_instance.web

# Destroy with variables
terraform destroy -var-file="prod.tfvars"
```

#### terraform show
```bash
# Show current state
terraform show

# Show specific plan
terraform show tfplan

# JSON output
terraform show -json

# Show specific state file
terraform show terraform.tfstate
```

#### terraform output
```bash
# Show all outputs
terraform output

# Show specific output
terraform output vpc_id

# Raw output (no quotes)
terraform output -raw alb_dns_name

# JSON output
terraform output -json
```

### State Management Commands

#### terraform state list
```bash
# List all resources
terraform state list

# Filter by pattern
terraform state list aws_instance.*

# List specific module
terraform state list module.vpc
```

#### terraform state show
```bash
# Show specific resource
terraform state show aws_instance.web

# Show with full details
terraform state show -json aws_instance.web
```

#### terraform state mv
```bash
# Rename resource
terraform state mv aws_instance.web aws_instance.app

# Move to module
terraform state mv aws_instance.web module.compute.aws_instance.web

# Move module
terraform state mv module.old_vpc module.new_vpc
```

#### terraform state rm
```bash
# Remove resource from state
terraform state rm aws_instance.web

# Remove module
terraform state rm module.vpc

# Remove all instances of resource
terraform state rm 'aws_instance.web[*]'
```

#### terraform state pull
```bash
# Download remote state
terraform state pull > terraform.tfstate

# View remote state
terraform state pull | jq .
```

#### terraform state push
```bash
# Upload local state
terraform state push terraform.tfstate

# Force push (dangerous!)
terraform state push -force terraform.tfstate
```

### Workspace Commands

```bash
# List workspaces
terraform workspace list

# Show current workspace
terraform workspace show

# Create new workspace
terraform workspace new dev

# Select workspace
terraform workspace select prod

# Delete workspace
terraform workspace delete dev
```

### Other Useful Commands

#### terraform fmt
```bash
# Format current directory
terraform fmt

# Format recursively
terraform fmt -recursive

# Check if formatted
terraform fmt -check

# Show differences
terraform fmt -diff
```

#### terraform validate
```bash
# Validate configuration
terraform validate

# JSON output
terraform validate -json
```

#### terraform graph
```bash
# Generate dependency graph
terraform graph

# Generate and view
terraform graph | dot -Tpng > graph.png
open graph.png

# Specific plan graph
terraform graph -plan=tfplan
```

#### terraform console
```bash
# Interactive console
terraform console

# Test expressions
> var.vpc_cidr
"10.0.0.0/16"

> aws_vpc.main.id
"vpc-12345"

> length(var.availability_zones)
3
```

#### terraform import
```bash
# Import existing resource
terraform import aws_instance.web i-1234567890abcdef0

# Import with module
terraform import module.vpc.aws_vpc.main vpc-12345
```

#### terraform taint / untaint
```bash
# Mark resource for recreation (deprecated, use -replace)
terraform apply -replace=aws_instance.web

# Old way (deprecated)
terraform taint aws_instance.web
terraform untaint aws_instance.web
```

#### terraform refresh
```bash
# Refresh state (deprecated, use apply -refresh-only)
terraform apply -refresh-only

# Old way
terraform refresh
```

#### terraform providers
```bash
# List providers
terraform providers

# Show provider versions
terraform version

# Lock providers
terraform providers lock
```

### Advanced Options

#### Environment Variables
```bash
# Set log level
export TF_LOG=DEBUG
export TF_LOG=TRACE
export TF_LOG=INFO

# Log to file
export TF_LOG_PATH=terraform.log

# Set variables
export TF_VAR_instance_type=t2.large
export TF_VAR_environment=production

# Disable color
export TF_CLI_ARGS="-no-color"

# Custom plugin directory
export TF_PLUGIN_CACHE_DIR="$HOME/.terraform.d/plugin-cache"
```

#### Common Workflows

**Complete deployment:**
```bash
terraform fmt -recursive
terraform validate
terraform plan -out=tfplan
terraform show tfplan
terraform apply tfplan
```

**Safe destroy:**
```bash
terraform plan -destroy -out=destroy.tfplan
terraform show destroy.tfplan
terraform apply destroy.tfplan
```

**State operations:**
```bash
# Backup state
terraform state pull > backup.tfstate

# Move resource
terraform state mv aws_instance.old aws_instance.new

# Remove from state
terraform state rm aws_instance.temporary

# Import existing
terraform import aws_instance.existing i-1234567
```

### Key Takeaways

📌 **Remember:**
- Always use `terraform plan` before `apply`
- Use `-out` to save plans
- Use `-target` carefully (can cause state drift)
- Back up state before risky operations
- Use workspaces for multiple environments
- Enable logging when debugging

---

## Section 47: Debugging and Troubleshooting

### What You'll Learn
- Common errors and solutions
- Debugging techniques
- Log analysis
- State issues
- Provider problems

### Enable Debugging

```bash
# Set log level
export TF_LOG=DEBUG
terraform apply

# Log levels:
# TRACE - Most verbose
# DEBUG - Detailed
# INFO  - General info
# WARN  - Warnings
# ERROR - Errors only

# Log to file
export TF_LOG=TRACE
export TF_LOG_PATH=./terraform-debug.log
terraform apply
```

### Common Errors and Solutions

#### Error: State Lock

**Error:**
```
Error: Error acquiring the state lock

Error message: ConditionalCheckFailedException: The conditional request failed
Lock Info:
  ID:        abc123-def456
  Path:      s3-bucket/terraform.tfstate
  Operation: OperationTypeApply
  Who:       user@hostname
  Version:   1.6.0
  Created:   2024-01-15 10:00:00
```

**Solutions:**
```bash
# Option 1: Wait (if someone is running terraform)
# Wait for lock to release

# Option 2: Force unlock (if lock is stuck)
terraform force-unlock abc123-def456

# Option 3: Manual DynamoDB cleanup
aws dynamodb delete-item \
  --table-name terraform-locks \
  --key '{"LockID": {"S": "my-state-bucket/terraform.tfstate-md5"}}'
```

#### Error: Resource Already Exists

**Error:**
```
Error: Error creating VPC: VpcLimitExceeded: The maximum number of VPCs has been reached
```

**Solutions:**
```bash
# Option 1: Import existing resource
terraform import aws_vpc.main vpc-12345

# Option 2: Delete unused resources
aws ec2 describe-vpcs
aws ec2 delete-vpc --vpc-id vpc-unused

# Option 3: Request limit increase
# Go to AWS Service Quotas
```

#### Error: Credentials

**Error:**
```
Error: error configuring Terraform AWS Provider: no valid credential sources found
```

**Solutions:**
```bash
# Check AWS credentials
aws sts get-caller-identity

# Configure credentials
aws configure

# Set explicitly
export AWS_ACCESS_KEY_ID=xxx
export AWS_SECRET_ACCESS_KEY=xxx
export AWS_DEFAULT_REGION=us-east-2

# Use profile
export AWS_PROFILE=myprofile
```

#### Error: State Out of Sync

**Error:**
```
Error: resource already exists
```

**Solutions:**
```bash
# Option 1: Refresh state
terraform apply -refresh-only

# Option 2: Import missing resource
terraform import aws_instance.web i-1234567

# Option 3: Remove from state and re-import
terraform state rm aws_instance.web
terraform import aws_instance.web i-1234567
```

#### Error: Cycle Dependency

**Error:**
```
Error: Cycle: aws_security_group.app, aws_security_group.db
```

**Solution:**
```hcl
# Bad - Circular dependency
resource "aws_security_group" "app" {
  ingress {
    security_groups = [aws_security_group.db.id]
  }
}

resource "aws_security_group" "db" {
  ingress {
    security_groups = [aws_security_group.app.id]
  }
}

# Good - Use security group rules
resource "aws_security_group" "app" {
  # No ingress here
}

resource "aws_security_group" "db" {
  # No ingress here
}

resource "aws_security_group_rule" "app_to_db" {
  type                     = "ingress"
  from_port                = 5432
  to_port                  = 5432
  protocol                 = "tcp"
  source_security_group_id = aws_security_group.app.id
  security_group_id        = aws_security_group.db.id
}
```

#### Error: Module Not Found

**Error:**
```
Error: Module not installed
```

**Solution:**
```bash
# Reinitialize
terraform init

# Upgrade modules
terraform init -upgrade

# Clean and reinit
rm -rf .terraform
terraform init
```

### Debugging Techniques

#### 1. Plan Analysis

```bash
# Detailed plan
terraform plan -out=tfplan
terraform show -json tfplan | jq .

# Check specific resource
terraform plan -target=aws_instance.web

# Show what would be destroyed
terraform plan -destroy
```

#### 2. State Investigation

```bash
# List all resources
terraform state list

# Show specific resource
terraform state show aws_instance.web

# Pull state locally
terraform state pull > state.json
jq . state.json

# Compare states
diff <(terraform state pull) state-backup.json
```

#### 3. Resource Inspection

```bash
# Show outputs
terraform output -json

# Refresh and show
terraform apply -refresh-only
terraform show

# Console for testing
terraform console
> aws_instance.web.public_ip
> var.vpc_cidr
```

#### 4. Provider Debug

```bash
# Enable provider logging
export TF_LOG_PROVIDER=TRACE
export TF_LOG_PATH_PROVIDER=./provider.log

terraform apply

# Check provider configuration
terraform providers
```

### Troubleshooting Workflow

**Step 1: Identify the Error**
```bash
# Enable verbose logging
export TF_LOG=DEBUG
terraform apply 2>&1 | tee debug.log
```

**Step 2: Check State**
```bash
# Verify state
terraform state list
terraform state show <resource>
```

**Step 3: Validate Configuration**
```bash
# Format and validate
terraform fmt -recursive
terraform validate
```

**Step 4: Test in Isolation**
```bash
# Target specific resource
terraform plan -target=aws_instance.web
terraform apply -target=aws_instance.web
```

**Step 5: Check AWS Console**
```bash
# Verify in AWS
aws ec2 describe-instances
aws ec2 describe-vpcs
aws rds describe-db-instances
```

### State Recovery

**Backup state before operations:**
```bash
# Pull current state
terraform state pull > backup-$(date +%Y%m%d-%H%M%S).tfstate

# Restore state
terraform state push backup-20240115-100000.tfstate
```

**Recover from corrupted state:**
```bash
# List backups (if using S3 backend with versioning)
aws s3api list-object-versions \
  --bucket my-terraform-state \
  --prefix terraform.tfstate

# Download specific version
aws s3api get-object \
  --bucket my-terraform-state \
  --key terraform.tfstate \
  --version-id <version-id> \
  recovered-state.tfstate

# Restore
terraform state push recovered-state.tfstate
```

### Performance Issues

```bash
# Increase parallelism
terraform apply -parallelism=20

# Target specific resources
terraform apply -target=module.vpc

# Disable refresh for known state
terraform apply -refresh=false
```

### Key Takeaways

📌 **Remember:**
- Enable logging for debugging
- Always backup state before risky operations
- Use `terraform console` to test expressions
- Check AWS console to verify resources
- Use `-target` to isolate issues
- Force-unlock only when necessary

---

## Section 48: Performance Optimization

### What You'll Learn
- Optimizing plan/apply time
- Module performance
- State management
- Provider configuration
- Best practices

### Parallelism

```bash
# Default parallelism is 10
terraform apply

# Increase parallelism
terraform apply -parallelism=20

# For large infrastructures
terraform apply -parallelism=50

# Balance between speed and API rate limits
```

### Reduce Plan Time

#### 1. Skip Refresh
```bash
# Don't refresh state during plan (if state is current)
terraform plan -refresh=false
terraform apply -refresh=false
```

#### 2. Target Specific Resources
```bash
# Only plan/apply specific resources
terraform plan -target=module.vpc
terraform apply -target=module.compute
```

#### 3. Use Depends_on Carefully
```hcl
# ❌ Bad - Unnecessary dependency
resource "aws_instance" "app" {
  # ...
  depends_on = [aws_vpc.main]  # Not needed, implicit
}

# ✅ Good - Only when necessary
resource "aws_instance" "app" {
  # ...
  depends_on = [null_resource.configuration]
}
```

### Optimize Module Usage

#### 1. Module Caching
```bash
# Set plugin cache directory
export TF_PLUGIN_CACHE_DIR="$HOME/.terraform.d/plugin-cache"
mkdir -p $TF_PLUGIN_CACHE_DIR

# Providers will be cached and reused
terraform init
```

#### 2. Selective Module Updates
```bash
# Only update specific modules
terraform init -upgrade=false

# Update specific provider
terraform init -upgrade \
  -target=registry.terraform.io/hashicorp/aws
```

### State Management Performance

#### 1. Smaller State Files
```hcl
# Split large infrastructures into multiple state files

# Instead of one huge state:
terraform/
└── main.tf  # 1000 resources

# Use separate states:
terraform/
├── networking/   # 50 resources
├── compute/      # 200 resources
├── database/     # 50 resources
└── monitoring/   # 100 resources
```

#### 2. Partial Configuration
```hcl
# backend.tf
terraform {
  backend "s3" {}
}
```

```bash
# Configure at init time
terraform init \
  -backend-config="bucket=my-state" \
  -backend-config="key=path/terraform.tfstate" \
  -backend-config="region=us-east-2"
```

### Resource Optimization

#### 1. Use Data Sources Efficiently
```hcl
# ❌ Bad - Multiple data source calls
data "aws_ami" "app1" {
  most_recent = true
  owners      = ["amazon"]
  # ...
}

data "aws_ami" "app2" {
  most_recent = true
  owners      = ["amazon"]
  # ... same filters
}

# ✅ Good - Reuse data source
data "aws_ami" "amazon_linux" {
  most_recent = true
  owners      = ["amazon"]
  # ...
}

resource "aws_instance" "app1" {
  ami = data.aws_ami.amazon_linux.id
}

resource "aws_instance" "app2" {
  ami = data.aws_ami.amazon_linux.id
}
```

#### 2. Minimize API Calls
```hcl
# ❌ Bad - Separate calls for each AZ
data "aws_availability_zones" "az1" {
  filter {
    name   = "zone-name"
    values = ["us-east-2a"]
  }
}

data "aws_availability_zones" "az2" {
  filter {
    name   = "zone-name"
    values = ["us-east-2b"]
  }
}

# ✅ Good - Single call
data "aws_availability_zones" "available" {
  state = "available"
}

locals {
  az1 = data.aws_availability_zones.available.names[0]
  az2 = data.aws_availability_zones.available.names[1]
}
```

### Provider Configuration

```hcl
# Configure retries and timeouts
provider "aws" {
  region = "us-east-2"
  
  # Retry configuration
  max_retries = 3
  
  # Custom endpoints for testing (faster)
  endpoints {
    ec2 = "http://localhost:4566"  # LocalStack
  }
}

# Use assume role efficiently
provider "aws" {
  region = "us-east-2"
  
  assume_role {
    role_arn     = "arn:aws:iam::123456789012:role/TerraformRole"
    session_name = "terraform"
  }
}
```

### For_each vs Count Performance

```hcl
# for_each is more efficient for updates
resource "aws_instance" "app" {
  for_each = toset(["app1", "app2", "app3"])
  
  ami           = data.aws_ami.amazon_linux.id
  instance_type = "t2.micro"
  
  tags = {
    Name = each.key
  }
}

# Removing "app2" only destroys one instance
# With count, might recreate multiple instances
```

### CI/CD Optimization

```yaml
# Cache Terraform files
- name: Cache Terraform
  uses: actions/cache@v3
  with:
    path: |
      ~/.terraform.d/plugin-cache
      .terraform
    key: ${{ runner.os }}-terraform-${{ hashFiles('**/.terraform.lock.hcl') }}

# Parallel execution
jobs:
  networking:
    runs-on: ubuntu-latest
    # ...
  
  compute:
    needs: networking
    runs-on: ubuntu-latest
    # ...
  
  database:
    needs: networking
    runs-on: ubuntu-latest
    # ...
```

### Large Infrastructure Tips

**1. Use Terraform Cloud/Enterprise**
- Remote execution (faster runners)
- State caching
- Parallel runs
- Sentinel policies

**2. Workspace Strategy**
```bash
# Separate workspaces for different components
terraform/
├── foundation/      # VPC, IAM (rarely changes)
├── compute/         # EC2, ASG (changes often)
└── application/     # App-specific resources
```

**3. Targeted Operations**
```bash
# Deploy only changed modules
./deploy.sh --target=module.compute

# Script example:
#!/bin/bash
terraform plan -out=tfplan
terraform show -json tfplan | jq -r '.resource_changes[]' | grep module.compute
if [ $? -eq 0 ]; then
  terraform apply -target=module.compute -auto-approve
fi
```

### Benchmarking

```bash
# Time operations
time terraform plan
time terraform apply -auto-approve

# Profile with detailed logging
export TF_LOG=TRACE
export TF_LOG_PATH=terraform.log
time terraform plan

# Analyze log for slow operations
grep "elapsed" terraform.log | sort -k3 -n
```

### Key Takeaways

📌 **Remember:**
- Use parallelism for large infrastructures
- Cache plugins and modules
- Split large states into smaller ones
- Use for_each instead of count when possible
- Target specific resources when debugging
- Minimize API calls with data sources
- Monitor and optimize regularly

---

## Section 49: Disaster Recovery

### What You'll Learn
- Backup strategies
- State recovery
- Infrastructure recovery
- Runbooks
- Testing DR plan

### State Backup Strategies

#### 1. S3 Backend with Versioning

```hcl
# backend.tf
terraform {
  backend "s3" {
    bucket         = "terraform-state-backup"
    key            = "prod/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true
    versioning     = true  # ✅ Enable versioning
    dynamodb_table = "terraform-locks"
  }
}
```

**S3 bucket configuration:**
```hcl
resource "aws_s3_bucket" "terraform_state" {
  bucket = "terraform-state-backup"
}

resource "aws_s3_bucket_versioning" "terraform_state" {
  bucket = aws_s3_bucket.terraform_state.id
  
  versioning_configuration {
    status = "Enabled"
  }
}

resource "aws_s3_bucket_lifecycle_configuration" "terraform_state" {
  bucket = aws_s3_bucket.terraform_state.id
  
  rule {
    id     = "keep-versions"
    status = "Enabled"
    
    noncurrent_version_expiration {
      noncurrent_days = 90
    }
  }
}
```

#### 2. Automated Backups

**Backup script:**
```bash
#!/bin/bash
# backup-state.sh

BACKUP_DIR="./state-backups"
TIMESTAMP=$(date +%Y%m%d-%H%M%S)

mkdir -p $BACKUP_DIR

# Pull current state
terraform state pull > "$BACKUP_DIR/terraform-$TIMESTAMP.tfstate"

# Keep only last 30 days
find $BACKUP_DIR -name "terraform-*.tfstate" -mtime +30 -delete

echo "State backed up to $BACKUP_DIR/terraform-$TIMESTAMP.tfstate"
```

**Cron job:**
```bash
# Run daily at 2 AM
0 2 * * * cd /path/to/terraform && ./backup-state.sh
```

#### 3. Cross-Region Replication

```hcl
# Primary region bucket
resource "aws_s3_bucket" "terraform_state_primary" {
  bucket = "terraform-state-us-east-2"
  
  provider = aws.us_east_2
}

# Replication bucket
resource "aws_s3_bucket" "terraform_state_replica" {
  bucket = "terraform-state-us-west-2"
  
  provider = aws.us_west_2
}

# Replication configuration
resource "aws_s3_bucket_replication_configuration" "replication" {
  bucket = aws_s3_bucket.terraform_state_primary.id
  role   = aws_iam_role.replication.arn
  
  rule {
    id     = "replicate-state"
    status = "Enabled"
    
    destination {
      bucket        = aws_s3_bucket.terraform_state_replica.arn
      storage_class = "STANDARD_IA"
    }
  }
  
  provider = aws.us_east_2
}
```

### Recovery Procedures

#### Scenario 1: Corrupted State File

**Recovery steps:**
```bash
# 1. List available versions
aws s3api list-object-versions \
  --bucket terraform-state-backup \
  --prefix prod/terraform.tfstate

# 2. Download previous version
aws s3api get-object \
  --bucket terraform-state-backup \
  --key prod/terraform.tfstate \
  --version-id <VERSION_ID> \
  recovered-state.tfstate

# 3. Validate recovered state
terraform state pull > current-state.tfstate
diff recovered-state.tfstate current-state.tfstate

# 4. Push recovered state
terraform state push recovered-state.tfstate

# 5. Verify
terraform plan
```

#### Scenario 2: Accidental Destroy

**Recovery steps:**
```bash
# 1. Restore previous state
aws s3api get-object \
  --bucket terraform-state-backup \
  --key prod/terraform.tfstate \
  --version-id <BEFORE_DESTROY_VERSION> \
  restored.tfstate

# 2. Push restored state
terraform state push restored.tfstate

# 3. Re-create resources
terraform plan
terraform apply
```

#### Scenario 3: Lost State File

**Recovery steps:**
```bash
# 1. Create new empty state
terraform init

# 2. Import existing resources
terraform import aws_vpc.main vpc-12345
terraform import aws_subnet.public[0] subnet-12345
terraform import aws_subnet.public[1] subnet-67890
# ... import all resources

# 3. Verify
terraform plan  # Should show no changes
```

**Auto-import script:**
```bash
#!/bin/bash
# import-resources.sh

# Import VPC
VPC_ID=$(aws ec2 describe-vpcs --filters "Name=tag:Name,Values=myapp-vpc" --query "Vpcs[0].VpcId" --output text)
terraform import aws_vpc.main $VPC_ID

# Import subnets
aws ec2 describe-subnets --filters "Name=vpc-id,Values=$VPC_ID" --query "Subnets[*].SubnetId" --output text | \
while read SUBNET_ID; do
  terraform import "aws_subnet.public[\"$SUBNET_ID\"]" $SUBNET_ID
done
```

### Infrastructure Recovery

#### Full Region Disaster

**Multi-region setup:**
```hcl
# Primary region
module "primary_infrastructure" {
  source = "./modules/infrastructure"
  
  providers = {
    aws = aws.primary
  }
  
  region = "us-east-2"
}

# Secondary region (hot standby)
module "secondary_infrastructure" {
  source = "./modules/infrastructure"
  
  providers = {
    aws = aws.secondary
  }
  
  region = "us-west-2"
}

# Route 53 failover
resource "aws_route53_record" "app" {
  zone_id = aws_route53_zone.main.zone_id
  name    = "app.example.com"
  type    = "A"
  
  set_identifier  = "primary"
  health_check_id = aws_route53_health_check.primary.id
  
  failover_routing_policy {
    type = "PRIMARY"
  }
  
  alias {
    name                   = module.primary_infrastructure.alb_dns_name
    zone_id                = module.primary_infrastructure.alb_zone_id
    evaluate_target_health = true
  }
}
```

#### Database Recovery

**RDS automated backups:**
```hcl
resource "aws_db_instance" "main" {
  identifier = "myapp-db"
  
  # Automated backups
  backup_retention_period = 30
  backup_window           = "03:00-04:00"
  
  # Point-in-time restore
  enabled_cloudwatch_logs_exports = ["error", "slowquery"]
  
  # Snapshots
  copy_tags_to_snapshot = true
  skip_final_snapshot   = false
  final_snapshot_identifier = "myapp-db-final-snapshot"
}
```

**Recovery:**
```bash
# Restore from automated backup
aws rds restore-db-instance-to-point-in-time \
  --source-db-instance-identifier myapp-db \
  --target-db-instance-identifier myapp-db-restored \
  --restore-time 2024-01-15T10:00:00Z

# Or restore from snapshot
aws rds restore-db-instance-from-db-snapshot \
  --db-instance-identifier myapp-db-restored \
  --db-snapshot-identifier myapp-db-snapshot-2024-01-15
```

### DR Runbook

**runbooks/disaster-recovery.md**
```markdown
# Disaster Recovery Runbook

## RTO: 1 hour
## RPO: 15 minutes

## Scenario 1: State File Corruption

### Detection
- Terraform commands fail
- State file shows errors

### Recovery Steps
1. Access S3 console
2. Go to terraform-state-backup bucket
3. Click on prod/terraform.tfstate
4. Go to "Versions" tab
5. Download version before corruption
6. Run: `terraform state push downloaded-state.tfstate`
7. Verify: `terraform plan`

**Responsible:** DevOps Team
**Contact:** devops@company.com

## Scenario 2: Complete AWS Region Failure

### Detection
- Health checks failing
- Route 53 not resolving

### Recovery Steps
1. Verify secondary region is healthy
2. Route 53 should auto-failover (5 minutes)
3. If manual intervention needed:
   ```bash
   aws route53 change-resource-record-sets \
     --hosted-zone-id Z1234 \
     --change-batch file://failover.json
   ```
4. Notify users (use status page)
5. Monitor secondary region

**Responsible:** SRE Team
**Contact:** sre@company.com

## Scenario 3: Accidental Terraform Destroy

### Detection
- Resources missing in AWS console
- Application down

### Recovery Steps
1. Stop all terraform operations
2. Recover state file (see Scenario 1)
3. Run terraform apply to recreate resources
4. Restore database from latest backup
5. Verify application

**Responsible:** DevOps Team
**Contact:** devops@company.com

## Testing Schedule
- Monthly: State recovery drill
- Quarterly: Full DR drill
- Annually: Region failover test
```

### Testing DR Plan

**Monthly drill:**
```bash
#!/bin/bash
# dr-drill.sh

echo "=== DR Drill Start ==="
echo "Date: $(date)"

# Backup current state
terraform state pull > state-before-drill.tfstate

# Simulate state corruption
terraform state rm aws_instance.test_dr

# Recover
terraform import aws_instance.test_dr i-1234567

# Verify
if terraform plan | grep "No changes"; then
  echo "✅ DR Drill Successful"
else
  echo "❌ DR Drill Failed"
  terraform state push state-before-drill.tfstate
fi

echo "=== DR Drill End ==="
```

### Key Takeaways

📌 **Remember:**
- Enable S3 versioning for state
- Automate state backups
- Document recovery procedures
- Test DR plan regularly
- Multi-region for critical systems
- Keep runbooks updated
- RTO: 1 hour, RPO: 15 minutes

---

## Section 50: CI/CD Integration

### What You'll Learn
- GitHub Actions setup
- GitLab CI/CD
- Jenkins integration
- Automated testing
- Deployment pipelines

### GitHub Actions

**.github/workflows/terraform.yml**
```yaml
name: Terraform CI/CD

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main, develop]
  workflow_dispatch:

env:
  TF_VERSION: 1.6.0
  AWS_REGION: us-east-2

jobs:
  setup:
    runs-on: ubuntu-latest
    outputs:
      environment: ${{ steps.env.outputs.environment }}
    steps:
      - name: Determine Environment
        id: env
        run: |
          if [ "${{ github.ref }}" == "refs/heads/main" ]; then
            echo "environment=prod" >> $GITHUB_OUTPUT
          else
            echo "environment=dev" >> $GITHUB_OUTPUT
          fi

  validate:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v2
        with:
          terraform_version: ${{ env.TF_VERSION }}
      
      - name: Terraform Format Check
        run: terraform fmt -check -recursive
      
      - name: Terraform Init
        run: terraform init -backend=false
      
      - name: Terraform Validate
        run: terraform validate

  security:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      
      - name: Run tfsec
        uses: aquasecurity/tfsec-action@v1.0.0
        with:
          soft_fail: false
      
      - name: Run Checkov
        uses: bridgecrewio/checkov-action@master
        with:
          directory: .
          framework: terraform

  plan:
    needs: [setup, validate, security]
    runs-on: ubuntu-latest
    environment: ${{ needs.setup.outputs.environment }}
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v2
        with:
          terraform_version: ${{ env.TF_VERSION }}
      
      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v2
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ env.AWS_REGION }}
      
      - name: Terraform Init
        run: terraform init
      
      - name: Terraform Plan
        id: plan
        run: |
          terraform plan -no-color -out=tfplan | tee plan.txt
          echo "exitcode=$?" >> $GITHUB_OUTPUT
      
      - name: Upload Plan
        uses: actions/upload-artifact@v3
        with:
          name: tfplan
          path: tfplan
      
      - name: Comment PR
        if: github.event_name == 'pull_request'
        uses: actions/github-script@v6
        with:
          script: |
            const fs = require('fs');
            const plan = fs.readFileSync('plan.txt', 'utf8');
            const output = `#### Terraform Plan 📖
            
            <details><summary>Show Plan</summary>
            
            \`\`\`terraform
            ${plan}
            \`\`\`
            
            </details>
            
            *Pushed by: @${{ github.actor }}, Action: \`${{ github.event_name }}\`*`;
            
            github.rest.issues.createComment({
              issue_number: context.issue.number,
              owner: context.repo.owner,
              repo: context.repo.repo,
              body: output
            });

  apply:
    needs: [setup, plan]
    if: github.ref == 'refs/heads/main' && github.event_name == 'push'
    runs-on: ubuntu-latest
    environment:
      name: production
      url: https://app.example.com
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      
      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v2
        with:
          terraform_version: ${{ env.TF_VERSION }}
      
      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v2
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ env.AWS_REGION }}
      
      - name: Terraform Init
        run: terraform init
      
      - name: Download Plan
        uses: actions/download-artifact@v3
        with:
          name: tfplan
      
      - name: Terraform Apply
        run: terraform apply -auto-approve tfplan
      
      - name: Slack Notification
        if: always()
        uses: rtCamp/action-slack-notify@v2
        env:
          SLACK_WEBHOOK: ${{ secrets.SLACK_WEBHOOK }}
          SLACK_COLOR: ${{ job.status }}
          SLACK_MESSAGE: 'Terraform deployment ${{ job.status }}'
```

### GitLab CI/CD

**.gitlab-ci.yml**
```yaml
variables:
  TF_VERSION: 1.6.0
  TF_ROOT: ${CI_PROJECT_DIR}

stages:
  - validate
  - plan
  - apply

before_script:
  - apt-get update
  - apt-get install -y unzip
  - wget https://releases.hashicorp.com/terraform/${TF_VERSION}/terraform_${TF_VERSION}_linux_amd64.zip
  - unzip terraform_${TF_VERSION}_linux_amd64.zip
  - mv terraform /usr/local/bin/
  - terraform --version

validate:
  stage: validate
  script:
    - terraform fmt -check -recursive
    - terraform init -backend=false
    - terraform validate
  only:
    - merge_requests
    - main

security_scan:
  stage: validate
  image: aquasec/tfsec:latest
  script:
    - tfsec . --no-color
  only:
    - merge_requests
    - main
  allow_failure: true

plan_dev:
  stage: plan
  environment:
    name: development
  script:
    - cd environments/dev
    - terraform init
    - terraform plan -out=tfplan
  artifacts:
    paths:
      - environments/dev/tfplan
  only:
    - merge_requests

plan_prod:
  stage: plan
  environment:
    name: production
  script:
    - cd environments/prod
    - terraform init
    - terraform plan -out=tfplan
  artifacts:
    paths:
      - environments/prod/tfplan
  only:
    - main

apply_dev:
  stage: apply
  environment:
    name: development
  script:
    - cd environments/dev
    - terraform init
    - terraform apply -auto-approve tfplan
  dependencies:
    - plan_dev
  only:
    - merge_requests
  when: manual

apply_prod:
  stage: apply
  environment:
    name: production
  script:
    - cd environments/prod
    - terraform init
    - terraform apply -auto-approve tfplan
  dependencies:
    - plan_prod
  only:
    - main
  when: manual
```

### Key Takeaways

📌 **Remember:**
- Automate validation and security scans
- Require manual approval for production
- Store plans as artifacts
- Comment plans on PRs
- Use environment protection rules
- Notify team of deployments
- Test pipelines regularly

---

## Part 11: Career Development

---

## Section 51: Interview Questions and Answers

### What You'll Learn
- Common interview questions
- Technical concepts to know
- Practical scenarios
- How to prepare

### Beginner Level Questions

**Q1: What is Terraform and why use it?**

**Answer:** Terraform is an Infrastructure as Code (IaC) tool that allows you to define and provision infrastructure using declarative configuration files. Benefits include:
- **Version Control**: Infrastructure changes tracked in git
- **Repeatability**: Deploy same infrastructure multiple times
- **Automation**: Reduce manual errors
- **Multi-cloud**: Works with AWS, Azure, GCP, etc.
- **State Management**: Tracks current infrastructure state

**Q2: Explain Terraform workflow**

**Answer:** The basic workflow is:
1. **Write**: Create `.tf` configuration files
2. **Init**: Run `terraform init` to initialize and download providers
3. **Plan**: Run `terraform plan` to preview changes
4. **Apply**: Run `terraform apply` to create/update resources
5. **Destroy**: Run `terraform destroy` to remove resources

**Q3: What is the difference between Terraform and Ansible?**

**Answer:**
- **Terraform**: Infrastructure provisioning (creates VMs, networks, etc.). Declarative, state-based.
- **Ansible**: Configuration management (installs software, configures servers). Procedural, agentless.
- Often used together: Terraform creates infrastructure, Ansible configures it.

**Q4: What is a Terraform provider?**

**Answer:** A provider is a plugin that enables Terraform to interact with cloud platforms and services. Examples:
- `aws`: Amazon Web Services
- `azurerm`: Microsoft Azure
- `google`: Google Cloud Platform
- `kubernetes`: Kubernetes clusters

Each provider offers resources and data sources for its platform.

**Q5: Explain Terraform state file**

**Answer:** The state file (`terraform.tfstate`) tracks the current state of your infrastructure. It:
- Maps configuration to real-world resources
- Stores metadata and resource attributes
- Enables planning (compares desired vs current state)
- Should be stored remotely (S3) for team collaboration
- Contains sensitive data, should be encrypted

### Intermediate Level Questions

**Q6: What are Terraform modules and why use them?**

**Answer:** Modules are containers for multiple resources used together. Benefits:
- **Reusability**: Write once, use multiple times
- **Organization**: Logical grouping of resources
- **Encapsulation**: Hide complexity
- **Versioning**: Tag and version modules

Example:
```hcl
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "5.0.0"
  
  name = "my-vpc"
  cidr = "10.0.0.0/16"
}
```

**Q7: Difference between count and for_each?**

**Answer:**
- **count**: Creates multiple identical resources using numeric index
  - Index-based: `resource[0]`, `resource[1]`
  - If you remove middle item, Terraform recreates everything after it
  
- **for_each**: Creates resources based on map or set
  - Key-based: `resource["key1"]`, `resource["key2"]`
  - Removing item only destroys that specific resource
  - More stable for dynamic lists

**Q8: What is remote backend and why use it?**

**Answer:** Remote backend stores state file remotely (e.g., S3, Terraform Cloud). Benefits:
- **Collaboration**: Team members share same state
- **State Locking**: Prevents concurrent modifications
- **Security**: Encrypted storage
- **Backup**: Automatic versioning
- **Access Control**: IAM policies

Configuration:
```hcl
terraform {
  backend "s3" {
    bucket         = "my-terraform-state"
    key            = "prod/terraform.tfstate"
    region         = "us-east-2"
    encrypt        = true
    dynamodb_table = "terraform-locks"
  }
}
```

**Q9: How does Terraform handle dependencies?**

**Answer:**
- **Implicit Dependencies**: Automatically detected through resource references
  ```hcl
  subnet_id = aws_subnet.public.id  # Implicit dependency
  ```
  
- **Explicit Dependencies**: Using `depends_on`
  ```hcl
  depends_on = [aws_iam_role_policy.app]
  ```
  
- **Dependency Graph**: Terraform builds a graph and processes resources in correct order

**Q10: What are workspaces?**

**Answer:** Workspaces allow multiple state files for the same configuration. Use cases:
- Multiple environments (dev, staging, prod)
- Feature branches
- Testing changes

```bash
terraform workspace new dev
terraform workspace select prod
terraform workspace list
```

Current workspace accessible via `terraform.workspace`.

### Advanced Level Questions

**Q11: How do you manage secrets in Terraform?**

**Answer:** Best practices:
1. **Never hardcode secrets** in .tf files
2. **Use variables** with `sensitive = true`
3. **Environment variables**: `TF_VAR_db_password`
4. **External secrets management**:
   - AWS Secrets Manager
   - HashiCorp Vault
   - Azure Key Vault
5. **Encrypt state** file (S3 with KMS)
6. **Use .gitignore** for .tfvars files

Example:
```hcl
data "aws_secretsmanager_secret_version" "db_password" {
  secret_id = "prod/db/password"
}

resource "aws_db_instance" "main" {
  password = jsondecode(data.aws_secretsmanager_secret_version.db_password.secret_string)["password"]
}
```

**Q12: How do you handle Terraform state conflicts?**

**Answer:**
1. **State Locking**: Use DynamoDB with S3 backend
2. **Force Unlock**: `terraform force-unlock <lock-id>` (only if lock is stuck)
3. **State Backup**: Always backup before risky operations
4. **Team Coordination**: Communicate before running terraform
5. **CI/CD**: Single source of truth for applies

**Q13: What is Terraform taint and when to use it?**

**Answer:** Tainting marks a resource for recreation on next apply. Deprecated in favor of `-replace`.

Old way:
```bash
terraform taint aws_instance.web
terraform apply
```

New way:
```bash
terraform apply -replace=aws_instance.web
```

Use cases:
- Resource is in bad state
- Configuration drift detected
- Force recreation for testing

**Q14: How do you handle large Terraform states?**

**Answer:**
1. **Split into multiple states**: Separate by component or environment
2. **Use modules**: Organize code logically
3. **Targeted operations**: `terraform apply -target=module.vpc`
4. **Increase parallelism**: `terraform apply -parallelism=20`
5. **Remote state references**: Use `terraform_remote_state` data source
6. **Selective refresh**: `terraform apply -refresh=false`

**Q15: Explain Terraform import**

**Answer:** Import brings existing infrastructure under Terraform management.

Process:
```bash
# 1. Write resource configuration
resource "aws_instance" "web" {
  # configuration...
}

# 2. Import existing resource
terraform import aws_instance.web i-1234567890abcdef0

# 3. Verify
terraform plan  # Should show no changes
```

Limitations:
- Must write configuration manually
- Some resources don't support import
- No bulk import (one at a time)

### Scenario-Based Questions

**Q16: How would you migrate from manual infrastructure to Terraform?**

**Answer:**
1. **Inventory**: Document all existing resources
2. **Prioritize**: Start with non-critical resources
3. **Import**: Use `terraform import` for existing resources
4. **Write Config**: Match existing infrastructure
5. **Validate**: `terraform plan` should show no changes
6. **Test**: In non-production first
7. **Migrate**: Gradually move environments
8. **Document**: Update runbooks and documentation

**Q17: A terraform apply failed midway. How do you handle it?**

**Answer:**
1. **Check error message**: Identify the failing resource
2. **Review state**: `terraform state list`, `terraform state show`
3. **Fix the issue**: Correct configuration or AWS quota
4. **Re-run apply**: Terraform will continue from where it stopped
5. **If state is corrupted**:
   - Restore from backup: `terraform state push backup.tfstate`
   - Or refresh: `terraform apply -refresh-only`

**Q18: How do you implement blue-green deployment with Terraform?**

**Answer:**
```hcl
# Create new (green) environment
module "app_green" {
  source = "./modules/app"
  
  version         = "v2.0"
  target_group_arn = aws_lb_target_group.green.arn
}

# Switch traffic (update ALB listener)
resource "aws_lb_listener_rule" "switch" {
  priority = 100
  
  action {
    type             = "forward"
    target_group_arn = var.use_green ? aws_lb_target_group.green.arn : aws_lb_target_group.blue.arn
  }
}

# After validation, destroy old (blue)
# terraform destroy -target=module.app_blue
```

**Q19: How do you handle provider version upgrades?**

**Answer:**
1. **Review changelog**: Check breaking changes
2. **Update version constraint**:
   ```hcl
   required_providers {
     aws = {
       source  = "hashicorp/aws"
       version = "~> 5.0"  # Was 4.0
     }
   }
   ```
3. **Test in dev**: Upgrade dev environment first
4. **Run terraform init -upgrade**: Update providers
5. **Run terraform plan**: Check for breaking changes
6. **Update code**: Fix any incompatibilities
7. **Gradual rollout**: Dev → Staging → Prod

**Q20: How would you implement disaster recovery for Terraform?**

**Answer:**
1. **State backups**:
   - S3 versioning enabled
   - Automated backups with cron
   - Cross-region replication
2. **Code backup**: Git repository (multiple remotes)
3. **Multi-region infrastructure**: Terraform in multiple regions
4. **Documentation**: Runbooks for recovery procedures
5. **Testing**: Regular DR drills
6. **Monitoring**: Alerts for state file changes

### Key Takeaways

📌 **Remember:**
- Understand core concepts (state, providers, modules)
- Practice explaining concepts simply
- Know real-world scenarios
- Be honest about what you don't know
- Have hands-on project examples ready

---

## Section 52: Building Your Portfolio

### What You'll Learn
- Project ideas for portfolio
- GitHub profile setup
- Documentation best practices
- Showcasing your work

### Portfolio Projects

#### Project 1: Multi-Tier Web Application

**Description:** Complete AWS infrastructure with VPC, ALB, ASG, RDS

**Repository structure:**
```
aws-web-app-terraform/
├── README.md
├── architecture.png
├── modules/
│   ├── networking/
│   ├── compute/
│   └── database/
├── environments/
│   ├── dev/
│   └── prod/
└── .github/
    └── workflows/
        └── terraform.yml
```

**README.md highlights:**
```markdown
# AWS Three-Tier Web Application

![Architecture](architecture.png)

## Features
- ✅ High availability across 3 AZs
- ✅ Auto Scaling based on CPU
- ✅ RDS Multi-AZ with automated backups
- ✅ CloudWatch monitoring and alarms
- ✅ CI/CD with GitHub Actions

## Technologies
- Terraform 1.6+
- AWS (VPC, EC2, ALB, RDS, CloudWatch)
- GitHub Actions

## Quick Start
```bash
cd environments/dev
terraform init
terraform apply
```

## Cost
~$100/month for production setup

## What I Learned
- Designing for high availability
- Auto Scaling strategies
- State management with S3/DynamoDB
- CI/CD pipeline implementation
```

#### Project 2: Kubernetes Cluster (EKS)

**Repository:** `terraform-eks-cluster/`

**Highlights:**
- Complete EKS setup
- Node groups with spot instances
- IRSA (IAM Roles for Service Accounts)
- Cluster autoscaler
- ALB Ingress Controller
- Helm chart deployments

#### Project 3: Multi-Cloud Infrastructure

**Repository:** `multi-cloud-terraform/`

**Highlights:**
- Same application on AWS, Azure, GCP
- Demonstrates provider flexibility
- Terraform modules for abstraction
- Cross-cloud networking
- Cost comparison

#### Project 4: Serverless Application

**Repository:** `serverless-aws-terraform/`

**Highlights:**
- Lambda functions
- API Gateway
- DynamoDB
- S3 for static hosting
- CloudFront CDN
- CI/CD pipeline

#### Project 5: Infrastructure Monitoring

**Repository:** `terraform-monitoring-stack/`

**Highlights:**
- Prometheus + Grafana on ECS
- Custom CloudWatch dashboards
- SNS alerting
- Log aggregation with CloudWatch Logs
- Cost optimization monitoring

### GitHub Profile Optimization

**Profile README.md:**
```markdown
# Hi, I'm [Your Name] 👋

## 🚀 DevOps Engineer | Terraform Specialist

I build scalable, secure cloud infrastructure using Infrastructure as Code.

### 🛠️ Technologies
![Terraform](https://img.shields.io/badge/-Terraform-623CE4?logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/-AWS-232F3E?logo=amazon-aws&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?logo=docker&logoColor=white)

### 📊 GitHub Stats
![Stats](https://github-readme-stats.vercel.app/api?username=yourusername&show_icons=true)

### 🔥 Featured Projects

#### [AWS Three-Tier Application](https://github.com/you/aws-app)
Production-ready infrastructure with HA, auto-scaling, and monitoring
- Terraform, AWS, GitHub Actions
- ⭐ 150 stars

#### [EKS Cluster Setup](https://github.com/you/eks-cluster)
Complete Kubernetes platform on AWS
- Terraform, EKS, Helm
- ⭐ 89 stars

### 📝 Latest Blog Posts
- [Terraform Best Practices I Learned the Hard Way](link)
- [Building a CI/CD Pipeline for Terraform](link)
- [Cost Optimization with Terraform](link)

### 📫 Connect
- LinkedIn: [profile](link)
- Blog: [yoursite.com](link)
- Email: you@example.com
```

### Documentation Best Practices

**Each project should have:**

1. **Clear README** with:
   - Architecture diagram
   - Prerequisites
   - Quick start guide
   - Detailed documentation
   - Cost estimates
   - Screenshots/demos

2. **Code Quality**:
   - Well-formatted code
   - Meaningful variable names
   - Comments for complex logic
   - Pre-commit hooks setup

3. **CI/CD**:
   - GitHub Actions workflow
   - Automated testing
   - Security scanning

4. **Examples**:
   - Working examples directory
   - Different use cases
   - Complete configurations

### Project Presentation

**When showcasing projects:**

1. **Demo Video** (2-3 minutes):
   - Problem statement
   - Solution overview
   - Architecture explanation
   - Live demo
   - Results/impact

2. **Blog Post**:
   - Detailed write-up
   - Challenges faced
   - Solutions implemented
   - Lessons learned

3. **Architecture Diagrams**:
   - Use draw.io, Lucidchart, or Cloudcraft
   - Clear, professional diagrams
   - Include in README

### Key Takeaways

📌 **Remember:**
- Quality over quantity (3-5 excellent projects)
- Include architecture diagrams
- Write clear documentation
- Show real-world applications
- Keep repositories updated
- Add CI/CD pipelines
- Cost estimates appreciated

---

## Section 53: Terraform Certifications

### What You'll Learn
- HashiCorp Certified: Terraform Associate
- Exam format and topics
- Study resources
- Preparation tips

### Terraform Associate Certification

**Overview:**
- **Name**: HashiCorp Certified: Terraform Associate (003)
- **Cost**: $70.50 USD
- **Duration**: 60 minutes
- **Questions**: 57 questions
- **Format**: Multiple choice, multiple answer, true/false
- **Passing Score**: Pass/Fail (no specific score published)
- **Validity**: 2 years
- **Renewal**: Retake exam or achieve higher certification

### Exam Objectives

**1. Understand Infrastructure as Code (IaC) concepts (15%)**
- Benefits of IaC
- IaC vs traditional approaches
- Multi-cloud and provider-agnostic benefits

**2. Understand Terraform purpose (20%)**
- Multi-cloud deployment
- Provider plugins
- Terraform workflow
- Terraform vs other IaC tools

**3. Understand Terraform basics (25%)**
- Terraform files and formats
- Terraform CLI
- Terraform providers
- Provider versioning
- Provider configuration

**4. Use Terraform outside the core workflow (8%)**
- Debug Terraform
- Terraform import
- Terraform state manipulation
- Backend types and configuration

**5. Interact with Terraform modules (12%)**
- Module sources
- Module inputs and outputs
- Module versioning
- Public module registry

**6. Navigate Terraform workflow (10%)**
- terraform init
- terraform validate
- terraform plan
- terraform apply
- terraform destroy

**7. Implement and maintain state (18%)**
- Purpose of state
- State file management
- Remote state backends
- State locking
- State security

**8. Read, generate, and modify configuration (25%)**
- Variables and outputs
- Resource blocks
- Data blocks
- Resource addressing
- Complex types (lists, maps)
- Built-in functions
- Dynamic blocks

**9. Understand Terraform Cloud capabilities (12%)**
- Terraform Cloud features
- Sentinel policies
- Remote execution
- Terraform Cloud workspaces vs OSS workspaces

### Study Plan (4-6 Weeks)

**Week 1-2: Fundamentals**
- Complete official HashiCorp tutorials
- Hands-on practice: Basic resources
- Read Terraform documentation
- Watch HashiCorp videos

**Week 3-4: Advanced Topics**
- Modules deep dive
- State management
- Remote backends
- Workspaces
- Practice projects

**Week 5: Terraform Cloud**
- Set up Terraform Cloud account
- Remote execution
- Sentinel policies
- Team collaboration features

**Week 6: Review & Practice**
- Practice exams
- Review weak areas
- Flashcards for commands
- Mock exam

### Study Resources

**Official Resources:**
1. **HashiCorp Learn**: https://learn.hashicorp.com/terraform
   - Interactive tutorials
   - Exam review guide
   - Sample questions

2. **Terraform Documentation**: https://www.terraform.io/docs
   - Comprehensive reference
   - Provider documentation
   - Best practices

3. **Exam Review**: https://learn.hashicorp.com/tutorials/terraform/associate-review
   - Official study guide
   - Topic breakdown
   - Sample questions

**Practice Exams:**
1. **Udemy**: Bryan Krausen's practice exams
2. **Whizlabs**: Terraform Associate practice tests
3. **KodeKloud**: Hands-on labs and quizzes

**Books:**
1. "Terraform: Up & Running" by Yevgeniy Brikman
2. "Terraform in Action" by Scott Winkler

### Sample Questions

**Q1: Which command is used to show the execution plan?**
- A. terraform show
- B. terraform plan ✅
- C. terraform apply
- D. terraform validate

**Q2: What is the purpose of the terraform.tfstate file?**
- A. Store provider credentials
- B. Track current infrastructure state ✅
- C. Define resource configurations
- D. Store terraform variables

**Q3: Which backend type supports state locking?**
- A. local
- B. s3 with DynamoDB ✅
- C. http
- D. All backends

**Q4: How do you mark a resource for recreation?**
- A. terraform taint (deprecated)
- B. terraform apply -replace ✅
- C. terraform destroy -target
- D. terraform refresh

**Q5: What does count = 0 do?**
- A. Creates 0 resources (disables resource) ✅
- B. Creates 1 resource
- C. Causes an error
- D. Creates infinite resources

### Exam Tips

**During Preparation:**
1. **Hands-on Practice**: Do, don't just read
2. **Official Docs**: Familiarize yourself with structure
3. **Terraform CLI**: Master all commands
4. **Time Management**: 60 mins for 57 questions ≈ 1 min/question
5. **Practice Exams**: Take multiple times

**During Exam:**
1. **Flag Questions**: Mark difficult ones, return later
2. **Eliminate Options**: Rule out wrong answers
3. **Read Carefully**: Watch for "NOT" questions
4. **Time Aware**: Keep track of time
5. **Trust First Instinct**: Don't overthink

**Topics to Focus:**
- State management (18%)
- Configuration syntax (25%)
- Terraform basics (25%)
- Modules (12%)

### After Certification

**Update:**
- LinkedIn profile (add certification badge)
- Resume/CV
- GitHub profile
- Email signature

**Maintain:**
- Stay updated with Terraform releases
- Renew certification after 2 years
- Consider Terraform Advanced certification
- Continue building projects

### Key Takeaways

📌 **Remember:**
- 4-6 weeks of focused study
- Hands-on practice is crucial
- Use official HashiCorp resources
- Take practice exams
- 60 minutes, 57 questions
- Focus on state, configuration, and modules
- Valid for 2 years

---

## Section 54: Advanced Topics and Resources

### What You'll Learn
- Advanced Terraform concepts
- Learning resources
- Community involvement
- Staying updated

### Advanced Topics to Explore

#### 1. Terraform CDK (Cloud Development Kit)

Write Terraform in familiar programming languages:

**TypeScript example:**
```typescript
import { Construct } from 'constructs';
import { App, TerraformStack } from 'cdktf';
import { AwsProvider } from '@cdktf/provider-aws/lib/provider';
import { Instance } from '@cdktf/provider-aws/lib/instance';

class MyStack extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);

    new AwsProvider(this, 'aws', {
      region: 'us-east-2',
    });

    new Instance(this, 'compute', {
      ami: 'ami-12345',
      instanceType: 't2.micro',
      tags: {
        Name: 'my-instance',
      },
    });
  }
}

const app = new App();
new MyStack(app, 'terraform-cdk-example');
app.synth();
```

#### 2. Terragrunt

DRY Terraform configurations:

```hcl
# terragrunt.hcl
include "root" {
  path = find_in_parent_folders()
}

terraform {
  source = "git::git@github.com:foo/modules.git//app?ref=v0.0.3"
}

inputs = {
  instance_type = "t2.micro"
  instance_count = 3
}
```

#### 3. Terraform Testing

**Terratest (Go):**
```go
func TestTerraformAwsExample(t *testing.T) {
    terraformOptions := &terraform.Options{
        TerraformDir: "../examples/basic",
    }
    
    defer terraform.Destroy(t, terraformOptions)
    
    terraform.InitAndApply(t, terraformOptions)
    
    instanceID := terraform.Output(t, terraformOptions, "instance_id")
    assert.NotEmpty(t, instanceID)
}
```

#### 4. Policy as Code (Sentinel)

**Terraform Cloud/Enterprise:**
```python
import "tfplan/v2" as tfplan

# Ensure all EC2 instances are t2.micro or t2.small
allowed_types = ["t2.micro", "t2.small"]

main = rule {
    all tfplan.resource_changes as _, rc {
        rc.type is "aws_instance" and
        rc.change.after.instance_type in allowed_types
    }
}
```

#### 5. Custom Providers

Build your own provider:

```go
package main

import (
    "github.com/hashicorp/terraform-plugin-sdk/v2/plugin"
    "github.com/hashicorp/terraform-plugin-sdk/v2/helper/schema"
)

func Provider() *schema.Provider {
    return &schema.Provider{
        ResourcesMap: map[string]*schema.Resource{
            "custom_resource": resourceCustom(),
        },
    }
}

func main() {
    plugin.Serve(&plugin.ServeOpts{
        ProviderFunc: Provider,
    })
}
```

### Learning Resources

#### Official Resources

**1. HashiCorp Learn**
- https://learn.hashicorp.com/terraform
- Interactive tutorials
- Hands-on labs
- Certification prep

**2. Terraform Documentation**
- https://www.terraform.io/docs
- Complete reference
- Provider docs
- Best practices

**3. HashiCorp Blog**
- https://www.hashicorp.com/blog
- New features
- Use cases
- Product updates

#### Books

**1. "Terraform: Up & Running" (3rd Edition)**
- By Yevgeniy Brikman
- Comprehensive guide
- Production best practices
- Testing strategies

**2. "Terraform in Action"**
- By Scott Winkler
- Manning Publications
- Hands-on projects
- Real-world scenarios

**3. "Getting Started with Terraform"**
- By Kirill Shirinkin
- Quick start guide
- AWS focused
- Practical examples

#### Online Courses

**1. A Cloud Guru / Pluralsight**
- Terraform Deep Dive
- Advanced Terraform
- Multi-cloud with Terraform

**2. Udemy**
- HashiCorp Certified: Terraform Associate
- Terraform on AWS with SRE & IaC DevOps
- Complete Terraform Course

**3. Linux Academy / A Cloud Guru**
- Terraform Certified Associate Prep
- Advanced Terraform
- Infrastructure Automation

**4. KodeKloud**
- Terraform for Beginners
- Hands-on labs
- Practice tests

#### YouTube Channels

1. **HashiCorp**
   - Official tutorials
   - Product demos
   - HashiConf talks

2. **TechWorld with Nana**
   - Terraform tutorials
   - DevOps concepts
   - Project walkthroughs

3. **FreeCodeCamp**
   - Full courses
   - Beginner-friendly
   - Comprehensive

4. **Cloud Guru**
   - Short tutorials
   - Exam tips
   - Best practices

### Community Resources

#### GitHub Repositories

**1. Awesome Terraform**
- https://github.com/shuaibiyy/awesome-terraform
- Curated list of resources
- Modules, tools, tutorials

**2. Terraform Best Practices**
- https://github.com/ozbillwang/terraform-best-practices
- Real-world patterns
- Anti-patterns to avoid

**3. Terraform Examples**
- https://github.com/hashicorp/terraform-guides
- Official examples
- Multiple providers

#### Forums and Communities

**1. HashiCorp Discuss**
- https://discuss.hashicorp.com/c/terraform-core
- Official forum
- Get help from experts
- Share knowledge

**2. Reddit**
- r/Terraform
- Community discussions
- Questions and answers
- News and updates

**3. Stack Overflow**
- Tag: terraform
- Technical Q&A
- Code examples

**4. Discord/Slack**
- DevOps Discord servers
- Cloud communities
- Real-time help

### Blogs to Follow

1. **HashiCorp Blog**
   - Official announcements
   - Feature releases
   - Best practices

2. **Gruntwork Blog**
   - Terraform in production
   - Module library
   - DevOps practices

3. **Terraform Registry Blog**
   - New modules
   - Provider updates
   - Community highlights

4. **Personal Blogs**
   - Anton Babenko (Terraform modules)
   - Yevgeniy Brikman (Author)
   - Alex Brandsen (DevOps)

### Staying Updated

**1. Follow Release Notes**
- https://github.com/hashicorp/terraform/releases
- New features
- Breaking changes
- Bug fixes

**2. Newsletter Subscriptions**
- HashiCorp Newsletter
- DevOps Weekly
- Cloud Native News

**3. Attend Events**
- HashiConf (annual conference)
- Local meetups
- Online webinars
- Virtual summits

**4. Twitter/X**
- Follow @HashiCorp
- Follow @Terraform
- Terraform community members
- Cloud provider accounts

### Contributing to Community

**1. Open Source Contributions**
- Fix bugs in providers
- Contribute to modules
- Improve documentation
- Share your modules

**2. Write Content**
- Blog posts
- Tutorials
- Video tutorials
- Conference talks

**3. Help Others**
- Answer questions on forums
- Review pull requests
- Mentor beginners
- Share experiences

### Key Takeaways

📌 **Remember:**
- Terraform CDK for programming language preference
- Terragrunt for DRY configurations
- Policy as Code with Sentinel
- Join communities for learning
- Follow official blogs and releases
- Contribute back to community
- Never stop learning

---

## Section 55: Your Learning Roadmap and Next Steps

### What You'll Learn
- Complete learning path
- Career progression
- Continuous improvement
- Final recommendations

### Your Learning Journey So Far

**🎉 Congratulations!** You've completed:
- ✅ 55 sections
- ✅ 11 comprehensive parts
- ✅ 5 real-world projects
- ✅ Hundreds of code examples

**What you now know:**
1. Infrastructure as Code fundamentals
2. Terraform core concepts and workflow
3. AWS resource management
4. State management and backends
5. Advanced features (modules, workspaces)
6. Real-world project implementations
7. Best practices and security
8. Operations and CI/CD
9. Career development strategies

### Your Next 90 Days

#### Days 1-30: Consolidation

**Week 1-2: Practice Projects**
```
✅ Project 1: Personal website with S3/CloudFront
✅ Project 2: 3-tier web application
✅ Project 3: EKS cluster deployment
```

**Week 3-4: Contribute to Open Source**
- Find Terraform modules to improve
- Submit documentation fixes
- Create pull requests
- Share your own modules

#### Days 31-60: Advancement

**Advanced Topics:**
- Terraform CDK
- Terragrunt
- Custom providers
- Policy as Code (Sentinel)

**Certification:**
- Study for HashiCorp Terraform Associate
- Take practice exams
- Schedule and pass certification

**Community Involvement:**
- Join Terraform Slack/Discord
- Attend local meetups
- Write blog posts
- Create video tutorials

#### Days 61-90: Specialization

**Choose a focus area:**

**Option 1: Multi-Cloud Architect**
- Master AWS, Azure, GCP providers
- Build cross-cloud infrastructure
- Cloud migration strategies

**Option 2: Kubernetes + Terraform**
- Deep dive into EKS/AKS/GKE
- Helm integration
- GitOps with ArgoCD

**Option 3: Enterprise Terraform**
- Terraform Cloud/Enterprise
- Sentinel policies
- Module libraries
- Team collaboration

**Option 4: DevOps/SRE**
- CI/CD pipelines
- Infrastructure monitoring
- Incident response
- Reliability engineering

### Career Progression Path

**Level 1: Junior DevOps Engineer (0-1 year)**
- ✅ Basic Terraform knowledge
- ✅ Can create simple resources
- ✅ Understands state management
- ✅ Basic AWS services
- **Salary**: $60k-$80k

**Level 2: DevOps Engineer (1-3 years)**
- ✅ Terraform certified
- ✅ Modules and workspaces
- ✅ CI/CD integration
- ✅ Multiple cloud providers
- **Salary**: $80k-$120k

**Level 3: Senior DevOps Engineer (3-5 years)**
- ✅ Advanced Terraform patterns
- ✅ Infrastructure design
- ✅ Security best practices
- ✅ Mentoring junior engineers
- **Salary**: $120k-$160k

**Level 4: Staff/Principal Engineer (5+ years)**
- ✅ Architecture decisions
- ✅ Multiple products/teams
- ✅ Custom tooling development
- ✅ Industry speaker/writer
- **Salary**: $160k-$250k+

**Level 5: Cloud Architect / DevOps Lead**
- ✅ Enterprise strategy
- ✅ Team leadership
- ✅ Budget and planning
- ✅ Stakeholder management
- **Salary**: $180k-$300k+

### Skills to Develop Alongside Terraform

**Core Skills:**
1. **Cloud Platforms**: AWS (primary), Azure, GCP
2. **Containers**: Docker, Kubernetes
3. **CI/CD**: GitHub Actions, GitLab CI, Jenkins
4. **Scripting**: Bash, Python, Go
5. **Version Control**: Git (advanced)
6. **Networking**: VPC, subnets, load balancers
7. **Security**: IAM, encryption, compliance

**DevOps Tools:**
1. **Configuration Management**: Ansible, Chef, Puppet
2. **Monitoring**: Prometheus, Grafana, Datadog
3. **Logging**: ELK Stack, CloudWatch
4. **Service Mesh**: Istio, Consul
5. **Secrets Management**: Vault, AWS Secrets Manager

### Building Your Brand

**1. Online Presence**
- Active GitHub profile (quality projects)
- Technical blog (weekly/bi-weekly posts)
- LinkedIn (share learnings, engage)
- Twitter (follow and interact with community)

**2. Content Creation**
- Write tutorials
- Record screencasts
- Speak at meetups
- Contribute to open source

**3. Networking**
- Attend conferences (HashiConf, AWS re:Invent)
- Join local DevOps meetups
- Participate in online communities
- Build mentor relationships

### Continuous Learning Strategy

**Daily (30 minutes)**
- Read Terraform/AWS release notes
- Follow Terraform hashtag on Twitter
- Answer questions on Stack Overflow

**Weekly (2-3 hours)**
- Complete one tutorial/lab
- Read one technical blog post
- Watch one conference talk
- Work on personal project

**Monthly**
- Finish one course/book chapter
- Write one blog post
- Attend one meetup
- Update portfolio projects

**Quarterly**
- Complete one certification
- Speak at one event
- Launch one significant project
- Review and update resume

### Common Pitfalls to Avoid

**1. Tutorial Hell**
❌ Endlessly watching tutorials
✅ Build projects, learn by doing

**2. Perfectionism**
❌ Waiting for "perfect" project
✅ Ship early, iterate often

**3. Isolation**
❌ Learning alone
✅ Join communities, find mentors

**4. Stagnation**
❌ Only using basic features
✅ Constantly challenge yourself

**5. Ignoring Fundamentals**
❌ Jumping to advanced topics
✅ Master basics first

### Your Action Plan Template

**This Week:**
```
[ ] Deploy one Terraform project to AWS
[ ] Write README for the project
[ ] Share on LinkedIn/Twitter
[ ] Join Terraform Slack/Discord
```

**This Month:**
```
[ ] Complete 3 projects from this tutorial
[ ] Start Terraform certification study
[ ] Write first blog post
[ ] Contribute to 1 open source project
```

**This Quarter:**
```
[ ] Pass Terraform Associate certification
[ ] Build portfolio website
[ ] Speak at local meetup
[ ] Network with 10 professionals
```

**This Year:**
```
[ ] Land DevOps Engineer role or promotion
[ ] Publish 12 blog posts
[ ] Complete 10 portfolio projects
[ ] Achieve 2 certifications
```

### Resources Checklist

**Essential Tools Installed:**
- [ ] Terraform (latest version)
- [ ] AWS CLI
- [ ] VS Code with Terraform extension
- [ ] Git
- [ ] Docker

**Accounts Created:**
- [ ] AWS (with IAM user)
- [ ] GitHub
- [ ] Terraform Cloud
- [ ] HashiCorp Learn

**Bookmarks Saved:**
- [ ] Terraform Documentation
- [ ] AWS Documentation
- [ ] HashiCorp Learn
- [ ] Terraform Registry

### Final Words

**You've learned Terraform!** But this is just the beginning. Technology evolves rapidly, and the best DevOps engineers are lifelong learners.

**Remember:**
1. **Practice consistently** - Daily coding beats weekend marathons
2. **Build in public** - Share your learning journey
3. **Help others** - Teaching reinforces your knowledge
4. **Stay curious** - Always ask "why" and "how"
5. **Be patient** - Expertise takes time

**Your Terraform journey:**
```
Today: Beginner → [You are here]
3 months: Practitioner
6 months: Proficient
1 year: Expert
2+ years: Master
```

**The DevOps community is welcoming and supportive. You belong here!**

### Connect and Share

**Share your progress:**
- Tag your projects: #Terraform #IaC #DevOps
- Share your certification: #TerraformCertified
- Write about your journey: #100DaysOfIaC

**Need help?**
- HashiCorp Discuss: discuss.hashicorp.com
- r/Terraform: reddit.com/r/terraform
- Stack Overflow: [terraform] tag

**Found this tutorial helpful?**
- ⭐ Star the repository
- 📣 Share with others
- 💬 Provide feedback
- 🤝 Contribute improvements

### Key Takeaways

📌 **Remember:**
- You've completed a comprehensive Terraform education
- Practice through projects
- Get certified
- Join the community
- Keep learning
- Help others
- Build your career
- Stay consistent

---

## 🎊 CONGRATULATIONS! 🎊

**You've completed the entire Terraform tutorial - all 55 sections!**

You now have the knowledge and skills to:
- ✅ Build production infrastructure with Terraform
- ✅ Implement best practices and security
- ✅ Work on real-world projects
- ✅ Pass the Terraform Associate certification
- ✅ Advance your DevOps career

**Your Terraform Journey: COMPLETE! 🚀**

---

## What's Next?

1. **Build Projects**: Apply what you learned
2. **Get Certified**: HashiCorp Terraform Associate
3. **Join Community**: Share and learn from others
4. **Keep Practicing**: Consistency is key
5. **Teach Others**: Reinforce your knowledge

---

**Thank you for completing this tutorial! Now go build amazing infrastructure! 💪**

---

*Tutorial Complete: 55/55 Sections ✅*
*11 Parts ✅*
*5 Real-World Projects ✅*
*You're ready for Terraform mastery! 🎯*

---

## Appendix: Quick Reference

### Essential Commands
```bash
# Initialization
terraform init
terraform init -upgrade

# Planning
terraform plan
terraform plan -out=tfplan

# Applying
terraform apply
terraform apply tfplan
terraform apply -auto-approve

# Destroying
terraform destroy
terraform destroy -auto-approve

# State
terraform state list
terraform state show <resource>
terraform state mv <source> <destination>
terraform state rm <resource>

# Workspace
terraform workspace list
terraform workspace new <name>
terraform workspace select <name>

# Validation
terraform fmt -recursive
terraform validate

# Output
terraform output
terraform output <name>
terraform output -json
```

### Common Terraform Blocks
```hcl
# Provider
provider "aws" {
  region = "us-east-2"
}

# Variable
variable "name" {
  type    = string
  default = "value"
}

# Resource
resource "aws_instance" "web" {
  ami           = "ami-12345"
  instance_type = "t2.micro"
}

# Data Source
data "aws_ami" "latest" {
  most_recent = true
  owners      = ["amazon"]
}

# Output
output "instance_ip" {
  value = aws_instance.web.public_ip
}

# Module
module "vpc" {
  source = "./modules/vpc"
  name   = "my-vpc"
}

# Locals
locals {
  common_tags = {
    Project = "MyApp"
  }
}
```

### Helpful Resources
- **Documentation**: https://www.terraform.io/docs
- **Registry**: https://registry.terraform.io
- **Learn**: https://learn.hashicorp.com/terraform
- **Community**: https://discuss.hashicorp.com

---

**END OF TUTORIAL** 🎉
