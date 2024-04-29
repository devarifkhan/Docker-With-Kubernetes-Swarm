# NodePort and LoadBalancer

- Let's export a node port, so we can access it via the host ip
- These three service types are additive, each one creates the ones above it:
- ClusterIP
- NodePort
- LoadBalancer

```bash
microk8s.kubectl expose deployment httpenv --port 8888 --name httpenv-np --type NodePort
microk8s.kubectl get service
curl localhost:31370
microk8s.kubectl expose deployment httpenv --port 8888 --name httpenv-lb --type LoadBalancer
service/httpenv-lb exposed
microk8s.kubectl delete service/httpenv service/httpenv-np
microk8s.kubectl delete service/httpenv-lb deployment/httpenv

# DNS
microk8s.kubectl get namespaces 
```