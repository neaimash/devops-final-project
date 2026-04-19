1. Kubernetes Cluster Setup:
    1.Set up a Kubernetes cluster using Minikube - minikube start
    check it - kubectl get nodes
    2.kubectl apply -f flask-pod.yml
2. Basic Kubernetes Resources:
   1.kubectl apply -f flask-deployment.yml
     check it - kubectl get deployments
   2.kubectl apply -f flask-service.yml
     check it - kubectl get services
                minikube service flask-service
   3.kubectl apply -f flask-HorizontalPodAutoscaler.yml    
3. Advanced Kubernetes Concepts:   
   1.I added envFrom in deployment 
   2.kubectl apply -f flask-cronJob.yml
     check it - kubectl get cronjobs
                kubectl get jobs
   3.added to the deployment             