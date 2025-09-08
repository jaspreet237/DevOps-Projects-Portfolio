# 🚀 DevOps Projects Portfolio

This repository showcases two key DevOps projects demonstrating **Self-Healing Infrastructure** and **GitOps with ArgoCD**.  
Both projects highlight automation, monitoring, and modern deployment workflows.

---

## 📂 Projects Included

### 1️⃣ Self-Healing Infrastructure
- **Tech Stack:** Terraform, Docker, Prometheus, Alertmanager, Amtool, jq, Grafana  
- **Objective:** Automatically detect Nginx container failures and restart them without manual intervention.  
- **Highlights:**
  - Terraform-based container provisioning  
  - Prometheus & Alertmanager for monitoring  
  - Self-healing scripts with amtool + jq  
- 📄 [Project Report](./self-healing-infra/PROJECT_REPORT.md)  
- 📦 [Source Code](./self-healing-infra/)  

---

### 2️⃣ GitOps with ArgoCD
- **Tech Stack:** Minikube, Kubernetes, ArgoCD, GitHub, Nginx  
- **Objective:** Demonstrate GitOps-driven deployments for Nginx on Kubernetes using ArgoCD.  
- **Highlights:**
  - Kubernetes manifests stored in GitHub repo  
  - ArgoCD continuously syncs manifests → auto-deploys to Minikube  
  - Showcased GitOps principles (sync, rollback, drift detection)  
- 📄 [Project Report](./gitops-argocd-demo/PROJECT_REPORT.md)  
- 📦 [Source Code](./gitops-argocd-demo/)  

---

## 🔗 Additional Links
- **GitHub Profile:** https://github.com/jaspreet237  
- **Docker Hub:** https://hub.docker.com/repositories/jaspreet237
---

## 📜 How to Use
1. Clone this repository:
   ```bash
   git clone https://github.com/jaspreet237/DevOps-Projects-Portfolio.git
