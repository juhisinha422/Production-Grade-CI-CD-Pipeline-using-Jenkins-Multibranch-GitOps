# 🚀 Production-Grade CI/CD Pipeline with Jenkins Multibranch & GitOps

![CI/CD](https://img.shields.io/badge/CI%2FCD-Jenkins-blue?logo=jenkins)
![Docker](https://img.shields.io/badge/Container-Docker-blue?logo=docker)
![Kubernetes](https://img.shields.io/badge/Kubernetes-AWS%20EKS-blue?logo=kubernetes)
![GitOps](https://img.shields.io/badge/GitOps-ArgoCD-orange?logo=argo)

---

## 📌 Project Overview

In this project 🎥, we build a **production-grade CI/CD pipeline** using:

* **Jenkins Multibranch Pipeline**
* **Docker & DockerHub**
* **GitHub (feature branches & PR workflow)**
* **Argo CD (GitOps)**
* **AWS EKS (Kubernetes)**

This repository demonstrates how **real-world DevOps teams** design, automate, and deploy applications from **code commit to live production** using modern DevOps best practices.

This project demonstrates a production-grade CI/CD pipeline that implements modern DevOps practices using Jenkins Multibranch Pipeline, Docker containerization, Kubernetes orchestration, and GitOps principles with ArgoCD.

The pipeline automates the entire software delivery lifecycle from code commit to production deployment, showcasing how enterprise teams build, test, and deploy applications efficiently and reliably.

---

## 🎯Learning Key Points

✔ How feature branches (`featureA`, `featureB`) are handled in CI/CD

✔ Pull Request (PR) based merge strategy using GitHub UI

✔ Jenkins Multibranch Pipeline auto-detection & execution

✔ Docker image build, tagging, and push to DockerHub

✔ Updating Kubernetes manifests via Git (GitOps model)

✔ Argo CD automated sync & deployment to AWS EKS

✔ Accessing the live application using LoadBalancer service

---

## 🔁 End-to-End Deployment Flow

```text
Developer
   ↓
Feature Branch (featureA / featureB)
   ↓
Pull Request → Merge to main (GitHub UI)
   ↓
Jenkins Multibranch Pipeline (CI)
   ↓
Build Docker Image + Push to DockerHub
   ↓
Update Image Tag in Git (K8s Manifest Repo)
   ↓
Argo CD Sync (GitOps)
   ↓
AWS EKS Deployment
   ↓
LoadBalancer URL → Live Application
```

---

## 🛠️ Tools & Technologies Used

| Tool                                | Purpose                                         |
| ----------------------------------- | ----------------------------------------------- |
| 🐙 **GitHub**                       | Feature branches, Pull Requests, Source Control |
| 🧩 **Jenkins Multibranch Pipeline** | Continuous Integration (CI)                     |
| 🐳 **Docker**                       | Containerization                                |
| 📦 **DockerHub**                    | Image Registry                                  |
| ☸️ **Kubernetes (AWS EKS)**         | Container Orchestration                         |
| 🔄 **Argo CD**                      | GitOps-based Continuous Deployment              |
| 🌐 **LoadBalancer Service**         | External Application Access                     |



<img width="1873" height="906" alt="Image" src="https://github.com/user-attachments/assets/4aad0a82-ed76-4b58-a5cf-b98248c8a889" />

<img width="1900" height="877" alt="image" src="https://github.com/user-attachments/assets/a0d635c2-9045-48fc-b90a-a7996a5e6585" />

<img width="1588" height="506" alt="image" src="https://github.com/user-attachments/assets/594bce7b-c024-4698-88a8-1d720d0a9008" />

<img width="1912" height="897" alt="image" src="https://github.com/user-attachments/assets/12da0934-8b20-4808-985a-3f36a76c0462" />


---

Happy Learning & Automating! 🚀

— **Juhi Sinha**
