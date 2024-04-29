# Scaling ReplicaSets

- start a new deployment for one replica/pod
```bash
kubectl create deployment my-apache --image httpd
kubectl scale deploy/my-apache --replicas 2
microk8s.kubectl logs deployments/my-apache
microk8s.kubectl describe pod my-apache-5bd7979764-t9lcr
microk8s.kubectl get pods -w
```
