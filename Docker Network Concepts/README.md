# Docker Network: Concepts

- Review Of docker container run -p
- Quick port check with docker container port <container>
- Learn concept of docker networking
- Understand how network packet move around docker

# Docker Network Defaults

- Each container connected to a private virtual network "bridge"
- Each virtual network routes through NAT firewall on host IP
- All containers on a virtual network can talk to each other without -p
- Best practice is to create a new virtual network for each app:
  - network "my_web_app" for mysql and php/apache containers
  - network "my_api" for mongo and nodejs containers

# Docker Networks

- "Batteries included, But Removable"
    - Default work well in many cases, but easy to swap out parts to customize it
- Make new virtual networks
- Attach containers to more than one virtual network ( or none )
- Skip virtual networks and use host IP ( --net=host )
- Use different Docker network drivers to gain new abilities


# CODE

```bash
docker container run -p 80:80 --name webhost -d nginx
docker container port webhost
docker container inspect --format "{{.NetworkSettings.IPAddress}}" webhost

# check we are not in the same ip with docker

```