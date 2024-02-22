---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Containerizing microservices enhances isolation, with two "COPY" commands aiding dependencies through layered caching in Docker. Leveraging official Docker images from companies or technologies, such as the node official image, ensures reliability.

For security management, Linux commands are employed, particularly within Docker RUN, linking commands, and Docker USER to handle permissions effectively.

Consider using bind mounts for configuration or ENV files. An example command is:
```bash
docker run -d --name containerName -v /path/to/env:/path/in/container -e ENV_FILE=/path/in/container/envfile.env imageNameToBaseContainerOn
```

To cache dependencies efficiently, run `mvn dependency:resolve` when making no changes, eliminating the need to fetch dependencies multiple times.

For a MySQL Docker run example:
```bash
docker run --name test -p 3306:3306 -e MYSQL_ROOT_PASSWORD=test -e MYSQL_DATABASE=mydatabase -e MYSQL_USER=myuser -e MYSQL_PASSWORD=mypassword -d --env-file /path/to/env/file mysql
```
The "-e" flag sets environment variables.

Volumes in Docker act as mirrors, reflecting the container's contents, providing enduring databases for data persistence. They serve as a singular source of truth, accommodating log files and diverse data types across distinct storage spaces.