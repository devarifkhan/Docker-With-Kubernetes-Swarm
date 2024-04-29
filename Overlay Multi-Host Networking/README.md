# Overlay Multi Host Networking

- Just choose --driver overlay when creating network
- For container-to-container traffic inside a single swarm
- Optional IPSec ( AES ) encryption on network creation
- Each Service can be connected on multiple networks

# CODE
```bash
docker network create --driver overlay mydrupal
docker network ls
docker service create --name psql --network mydrupal -e POSTGRES_PASSWORD=mypass postgres
docker service ls
docker service ps psql
docker service create --name drupal --network mydrupal -p 80:80 drupal
```