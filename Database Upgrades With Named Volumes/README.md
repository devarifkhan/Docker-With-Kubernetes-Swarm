# Database Upgrades With Named Volumes

- Database upgrade with containers
- Create postgres container with named volume psql-data using version 9.6.1
- Use Docker Hub to learn VOLUME path and versions needed to run it
- Check logs, stop container
- Create new postgres container with named volume psql-data using version 9.6.2
- Check logs to validate

# CODE
```bash
docker container run -d --name psql -v psql:/var/lib/postgresql/data postgres:9.6.1
 docker container logs -f psql
```