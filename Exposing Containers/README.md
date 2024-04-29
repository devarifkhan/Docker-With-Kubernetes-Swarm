# Exposing Containers

- kubectl expose creates a service for existing pods
- A Service is a stable address for pods(s)
- If we want to connect to pod(s), we need a service
- CoreDNS allows us to resolve services by name

# Basic Services Types
-ClusterIP (default)
-NodePort
-LoadBalancer

```bash
microk8s.kubectl get pods -w 
microk8s.kubectl create deployment httpenv --image=bretfisher/httpenv
microk8s.kubectl scale deployment httpenv --replicas=5
microk8s.kubectl expose deployment httpenv --port 8888
 microk8s.kubectl get service
 curl 10.152.183.71:8888
```