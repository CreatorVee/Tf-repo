#  Infrastructure as Code with Terraform – AWS Automation
## EVERYTHING WRITTEN HERE IS AN AUTHENTIC  SIMPLE FORM OF MY NOTEBOOK 
<div style="border-top: 2px solid black; margin: 20px 0;"></div>

##  Project Overview
**Demo Project:**  
Automate AWS Infrastructure provisioning and deployment using Terraform.  

**Technologies Used:**  
🛠 Terraform • ☁️ AWS • 🐳 Docker • 🐧 Linux • 🔗 Git • ☕ Java • 🐘 Maven • 🐋 Docker Hub • ⚙ Jenkins  

<div style="border-top: 2px solid black; margin: 20px 0;"></div>

##  Project Goals
- Provision AWS infrastructure automatically instead of manual configuration.
- Modularize Terraform scripts for reusability.
- Configure AWS S3 for **remote shared Terraform state**.
- Automate Docker container deployment to EC2 instances.
- Integrate Terraform into a **complete CI/CD pipeline**.

<div style="border-top: 2px solid black; margin: 20px 0;"></div>

## 📂 Project Components
1. **AWS Infrastructure Automation**
   - VPC, Subnets, Route Tables, Internet Gateways.
   - EC2 instances with Security Groups.
   - Automated Docker deployment on EC2.
   
2. **Modularized Terraform Setup**
   - Split Terraform resources into reusable modules.
   
3. **EKS Cluster Provisioning**
   - Use Terraform to automate creation of an AWS EKS cluster.

4. **Remote State Configuration**
   - Store Terraform state in AWS S3 for team collaboration and CI/CD integration.

5. **CI/CD Integration**
   - **CI**: Build Java Maven artifact → Build & Push Docker image to Docker Hub.
   - **CD**: Provision EC2 instance via Terraform → Deploy application using Docker Compose.

<div style="border-top: 2px solid black; margin: 20px 0;"></div>

## 🛠 How It Works
1. **Terraform Providers**
   - AWS provider acts as the "translator" between Terraform and AWS.
   - Terraform config file defines **what** to build, AWS provider makes it happen.

2. **Terraform Commands**
   - `terraform plan` → Compares config with real-world AWS state & shows changes.
   - `terraform apply` → Creates/updates AWS resources based on the plan.

3. **Remote State**
   - Stored in S3 bucket for shared access by team members and Jenkins pipelines.

4. **Pipeline Flow**
   ```plaintext
   Jenkins Trigger → Build App → Build Docker Image → Push to Docker Hub
   → Provision EC2 with Terraform → Deploy App via Docker Compose
   
  <div style="border-top: 2px solid black; margin: 20px 0;"></div>

    What I Learned
Terraform Basics: Declarative infrastructure management, reusable variables, .tfvars usage.

AWS Integration: Understanding VPCs, subnets, EC2, security groups.

State Management: Importance of remote state for collaboration.

CI/CD Concepts: Integrating Terraform into build/deploy workflows.

Security Best Practices: Never hardcode secrets, use variables and .tfvars.

--

⚠ Challenges & Issues Faced
Provisioning Stage Stuck: Jenkins could create the EC2 instance, but application deployment step failed.

Configuration Errors: Wrong settings in Terraform prevented correct EKS provisioning.

Cloning Projects: Learned the importance of reading documentation before making changes.

Terraform State Conflicts: Resolved by resetting state files and using remote state.

--

 Next Steps & Improvements
Fix provisioning configuration for EKS deployment stage.

Add Helm integration for Kubernetes deployments.

Improve CI/CD pipeline error handling.

Add automated Terraform testing (using terraform validate & terraform fmt).

---
# Photo evdience 
**Via Jenkins**

<img width="1920" height="945" alt="2025-09-11_10h31_43" src="https://github.com/user-attachments/assets/87bad24f-99b3-40a2-a81b-d7d2eb4bd6be" />

---





