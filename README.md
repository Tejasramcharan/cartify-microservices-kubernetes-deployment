<div align="center">

# 🛒 Cartify — Microservices on Kubernetes

### Production-grade e-commerce backend | Microservices | Kubernetes | Observability

[![Node.js](https://img.shields.io/badge/API%20Gateway-Node.js%20%2F%20Express-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Spring Boot](https://img.shields.io/badge/User%20Service-Spring%20Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![FastAPI](https://img.shields.io/badge/Cart%20Service-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)](https://kubernetes.io/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)](https://prometheus.io/)
[![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)](https://grafana.com/)

> **Cartify** is a cloud-native e-commerce backend built on a polyglot microservices architecture, containerised with Docker and orchestrated on Kubernetes. Each service is independently deployable, language-agnostic, and observable via a full Prometheus + Grafana monitoring stack.

</div>

---
## Images:
1) webapp

<img width="1920" height="1080" alt="Screenshot 2026-10-03 221941" src="https://github.com/user-attachments/assets/26eb48f2-cf35-4c14-b3c2-561e6e8f6b8b" />


2)Grafana dashboard for the project

<img width="1920" height="1080" alt="Screenshot 2026-10-03 220547" src="https://github.com/user-attachments/assets/91a4ad3a-df4b-4399-96b2-5ed3c5eb4bba" />


3)Prometheus for the project

<img width="1920" height="1080" alt="Screenshot 2026-10-03 220846" src="https://github.com/user-attachments/assets/98b46c08-7e9b-40f7-9a00-35d06c4ede77" />




## 📐 Architecture

```
                          ┌─────────────────────┐
                          │   Client / Browser   │
                          └──────────┬──────────┘
                                     │ HTTPS
                          ┌──────────▼──────────┐
                          │  Ingress Controller  │
                          │   + Load Balancer    │  ← TLS termination, routing rules
                          └──────────┬──────────┘
                                     │
                    ╔════════════════▼════════════════════╗
                    ║         Kubernetes Cluster           ║
                    ║                                      ║
                    ║   ┌──────────────────────────────┐  ║
                    ║   │       API Gateway             │  ║
                    ║   │    Node.js / Express          │  ║
                    ║   │  Routing · Auth · Rate-limit  │  ║
                    ║   └──────┬────────────┬───────────┘  ║
                    ║          │            │               ║
                    ║  ┌───────▼──┐   ┌────▼──────────┐   ║
                    ║  │  User    │   │  Cart Service  │   ║
                    ║  │ Service  │   │ Python/FastAPI │   ║
                    ║  │  Java /  │   │  Add, remove,  │   ║
                    ║  │  Spring  │   │  view cart     │   ║
                    ║  └──────────┘   └───────────────┘   ║
                    ║                                      ║
                    ║   ┌────────────────────────────────┐ ║
                    ║   │  Prometheus  ──►  Grafana       │ ║
                    ║   │  Metrics scraping & dashboards  │ ║
                    ║   └────────────────────────────────┘ ║
                    ╚══════════════════════════════════════╝
```

---

# 🛒 Cartify — Microservices Kubernetes Deployment

### End-to-End DevOps Project using Docker, AWS EKS, Terraform, Kubernetes, Helm, CI/CD & Monitoring

![AWS](https://img.shields.io/badge/AWS-EKS-orange?style=for-the-badge&logo=amazonaws)
![Kubernetes](https://img.shields.io/badge/Kubernetes-blue?style=for-the-badge&logo=kubernetes)
![Docker](https://img.shields.io/badge/Docker-blue?style=for-the-badge&logo=docker)
![Terraform](https://img.shields.io/badge/Terraform-purple?style=for-the-badge&logo=terraform)
![Helm](https://img.shields.io/badge/Helm-blue?style=for-the-badge&logo=helm)
![Prometheus](https://img.shields.io/badge/Prometheus-orange?style=for-the-badge&logo=prometheus)
![Grafana](https://img.shields.io/badge/Grafana-orange?style=for-the-badge&logo=grafana)

---

## 📌 Project Overview

**Cartify** is a microservices-based e-commerce application containerized with Docker and deployed on **Amazon EKS**.

The project demonstrates a complete DevOps workflow:

```text
Developer
   ↓
GitHub
   ↓
Docker → Docker Hub
   ↓
Terraform
   ↓
AWS EKS
   ↓
Kubernetes + Helm
   ↓
NGINX Ingress
   ↓
Cartify Application
   ↓
Prometheus → Grafana
```

### Application Components

| Component | Technology |
|---|---|
| Frontend | Angular / React |
| API | Node.js |
| Backend | Java |
| Database | MongoDB |
| Database | MySQL |
| Reverse Proxy | NGINX |
| Containers | Docker |
| Orchestration | Kubernetes |
| Cloud | AWS EKS |
| Infrastructure | Terraform |
| Package Management | Helm |
| CI/CD | Jenkins |
| Monitoring | Prometheus + Grafana |

> **Note:** This project uses **Terraform + Amazon EKS**, not Kops.

---



# 📁 Project Structure

```text
cartify-microservices-kubernetes-deployment/
│
├── client/              # Frontend
├── nodeapi/             # Node.js API
├── javaapi/             # Java API
├── nginx/               # NGINX configuration
├── k8s/                 # Kubernetes manifests
├── kkartchart/          # Helm chart
├── terraform/           # AWS EKS infrastructure
├── github-actions/      # CI/CD workflows
├── docker-compose.yml   # Local development
├── Jenkinsfile          # Jenkins pipeline
└── README.md
```

---

# 🛠️ Prerequisites

Install:

- Git
- Docker
- AWS CLI
- Terraform
- kubectl
- Helm

Verify:

```bash
git --version
docker --version
aws --version
terraform version
kubectl version --client
helm version
```

Configure AWS:

```bash
aws configure
```

Verify AWS:

```bash
aws sts get-caller-identity
```

---

# 🚀 1. Clone the Repository

```bash
git clone https://github.com/Tejasramcharan/cartify-microservices-kubernetes-deployment.git

cd cartify-microservices-kubernetes-deployment
```

---

# 🐳 2. Build Docker Images

Each major application component has its own Dockerfile.

```bash
docker build -t YOUR_USERNAME/cartify-client:latest ./client

docker build -t YOUR_USERNAME/cartify-nodeapi:latest ./nodeapi

docker build -t YOUR_USERNAME/cartify-javaapi:latest ./javaapi

docker build -t YOUR_USERNAME/cartify-nginx:latest ./nginx
```

Check:

```bash
docker images
```

---

# 🧪 3. Test Locally with Docker Compose

Start the complete application:

```bash
docker compose up --build
```

Check containers:

```bash
docker ps
```

Stop:

```bash
docker compose down
```

Docker Compose runs the application components together with the required databases.

---

# 📦 4. Push Images to Docker Hub

Login:

```bash
docker login
```

Push:

```bash
docker push YOUR_USERNAME/cartify-client:latest

docker push YOUR_USERNAME/cartify-nodeapi:latest

docker push YOUR_USERNAME/cartify-javaapi:latest

docker push YOUR_USERNAME/cartify-nginx:latest
```

These images will later be pulled by Kubernetes.

---

# ☁️ 5. Create AWS EKS Using Terraform

Go to Terraform:

```bash
cd terraform
```

Initialize:

```bash
terraform init
```

Validate:

```bash
terraform validate
```

Review infrastructure:

```bash
terraform plan
```

Create infrastructure:

```bash
terraform apply
```

Enter:

```text
yes
```

Terraform provisions the required AWS infrastructure including the **EKS cluster and worker nodes**.

---

# ☸️ 6. Connect kubectl to EKS

After Terraform creates the cluster:

```bash
aws eks update-kubeconfig \
  --region us-east-1 \
  --name YOUR_EKS_CLUSTER_NAME
```

Verify:

```bash
kubectl cluster-info
```

Check nodes:

```bash
kubectl get nodes
```

Expected:

```text
NAME              STATUS
ip-xxx-xxx-xxx    Ready
ip-xxx-xxx-xxx    Ready
```

---

# 📋 7. Deploy Application to Kubernetes

Create namespace:

```bash
kubectl create namespace cartify
```

Check Kubernetes files:

```bash
cd ..
ls k8s
```

Apply manifests:

```bash
kubectl apply -f k8s/ -n cartify
```

Check:

```bash
kubectl get pods -n cartify
```

```bash
kubectl get svc -n cartify
```

```bash
kubectl get deployments -n cartify
```

---

# ⛵ 8. Deploy Using Helm

The project also contains a Helm chart:

```text
kkartchart/
├── Chart.yaml
├── values.yaml
└── templates/
```

Validate:

```bash
helm lint ./kkartchart
```

Install:

```bash
helm install cartify ./kkartchart \
  --namespace cartify \
  --create-namespace
```

Check:

```bash
helm list -n cartify
```

```bash
kubectl get all -n cartify
```

For future changes:

```bash
helm upgrade cartify ./kkartchart -n cartify
```

Or:

```bash
helm upgrade --install cartify ./kkartchart -n cartify
```

---

# 🌐 9. NGINX Ingress

Install the NGINX Ingress Controller:

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/aws/deploy.yaml
```

Check:

```bash
kubectl get pods -n ingress-nginx
```

```bash
kubectl get svc -n ingress-nginx
```

Apply the project ingress:

```bash
kubectl apply -f k8s/ingress.yaml
```

Check:

```bash
kubectl get ingress -n cartify
```

Get the external address:

```bash
kubectl get ingress -n cartify
```

Open the provided Load Balancer address in a browser.

---

# 🔍 10. Kubernetes Verification

Useful commands:

```bash
kubectl get nodes

kubectl get pods -n cartify

kubectl get svc -n cartify

kubectl get deployments -n cartify

kubectl get ingress -n cartify

kubectl get all -n cartify
```

### Troubleshooting

Pod details:

```bash
kubectl describe pod POD_NAME -n cartify
```

Pod logs:

```bash
kubectl logs POD_NAME -n cartify
```

Watch pods:

```bash
kubectl get pods -n cartify -w
```

Events:

```bash
kubectl get events -n cartify
```

---

# 📊 11. Prometheus + Grafana Monitoring

The project uses **kube-prometheus-stack** for Kubernetes and application monitoring.

Add Helm repository:

```bash
helm repo add prometheus-community \
https://prometheus-community.github.io/helm-charts
```

Update:

```bash
helm repo update
```

Create monitoring namespace:

```bash
kubectl create namespace monitoring
```

Install:

```bash
helm install prometheus \
prometheus-community/kube-prometheus-stack \
--namespace monitoring
```

Check:

```bash
kubectl get pods -n monitoring
```

You should see components such as:

```text
Prometheus
Grafana
Alertmanager
Node Exporter
Kube State Metrics
Prometheus Operator
```

---

# 📈 12. Access Grafana

Check services:

```bash
kubectl get svc -n monitoring
```

Port-forward:

```bash
kubectl port-forward \
svc/prometheus-grafana 3000:80 \
-n monitoring
```

Open:

```text
http://localhost:3000
```

Get Grafana password:

```bash
kubectl get secret prometheus-grafana \
-n monitoring \
-o jsonpath="{.data.admin-password}" | base64 --decode
```

Login:

```text
Username: admin
Password: <password returned above>
```

---

# 🔥 13. Access Prometheus

Port-forward:

```bash
kubectl port-forward \
svc/prometheus-kube-prometheus-prometheus 9090:9090 \
-n monitoring
```

Open:

```text
http://localhost:9090
```

Example PromQL:

```promql
up
```

```promql
kube_pod_info
```

```promql
rate(node_cpu_seconds_total[5m])
```

Prometheus collects metrics and Grafana visualizes them through dashboards.

---


# 🧹 14. Cleanup

Remove Helm application:

```bash
helm uninstall cartify -n cartify
```

Delete Kubernetes resources:

```bash
kubectl delete -f k8s/ -n cartify
```

Remove monitoring:

```bash
helm uninstall prometheus -n monitoring
```

Delete namespaces:

```bash
kubectl delete namespace cartify
kubectl delete namespace monitoring
```

Finally, destroy AWS infrastructure:

```bash
cd terraform

terraform plan -destroy

terraform destroy
```

⚠️ **Be careful:** `terraform destroy` deletes the AWS infrastructure managed by Terraform.



# 👨‍💻 Author

## Tejas Ramcharan

DevOps / Cloud Enthusiast

**GitHub:**  
https://github.com/Tejasramcharan

**Project:**  
https://github.com/Tejasramcharan/cartify-microservices-kubernetes-deployment

⭐ If you find this project useful, consider giving it a star!

---

