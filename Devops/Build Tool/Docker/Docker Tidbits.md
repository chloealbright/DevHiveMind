---
tags:
  - Docker
author:
  - jacgit18
Comments: This documentation discusses tips to with using docker.
Status: Done
Started: 
EditDate: 2024-02-22
Relates:
---
Containerizing [[microservices]] enhances isolation, employing two "COPY" commands to facilitate dependencies through layered caching in Docker. Utilizing official Docker images from reputable sources, like the node official image, ensures reliability.

For robust security management, Linux commands within Docker RUN, linking commands, and Docker USER effectively handle permissions.

Start afresh using Docker prune to rectify issues with a problematic image.

Opt for the Alpine image when building a custom one to begin with a clean slate.

Avoid using "latest" as it might not genuinely represent the latest version.

Verify your images with a Docker image command to ensure correctness, especially when dealing with multiple tags.

Consider using bind mounts for configuration or ENV files, demonstrated by the example command:
```bash
docker run -d --name containerName -v /path/to/env:/path/in/container -e ENV_FILE=/path/in/container/envfile.env imageNameToBaseContainerOn
```

Efficiently cache dependencies by running `mvn dependency:resolve` when making no changes to eliminate the need for fetching dependencies multiple times.

For a MySQL Docker run example:
```bash
docker run --name test -p 3306:3306 -e MYSQL_ROOT_PASSWORD=test -e MYSQL_DATABASE=mydatabase -e MYSQL_USER=myuser -e MYSQL_PASSWORD=mypassword -d --env-file /path/to/env/file mysql
```
The "-e" flag sets environment variables.

Docker volumes serve as mirrors, reflecting container contents and providing enduring databases for data persistence. They function as a singular source of truth, accommodating log files and diverse data types across distinct storage spaces.