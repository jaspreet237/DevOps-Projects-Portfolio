GitOps Workflow with ArgoCD for Nginx Deployment on Kubernetes

Objective

To implement a GitOps-driven deployment workflow using ArgoCD to manage and continuously synchronize an Nginx application on a Kubernetes cluster.

Tools & Technologies

Minikube → Local Kubernetes cluster

ArgoCD → GitOps continuous delivery tool

GitHub → GitOps manifests repository

Nginx → Demo application deployed on Kubernetes

Kubectl → CLI for K8s cluster management

Architecture

Kubernetes cluster provisioned via Minikube.

GitHub repo stores Kubernetes manifests for the Nginx app.

ArgoCD is installed inside the cluster → configured to watch the repo.

On any manifest changes in GitHub → ArgoCD syncs and redeploys Nginx.

Workflow

Setup Minikube cluster locally.

Install ArgoCD in Kubernetes namespace.

Connect ArgoCD to GitHub repo containing Nginx deployment + service YAMLs.

Commit manifest changes → ArgoCD detects and automatically applies them.

Validate deployment and updates via kubectl and ArgoCD dashboard.

Outcome

Successfully demonstrated GitOps principles for Kubernetes deployments.

Achieved automatic sync, rollout, and rollback of Nginx app.

Showcased end-to-end GitOps workflow with ArgoCD + GitHub + Kubernetes.