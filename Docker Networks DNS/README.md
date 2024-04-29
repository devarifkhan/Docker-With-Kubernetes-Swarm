# Docker Networks DNS
- use --link to enable DNS resolution between containers

```bash
docker container inspect webhost
docker container run -d --name my_nginx --network my_app_neet nginx
docker container exec -it my_nginx ping new_nginx
```
