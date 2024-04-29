# Kubernetes Run, Create, Apply'

- Kubernetes is evolving and so the CLI
- We get three ways to create pods from the kubectl CLI
- kubectl run ( single pod per command since 1.18 )
- kubectl create ( create some resources via CLI or YAML )
- kubectl apply ( create / update anything via YAML )

# CODE
```bash
microk8s.kubectl run my-nginx --image nginx
microk8s.kubectl describe pod my-nginx
microk8s.kubectl get pods
microk8s.kubectl get all

```