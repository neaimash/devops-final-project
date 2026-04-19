# Flask on Kubernetes (Minikube)

This project demonstrates deploying a Flask application on a local Kubernetes cluster using Minikube, including basic and advanced Kubernetes concepts.

## 1. Kubernetes Cluster Setup

Start Minikube:
```bash
minikube start
```
Check cluster:
```bash
kubectl get nodes
```
Apply Pod:
```bash
kubectl apply -f flask-pod.yml
```
## 2. Basic Kubernetes Resources

### Deployment
```bash
kubectl apply -f flask-deployment.yml
kubectl get deployments
kubectl get pods
```
### Service
```bash
kubectl apply -f flask-service.yml
kubectl get services
minikube service flask-service
```
### Horizontal Pod Autoscaler (HPA)
```bash
kubectl apply -f flask-HorizontalPodAutoscaler.yml
kubectl get hpa
```
---
## 3. Advanced Kubernetes Concepts
### ConfigMap / Environment Variables
Used envFrom in Deployment to load ConfigMap.
```bash
kubectl apply -f flask-config.yaml
```
---
### CronJob
```bash
kubectl apply -f flask-cronjob.yml
kubectl get cronjobs
kubectl get jobs
kubectl get pods
```
---
## Summary
- Minikube cluster setup
- Pods & Deployments
- Services exposure
- Auto-scaling with HPA
- ConfigMaps for configuration
- CronJobs for scheduled tasks
