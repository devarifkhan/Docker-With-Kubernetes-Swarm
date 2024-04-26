# Manage Multiple Containers

- docs.docker.com and --help are your friend
- Run a **nginx**, a **mysql**, and a **httpd (apache)** server
- Run all of them `--detach` (or `-d`), name them with `--name`
- **nginx** should listen on `80:80`, **httpd** on `8080:80`, **mysql** on `3306:3306`
- When running **mysql**, use the `--env` option (or `-e`) to pass in `MYSQL_RANDOM_ROOT_PASSWORD=yes`
- Using `docker container logs` on **mysql** to find the random password it created on startup
- Clean it all up with `docker container stop` and `docker container rm` (both can accept multiple names or ID's)
- Use `docker container ls` to ensure everything is correct before and after cleanup

# Solution Manage Multiple Containers
## mysql:
```bash
- docker container run -d -p 3306:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql
- docker container logs db
```


## webserver:
```bash
- docker container run -d --name webserver -p 8080:80 httpd
- docker container logs webserver
```


## nginx:
```bash
- docker container run -d --name proxy -p 80:80 nginx
- docker container logs proxy
```



## stop all container:
```bash
- docker container stop 29b3bafc7305 248d950bf097 df337857be86
```

## remove all container:
```bash
- docker container rm 29b3bafc7305 248d950bf097 df337857be86
```
