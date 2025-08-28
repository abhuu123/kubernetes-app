📋 Overview
This project demonstrates a complete full-stack application deployment on Kubernetes, featuring frontend, backend, and PostgreSQL database components with persistent storage. All infrastructure is defined as code using Kubernetes manifests.

🏗️ Architecture Overview
<img width="822" height="3120" alt="deepseek_mermaid_20250828_ef2cb4" src="https://github.com/user-attachments/assets/f5226c3d-c2d6-4d4b-85c0-a06a965549a8" />


Backend: Handles business logic and API requests

PostgreSQL: Persistent database storage

Kubernetes Services: Enable communication between components

🛠️ Technology Stack
Kubernetes - Container orchestration

PostgreSQL - Relational database

YAML - Configuration files

Docker - Containerization (implied)

📁 Project Structure
text
kubernetes-manifests/
├── frontend-deployment.yaml    # Frontend application pods
├── frontend-service.yaml       # Frontend network exposure
├── backend-deployment.yaml     # Backend API pods
├── backend-service.yaml        # Backend network exposure
├── postgres-deployment.yaml    # Database pod
├── postgres-service.yaml       # Database network exposure
├── postgres-pvc-hostpath.yaml  # Database storage
└── README.md

🚀 Quick Deployment
Prerequisites
Kubernetes cluster (Minikube, Docker Desktop, or cloud cluster)

kubectl command-line tool

Deployment Steps
bash
# Deploy everything with one command
kubectl apply -f .

# Or deploy step by step
kubectl apply -f postgres-pvc-hostpath.yaml
kubectl apply -f postgres-deployment.yaml
kubectl apply -f postgres-service.yaml
kubectl apply -f backend-deployment.yaml
kubectl apply -f backend-service.yaml
kubectl apply -f frontend-deployment.yaml
kubectl apply -f frontend-service.yaml
🔍 Check Deployment Status
bash
# View all deployed components
kubectl get pods
kubectl get services
kubectl get pvc
🌐 Access Your Application
For Development (Local Cluster):
bash
# Port-forward to access frontend
kubectl port-forward service/frontend-service 3000:80

# Then open: http://localhost:3000
For Production (Cloud Cluster):
Check your service type (NodePort/LoadBalancer)

Use the provided external IP or node port

💡 Key Features Demonstrated
✅ Microservices architecture

✅ Persistent storage for databases

✅ Service discovery and networking

✅ Configuration as code

✅ Container orchestration best practices

⚠️ Important Notes
The hostPath volume is for development only (not production)

Add Kubernetes Secrets for sensitive data like database passwords

Consider using Ingress for production traffic routing
