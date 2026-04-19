# Flask on Kubernetes (Minikube)
This project demonstrates deploying a simple Flask application on a local Kubernetes cluster using Minikube.

The application returns:
**Hello, World!**
---
## Prerequisites
Make sure you have installed:
- Docker
- Minikube
- kubectl
---
## 1. Kubernetes Cluster Setup
Start the cluster:
```bash
minikube start
```
Verify the cluster:
```bash
kubectl get nodes
```
---
##  2. Deploy the Application
### Pod (basic test)
```bash
kubectl apply -f flask-pod.yml
```
### Deployment (recommended)
```bash
kubectl apply -f flask-deployment.yml
kubectl get deployments
kubectl get pods
```
---
## 3. Expose the Application
```bash
kubectl apply -f flask-service.yml
kubectl get services
```
Access the app in browser:
```bash
minikube service flask-service
```
---
## 4. Auto Scaling (HPA)
```bash
kubectl apply -f flask-HorizontalPodAutoscaler.yml
kubectl get hpa
```
---
## 5. Configuration (ConfigMap)
The application uses environment variables via ConfigMap:
```bash
kubectl apply -f flask-config.yaml
```
---
## 6. CronJob
Runs scheduled tasks automatically:
```bash
kubectl apply -f flask-cronjob.yml
kubectl get cronjobs
kubectl get jobs
kubectl get pods
```
---
## File Overview
- flask-deployment.yml → runs the application
- flask-service.yml → exposes the app
- flask-HorizontalPodAutoscaler.yml → enables auto scaling
- flask-config.yaml → stores configuration
- flask-cronjob.yml → schedules periodic tasks
---
##  Summary
This project covers:
- Kubernetes cluster setup with Minikube
- Deploying a Flask application
- Exposing services
- Auto-scaling with HPA
- Managing configuration with ConfigMaps
- Automating tasks with CronJobs
