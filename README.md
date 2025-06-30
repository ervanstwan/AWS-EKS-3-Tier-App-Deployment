# 🚀 AWS EKS 3-Tier App Deployment

A complete modern infrastructure-as-code project demonstrating how to deploy a containerized Node.js application on AWS EKS with:

- 3-tier VPC (public, private, db subnets)
- Application Load Balancer (ALB)
- Ingress Controller for routing
- Helm for Kubernetes packaging
- Terraform for full infrastructure provisioning

---

## 🛠 Tech Stack

- **Terraform:** Provision VPC, subnets, ALB, EKS cluster, IAM roles
- **Helm:** Deploy Kubernetes workloads (Node.js app & ingress)
- **Node.js:** Sample backend application
- **Docker:** Containerize the Node.js app
- **AWS EKS:** Managed Kubernetes cluster
- **ALB Ingress Controller:** HTTP routing to services
- **GitHub Actions / Jenkins:** (Optional) CI/CD automation pipelines
- **CloudWatch / Prometheus + Grafana:** (Optional) for monitoring

---

## ✨ Features

✅ 3-tier VPC (public, private, isolated)  
✅ Secure ALB with HTTPS termination & forwarding to ingress  
✅ Scalable EKS worker nodes via managed node groups  
✅ Helm chart to deploy app & ingress resources  
✅ Configurable values for quick adjustments  
✅ Ready for CI/CD pipeline integration

---

## 🚀 Getting Started

### Prerequisites
- Terraform >= 1.0
- AWS CLI configured
- kubectl & aws-iam-authenticator
- Helm 3 installed
- Docker (for building the app image)

---

### 🔥 Quick Deploy

1️⃣ Provision Infrastructure

cd terraform
terraform init
terraform apply -auto-approve

2️⃣ Build & Push Docker Image
Update values.yaml or deployment.yaml with your image:

cd app
docker build -t <your-ecr-repo>:latest .
docker push <your-ecr-repo>:latest

3️⃣ Deploy via Helm

cd helm-chart
helm install myapp .

#### 🌐 Access the Application
Find the ALB DNS name output by Terraform, or via:

kubectl get ingress

Then open in your browser.

##### 📂 Project Structure
```
├── app/                  # Node.js app source code
├── docker/               # Dockerfile
├── terraform/            # Infrastructure code
├── helm-chart/           # Helm chart (values, templates)
└── README.md
```

🚀 Credits & License
Built as part of a complete DevOps portfolio project.
