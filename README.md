# 📝 Notes-App: A Kubernetes Deployment Project

This repository contains a simple **"Notes App"** designed as a mini-project to practice and demonstrate fundamental Kubernetes (K8s) deployment concepts.

---

## 📖 Project Overview
This project focuses on containerizing a web application and deploying it to a Kubernetes cluster.  
The key objective is to showcase a complete, end-to-end workflow — from defining Kubernetes resources to exposing the application for access.

---

## ⚡ Prerequisites
To deploy and test this application, you must have the following installed:

- **Kubernetes Cluster**: A running Kubernetes cluster (e.g., Minikube, Docker Desktop with Kubernetes enabled, or a cloud-based cluster).  
- **kubectl**: The command-line tool for interacting with your cluster.  

---

## 📂 File Structure
The core Kubernetes configuration files are located in the `k8s` directory:

- `k8s/namespace.yml` → Defines the **notes-app** namespace to logically isolate the application's resources.  
- `k8s/deployment.yml` → Specifies the **Deployment** for the Notes App, ensuring a desired number of replicas are running.  
- `k8s/service.yml` → Creates a **Service** to expose the application within the cluster.  

---

## 🚀 Deployment Steps

### 1️⃣ Apply all Kubernetes manifests
This command applies the namespace, deployment, and service configurations from the `k8s` directory simultaneously:

```bash
kubectl apply -f k8s/
```
## 🌐 Accessing the Application

After deployment, you can use `kubectl port-forward` to access the application from your local machine.

---

### 1. Port-forward the service:
This command forwards traffic from port **8000** on your local machine to port **8000** of the `notes-app-service` within the `notes-app` namespace.

```bash
kubectl port-forward service/notes-app-service -n notes-app 8000:8000 --address=0.0.0.0
```
### 2. Verify the application:
Open your web browser and navigate to http://localhost:8000.

✅ You should now see the Notes App running.
