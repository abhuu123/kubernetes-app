🌐 Kubernetes Microservices Deployment
📋 Project Overview

This repository contains Kubernetes manifests for deploying a full-stack microservices application with:

⚙️ Backend Service – Handles API & business logic

🖥️ Frontend Service – User interface

🗄️ PostgreSQL Database – Persistent data storage
<img width="4901" height="210" alt="deepseek_mermaid_20250828_1b411c" src="https://github.com/user-attachments/assets/6b48fde2-e57e-48f1-bbd1-45eeb93f8d61" />


The deployment ensures service discovery, persistent storage, and modular scaling using Kubernetes best practices.

🛠️ Tech Stack

Kubernetes – Orchestration platform

PostgreSQL – Relational database

Docker – Containerization (for app images)

YAML – Infrastructure as Code

📂 Repository Structure
.
├── backend-deployment.yaml     # Backend Pods
├── backend-service.yaml        # Backend Service
├── frontend-deployment.yaml    # Frontend Pods
├── frontend-service.yaml       # Frontend Service
├── postgres-deployment.yaml    # PostgreSQL Pod
├── postgres-service.yaml       # PostgreSQL Service
└── postgres-pvc-hostpath.yaml  # Persistent Volume Claim

🚀 Deployment Guide
✅ Prerequisites

A running Kubernetes cluster (Minikube, Docker Desktop, or cloud provider)

kubectl CLI installed and configured

⚡ Deploy All at Once

Run the following command to deploy everything:

kubectl apply -f .

🪜 Step-by-Step Deployment

Create Persistent Storage for PostgreSQL

kubectl apply -f postgres-pvc-hostpath.yaml


Deploy PostgreSQL Database

kubectl apply -f postgres-deployment.yaml
kubectl apply -f postgres-service.yaml


Deploy Backend Service

kubectl apply -f backend-deployment.yaml
kubectl apply -f backend-service.yaml


Deploy Frontend Service

kubectl apply -f frontend-deployment.yaml
kubectl apply -f frontend-service.yaml

🔍 Verify Deployment

Check running pods, services, and storage:

kubectl get pods
kubectl get services
kubectl get pvc

🌐 Access the Application
Local Cluster (Minikube / Docker Desktop)

Port-forward the frontend service:

kubectl port-forward service/frontend-service 3000:80


➡️ Access via http://localhost:3000

Cloud Cluster

If NodePort/LoadBalancer is configured → Use external IP or NodePort

Recommended: Use Ingress for production

⚠️ Notes & Best Practices

hostPath volumes are not production-ready (use Persistent Volume from cloud providers in production).

Store database credentials in Kubernetes Secrets, not in plain manifests.

Configure Ingress for production traffic management.

✅ This setup provides a scalable, resilient, and modular microservices architecture on Kubernetes.
