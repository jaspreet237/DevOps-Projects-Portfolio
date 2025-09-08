GitOps with ArgoCD on Minikube – Nginx Demo
🚀 Project Overview

This project demonstrates how to deploy an Nginx application on Kubernetes (Minikube) using GitOps principles with ArgoCD.

The app serves a custom HTML page stored in a Kubernetes ConfigMap. ArgoCD continuously syncs the manifests from the GitHub repository and ensures the cluster state matches the repo state.

🛠️ Tech Stack

Kubernetes (Minikube → future: AKS)

ArgoCD (GitOps tool)

Nginx (web server)

ConfigMap (for custom HTML content)

GitHub (source repo for manifests)

📂 Project Structure

gitops-argocd-demo/

│── manifests/

│   ├── deployment.yaml      # Nginx Deployment

│   ├── service.yaml         # Nginx Service (ClusterIP)

│   └── configmap.yaml       # Custom HTML ConfigMap

│── application.yaml         # ArgoCD Application definition

└── README.md

⚙️ Setup Instructions
1️⃣ Start Minikube
minikube start

2️⃣ Install ArgoCD
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

3️⃣ Port-Forward ArgoCD Server
kubectl port-forward svc/argocd-server -n argocd 8080:443


Access UI → https://localhost:8080

Get initial admin password:

kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d

4️⃣ Create ArgoCD Application
kubectl apply -f application.yaml -n argocd


application.yaml points to this repo → manifests/ folder.

5️⃣ Sync the Application

Go to ArgoCD UI → Select your app (nginx-demo) → Click Sync

ArgoCD will deploy:

nginx-app (Deployment)

nginx-service (Service)

nginx-html (ConfigMap with custom page)

🌐 Access the App

Since the service is ClusterIP, port-forward to access:

kubectl port-forward svc/nginx-service 8084:80


Now open:
👉 http://localhost:8084

You should see:

Hello from GitOps 🚀
This page was deployed via ArgoCD!

🔄 GitOps Workflow

Make changes to manifests in the repo (e.g., configmap.yaml to update HTML).

Push changes to GitHub.

ArgoCD detects changes and syncs them to the cluster.

Nginx serves the updated page.


✅ Current Status (Minikube):

Running with ArgoCD GitOps sync

Access via kubectl port-forward svc/nginx-service 8084:80

Verified ConfigMap changes propagate via GitOps

✅ Future:

No need for port-forward (use LoadBalancer IP)

Production-grade GitOps workflow