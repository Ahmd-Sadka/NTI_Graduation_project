# NTI DevOps Final Project

This project demonstrates an end-to-end DevOps workflow that incorporates Terraform, Ansible, Docker, Kubernetes, and Jenkins to automate infrastructure provisioning, application deployment, and CI/CD pipelines on AWS.

---

## 1. Terraform
### Features:
- **EKS Cluster**:
  - Create an EKS cluster with two nodes managed by an Auto Scaling Group and an Elastic Load Balancer (ELB).
- **RDS Instance**:
  - Create an RDS instance and securely store the username and password in AWS Secrets Manager.
- **EC2 Instance for Jenkins**:
  - Provision an EC2 instance to host Jenkins.
  - Enable daily snapshots of the Jenkins instance using AWS Backup Service.
- **ELB Access Logs**:
  - Configure the ELB to save access logs to an AWS S3 bucket.
- **AWS ECR**:
  - Set up an AWS Elastic Container Registry (ECR) to store Docker images.

---

## 2. Ansible
### Features:
- **Jenkins Installation**:
  - Automate Jenkins installation, including initial configuration and plugin installations.
- **CloudWatch Agent**:
  - Install and configure the AWS CloudWatch agent on all EC2 instances in the project.

---

## 3. Docker
### Features:
- **Docker Images**:
  - Build Docker images for the application code.
- **Docker Compose**:
  - Create a `docker-compose.yml` file to run the application locally in a complete environment.

---

## 4. Kubernetes
### Features:
- **Kubernetes Manifests**:
  - Create YAML manifests for deploying the application to the AWS EKS cluster.
- **Network Policies**:
  - Implement network policies to enforce security best practices between pods.

---

## 5. Jenkins
### Features:
- **Multi-Branch Pipeline**:
  - Configure Jenkins to trigger builds on every push to any branch in the GitHub repository.
- **Pipeline Stages**:
  1. Build the Dockerfile in the repository.
  2. Push the resulting image to AWS ECR.
  3. Deploy the new image to Kubernetes pods.

---

## Prerequisites
### Tools and Technologies:
- **Infrastructure**: Terraform, Ansible, AWS (EKS, RDS, EC2, ELB, S3, Secrets Manager, Backup, CloudWatch, ECR)
- **Containers**: Docker, Docker Compose
- **Orchestration**: Kubernetes
- **CI/CD**: Jenkins
- **Version Control**: Git, GitHub

---

## Getting Started
### Step 1: Set Up the Environment
- Ensure you have the necessary permissions and access to your AWS account.
- Install required tools:
  - Terraform
  - Ansible
  - Docker and Docker Compose
  - kubectl
  - AWS CLI

### Step 2: Run Terraform
1. Navigate to the Terraform directory.
2. Initialize Terraform:
   ```bash
   terraform init
Apply the configuration:
bash
Copy code
terraform apply
Step 3: Configure Instances with Ansible
Navigate to the Ansible directory.
Run the Ansible playbook:
bash
Copy code
ansible-playbook playbook.yml
Step 4: Build and Run Docker Containers Locally
Navigate to the application directory.
Build Docker images:
bash
Copy code
docker build -t <image-name> .
Start the application with Docker Compose:
bash
Copy code
docker-compose up
Step 5: Deploy to Kubernetes
Apply Kubernetes manifests:
bash
Copy code
kubectl apply -f manifests/
Step 6: Configure Jenkins
Access the Jenkins web interface.
Set up a multi-branch pipeline for the GitHub repository.
Verify pipeline execution on push events.
Project Directory Structure
bash
Copy code
.
├── terraform/          # Terraform configurations
├── ansible/            # Ansible playbooks and roles
├── docker/             # Dockerfiles and docker-compose.yml
├── kubernetes/         # Kubernetes manifests
├── jenkins/            # Jenkins pipeline configuration
└── README.md           # Project documentation