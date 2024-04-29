# Container Lifetime & Persistent Data

- Containers are usually immutable and ephemeral
- "immutable infrastructure": only re-deploy containers, never change
- Docker gives us features to ensure these "separation of concerns"
- Two ways: Volumes and Bind Mounts
- Volumes: make special location outside of containers UFS
- VOLUME command in Dockerfile

# CODE
```bash
docker pull mysql
docker image inspect mysql
docker container run -d --name mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=True mysql
docker container ls
docker volume ls
docker volume inspect <volume-name>
docker container run -d --name mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=True -v mysql-db:/var/lib/mysql mysql
docker volume ls
docker volume inspect mysql-db
```