# Deployment with kubectl

- Let's create a Deployment of the nginx web server!
```bash
microk8s.kubectl create deployment my-nginx --image nginx 
microk8s.kubectl get pods
microk8s.kubectl get all
microk8s.kubectl delete pod my-nginx
microk8s.kubectl delete deployment my-nginx
```