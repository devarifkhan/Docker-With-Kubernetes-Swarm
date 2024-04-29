# Persistent Data Bind Mounting

- Maps a host file or directory to a container file or directory
- Basically just two locations pointing to the same file(s)
- Again, skips UFS, and host files overwrite any in container
- Can't use in Dockerfile, must be at container run
- `run -v /path/in/host:/path/in/container`

# CODE
```bash
docker container run -d --name nginx -p 80:80 -v "$(pwd)":/usr/share/nginx/html nginx
docker container run -d --name nginx2 -p 8080:80 nginx
docker container exec -it nginx bash
cd /usr/share/nginx/html
ls -al
```

