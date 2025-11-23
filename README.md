
# Graduation Project – IVOLVE

This repository contains my DevOps graduation project, demonstrating how to build and automate a complete DevOps workflow around a simple Flask application.  
The main goal is to apply real DevOps practices using modern tools and a clean end-to-end pipeline.

---

## 🚀 Tech Stack

- **Docker** – Containerization  
- **Kubernetes** – Deployment & orchestration  
- **Terraform** – Infrastructure as Code (AWS)  
- **Ansible** – Server configuration  
- **Jenkins** – CI/CD automation  
- **ArgoCD** – GitOps deployment  
- **Flask** – Simple Python web app  

---

## 📂 Project Structure
```bash
Graduation Project - IVOLVE/
│
├── app/ # Flask application (HTML, CSS, Python)
├── docker/ # Dockerfile for building the image
├── k8s/ # Kubernetes manifests
├── terraform/ # AWS IaC using modules + backend
├── ansible/ # Playbooks, roles, and dynamic inventory
├── jenkins/ # Jenkinsfile and shared library
├── argocd/ # ArgoCD application for GitOps deployment
└── READM.md
```

---

## 🐳 Docker

Build and run the container locally:

```bash
docker build -t ahmedbadawi/clouddevops -f docker/Dockerfile .
docker run -p 5000:5000 ahmedbadawi/clouddevops
```
## ☸️ Kubernetes
Apply Kubernetes manifests:

```bash
kubectl apply -f k8s/namespace.yaml
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

## ☁️ Infrastructure (Terraform)
The Terraform code provisions:

* VPC

* Subnets

* Internet Gateway

* EC2 instance for Jenkins

* CloudWatch monitoring

* S3 backend for Terraform state

* Modular design (network + server modules)

Run:

```bash
cd terraform
terraform init
terraform apply
```
## 🔧 Configuration Management (Ansible)
Configure the EC2 instance:

```bash
ansible-playbook -i inventories/aws_ec2.yml site.yml
```
Includes:

. Base system packages

. Jenkins installation

. Environment setup

## 🔄 CI/CD Pipeline (Jenkins)
The pipeline performs:

* Checkout source

* Build Docker image

* Optional image security scan

* Push to DockerHub

* Update Kubernetes manifests

* Commit the new image tag

* ArgoCD syncs the deployment automatically

Pipeline file:

jenkins/Jenkinsfile

## 🚀 GitOps Deployment (ArgoCD)
Apply ArgoCD application:

```bash
kubectl apply -f argocd/argocd-application.yaml
```
ArgoCD watches the repository and automatically deploys any updates.

## 👤 Author
Ahmed Badawi
Graduation Project – IVOLVE

GitHub: @AhmedBadawii
