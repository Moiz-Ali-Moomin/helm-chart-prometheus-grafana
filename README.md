# 📊 Kubernetes Monitoring using Helm – Prometheus & Grafana

## 📌 Overview
This project demonstrates how to **deploy a complete Kubernetes monitoring stack** using **Helm charts** for **Prometheus and Grafana**, with optional automation via **Ansible**.

The setup enables:
- Metrics collection using Prometheus
- Visualization and dashboards using Grafana
- A modular, reusable Helm-based deployment
- Easy customization using Helm values files

This is a **production-style observability setup** commonly used in real-world Kubernetes environments.

---

## 🧠 Problem Statement
Monitoring Kubernetes clusters manually is complex due to:
- Multiple components to configure
- Manual YAML management
- Difficult upgrades and rollbacks

This project solves the problem by:
- Packaging monitoring components as Helm charts
- Providing reusable and configurable deployments
- Automating installation with Helm and Ansible

---

## 🏗️ Architecture & Workflow
Kubernetes Cluster
↓
Helm Charts
↓
Prometheus (Metrics Collection)
↓
Grafana (Metrics Visualization)
↓
Dashboards & Alerts

yaml
Copy code

---

## 🛠️ Tech Stack
- **Container Orchestration:** Kubernetes
- **Package Manager:** Helm
- **Monitoring:** Prometheus
- **Visualization:** Grafana
- **Automation (Optional):** Ansible
- **Configuration:** YAML

---

## ⚙️ Key Features
- Helm-based deployment of Prometheus and Grafana
- Separate charts for Prometheus and Grafana
- Customizable values using `values.yaml`
- Template-driven Kubernetes manifests
- Scripted Helm installation
- Ansible-based automation support

---

## 📂 Project Structure

```text
helm-chart-prometheus-grafana/
├── grafana-chart/
│   ├── templates/
│   ├── .helmignore
│   ├── Chart.yaml
│   └── values.yaml
│
├── prometheus-chart/
│   ├── templates/
│   ├── .helmignore
│   ├── Chart.yaml
│   └── values.yaml
│
├── get_helm.sh           # Script to install Helm
├── helm_env.sh           # Helm environment setup
├── helm-ansible.yaml     # Ansible playbook for Helm deployment
└── README.md

🚀 How to Run the Project

1️⃣ Prerequisites
Kubernetes cluster (local or cloud)

kubectl configured

Linux environment

Internet access to install Helm

2️⃣ Install Helm

bash
Copy code
chmod +x get_helm.sh
./get_helm.sh
Verify Helm:

bash
Copy code
helm version

3️⃣ Setup Helm environment
bash
Copy code
source helm_env.sh

4️⃣ Deploy Prometheus using Helm
bash
Copy code
helm install prometheus ./prometheus-chart

5️⃣ Deploy Grafana using Helm
bash
Copy code
helm install grafana ./grafana-chart

6️⃣ (Optional) Deploy using Ansible
bash
Copy code
ansible-playbook helm-ansible.yaml

📊 Verification

Check running pods:

bash
Copy code
kubectl get pods
Check services:

bash
Copy code
kubectl get svc
Access Grafana using the exposed service or port-forwarding.

🧪 What I Learned

Packaging Kubernetes applications using Helm

Writing reusable Helm charts

Managing configuration with values.yaml

Deploying observability tools on Kubernetes

Automating Helm workflows using Ansible

Structuring production-ready Helm repositories

🔮 Future Enhancements

Add alerting using Alertmanager

Secure Grafana with authentication

Import predefined dashboards automatically

Use persistent storage for metrics

Add Helm upgrades and rollback strategies

Integrate with CI/CD pipelines
