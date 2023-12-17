---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Containerizing microservices ensures isolation.

Having two "Copy" aids with dependencies through layered caching in Docker.

Use official Docker images from companies or technologies like node official image  
  
  
When managing security you basically doing Linux commands  
  
Doing Docker RUN then whatever links command around permissions  
  
And Docker USER



Consider using bind mounts for configuration or ENV files. Example:
```bash
docker run -d --name containerName -v /path/to/env:/path/in/container -e ENV_FILE=/path/in/container/envfile.env imageNameToBaseContainerOn
```

Run `mvn dependency:resolve` to cache dependencies when making no changes which makes it so that you don't need to get dependencies multiple times.

Example MySQL Docker run:
```bash
docker run --name test -p 3306:3306 -e MYSQL_ROOT_PASSWORD=test -e MYSQL_DATABASE=mydatabase -e MYSQL_USER=myuser -e MYSQL_PASSWORD=mypassword -d --env-file /path/to/env/file mysql

```
The "-e" flag sets environment variables.


Volumes in Docker act as mirrors, reflecting the container's contents. They function as enduring databases, ensuring data persistence even if the database itself is brought offline. This approach fosters a singular source of truth. Volumes offer versatility, accommodating log files and diverse data types across distinct storage spaces.















































