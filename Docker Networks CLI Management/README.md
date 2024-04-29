# Docker Networks CLI Management

- show networks docker network ls
- inspect a network docker network inspect
- create a network docker network create --driver
- Attach a network to container docker network connect
- Detach a network from container docker network disconnect


# CODE
```bash
docker network ls
docker network inspect bridge
docker network create my_app_neet
docker container run -d --name new_nginx --network my_app_neet nginx
docker network inspect my_app_neet
docker network connect my_app_neet webhost
docker container inspect webhost
docker network disconnect my_app_neet webhost
docker container inspect webhost
```

# Docker Networks Default Security
- New network is not exposed to the outside world
- Containers on the same network can talk to each other
- Best practice is to create a new network for each app
- Create you apps so front end/backend sit on the same network
- you must manually expose via -p, which is better default security
- This gets even better later with Swarm and Overlay networks