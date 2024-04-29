# Scaling Out With Routing Mesh

- Routes ingress ( incoming ) packets for a service to proper task
- Spans all nodes in Swarm
- Uses IPVS from the Linux Kernel
- Load balances swarm services across their tasks
- Two ways this works:
- Container-to-container in a Overlay network ( Uses VIP)
- External traffic incoming to published ports
- This is stateless load balancing
- The LB is OSI Layer 3 ( TCP ) not Layer 4 ( DNS )

# CODE
```bash
docker service create --name search --replicas 3 -p 9200:9200 elasticsearch:2
docker service ls
docker service ps search
curl localhost:9200
```