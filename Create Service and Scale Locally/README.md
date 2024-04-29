# Create Service and Scale Locally


# CODE

```bash
docker info | grep -i "swarm"
docker swarm init
# Lots of PKI and security Automation
# Root Signing Certificate created for our Swarm
#Certificte is issued for first Manager node
# join tokens are created

# Raft database created to store root CA, Configs and secrets
# Encrypted by default on disk ( 1.13+ )
# No need for another key/value system to hold orchestration/secrets
# Replicates logs amongst Managers via manual TLS in "control plane"
docker node ls
docker service create alpine ping 8.8.8.8
docker service ls
docker service ps <service-name>
docker service update <service-id> --replicas 3
docker container rm -f adoring_black.1.i2evwx9a3hb70sib96k2mn0fo
```