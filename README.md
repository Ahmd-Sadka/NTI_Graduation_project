# NTI DevOps Final Project  

This project demonstrates a complete DevOps workflow for deploying a three-tier Node.js application with MongoDB on AWS EKS. The workflow incorporates Terraform, Ansible, Docker, Kubernetes, and GitHub Actions for automated infrastructure provisioning, application deployment, and CI/CD pipelines.  

---

## 1. Terraform  
### Features:  
- **EKS Cluster**:  
  - Create an AWS EKS cluster with two nodes managed by an Auto Scaling Group and an Elastic Load Balancer (ELB).  
- **MongoDB Deployment**:  
  - Deploy MongoDB as a StatefulSet on the EKS cluster with persistent storage for data reliability.  
- **EC2 Instance for Auxiliary Tools**:  
  - Provision an EC2 instance to host utility tools or monitoring agents.  
- **ELB Access Logs**:  
  - Configure the ELB to save access logs to an AWS S3 bucket.  
- **AWS ECR**:  
  - Set up an AWS Elastic Container Registry (ECR) to store Docker images.  

---

## 2. Ansible  
### Features:  
- **Utility Tool Setup**:  
  - Install required tools and monitoring agents on the EC2 instance.  
- **CloudWatch Agent**:  
  - Automate the installation and configuration of AWS CloudWatch Agent on all EC2 instances.  

---

## 3. Docker  
### Features:  
- **Docker Images**:  
  - Build Docker images for the Node.js application and MongoDB configuration.  
- **Docker Compose**:  
  - Create a `docker-compose.yml` file for local testing and development of the three-tier application.  

---

## 4. Kubernetes  
### Features:  
- **Kubernetes Manifests**:  
  - Create YAML manifests for deploying the Node.js application and MongoDB on the AWS EKS cluster.  
- **MongoDB Deployment**:  
  - Use a StatefulSet to manage MongoDB, ensuring data persistence and fault tolerance.  
- **Network Policies**:  
  - Implement security best practices with network policies to restrict pod communication.  

---

## 5. GitHub Actions  
### Features:  
- **CI/CD Workflow**:  
  - Set up a GitHub Actions pipeline triggered on push events for all branches.  
- **Pipeline Stages**:  
  1. Build the Docker images for the Node.js application and MongoDB.  
  2. Push the built images to AWS ECR.  
  3. Deploy the updated images to Kubernetes pods on AWS EKS.  

---

## Prerequisites  
### Tools and Technologies:  
- **Infrastructure**: Terraform, Ansible, AWS (EKS, EC2, ELB, S3, CloudWatch, ECR)  
- **Containers**: Docker, Docker Compose  
- **Orchestration**: Kubernetes  
- **CI/CD**: GitHub Actions  
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
Step 6: Automate CI/CD with GitHub Actions
Push changes to the GitHub repository to trigger the pipeline.
Verify the pipeline stages and monitor deployments to Kubernetes pods.
Project Directory Structure
graphql
Copy code
.  
├── terraform/          # Terraform configurations  
├── ansible/            # Ansible playbooks and roles  
├── docker/             # Dockerfiles and docker-compose.yml  
├── kubernetes/         # Kubernetes manifests  
├── github-actions/     # GitHub Actions workflows  
└── README.md           # Project documentation  