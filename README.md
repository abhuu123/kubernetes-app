🚀 Kubernetes Microservices Deployment Project
📋 Overview

This project demonstrates end-to-end deployment of a full-stack microservices application on Kubernetes.
It includes:

🌐 Frontend – User interface

⚙️ Backend – Business logic & API layer

🗄️ PostgreSQL Database – Persistent relational storage

All resources are defined as code using Kubernetes YAML manifests, ensuring reproducibility and scalability.

🏗️ Architecture Overview

Key Components:

🖥️ Frontend – Serves UI to users

⚙️ Backend – Handles API requests & logic

🗄️ PostgreSQL – Stores data with persistence

🔗 Kubernetes Services – Enable secure communication between components

🛠️ Tech Stack

Kubernetes → Container orchestration

PostgreSQL → Relational database

Docker → Containerization

YAML → Infrastructure as Code

📁 Project Structure
kubernetes-manifests/
├── frontend-deployment.yaml     # Frontend Pods
├── frontend-service.yaml        # Frontend exposure
├── backend-deployment.yaml      # Backend Pods
├── backend-service.yaml         # Backend exposure
├── postgres-deployment.yaml     # Database Pod
├── postgres-service.yaml        # Database exposure
├── postgres-pvc-hostpath.yaml   # Persistent Volume Claim
└── README.md

🚀 Quick Deployment
✅ Prerequisites

Kubernetes cluster (Minikube, Docker Desktop, or Cloud)

kubectl CLI installed

⚡ Deploy Everything in One Go
kubectl apply -f .

🪜 Deploy Step by Step
kubectl apply -f postgres-pvc-hostpath.yaml
kubectl apply -f postgres-deployment.yaml
kubectl apply -f postgres-service.yaml
kubectl apply -f backend-deployment.yaml
kubectl apply -f backend-service.yaml
kubectl apply -f frontend-deployment.yaml
kubectl apply -f frontend-service.yaml

🔍 Verify Deployment
# Check pods
kubectl get pods

# Check services
kubectl get services

# Check storage
kubectl get pvc

🌐 Access Your Application
🖥️ Local Development (Minikube / Docker Desktop)
kubectl port-forward service/frontend-service 3000:80


➡️ Open in browser: http://localhost:3000

☁️ Production (Cloud Cluster)

Use LoadBalancer / NodePort service type

Access via External IP or NodePort

💡 Key Features

✔️ Microservices architecture
✔️ Persistent database storage
✔️ Service discovery & networking
✔️ Infrastructure as Code (IaC)
✔️ Kubernetes orchestration best practices

⚠️ Important Notes

🚫 hostPath volumes are for development only (not production-ready).

🔑 Use Kubernetes Secrets for database credentials.

🌍 Use Ingress for production-grade routing & traffic management.

✨ With this project, you’ll learn how to:

Deploy microservices on Kubernetes

Manage persistent storage

Expose services securely

Scale applications seamlessly
