---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[Docker.gif]]


![[Docker.png]]





## Docker Images:


A Docker image is a lightweight, standalone, executable software package that includes everything needed to run a piece of software, including the code, runtime, libraries, and system tools. Docker images are typically built from a Dockerfile, which is a text file containing instructions to assemble the image. Images are immutable, meaning they cannot be changed once created. Instead, if changes are needed, a new image version is built.  

Images are build time and are read only you can think of a image as a stopped container  
  

Docker base images  are blueprints of a operating system an the overall Image consist of OS file and objects app files and manifest which is a JSON file describing how everything fits together
## Containers:
A container is a runtime instance of a Docker image. Containers provide an isolated environment for running applications, ensuring that the application and its dependencies are consistent across different environments. Containers share the host system's operating system kernel but have their own isolated filesystem, processes, and networking. They are portable and can be easily moved between different environments without changes to the application code.  


A container is an isolated area of an OS with resources usage limits applied

Containers are running instances of images

![[Kernal OS.jpg]]


  
### Relationships:  
- Docker Images and Containers: Docker images serve as blueprints for creating containers. Containers are instantiated from Docker images. Each container runs an instance of an image, allowing you to run multiple instances of the same application with isolated environments.  
  
- Containers and Volumes: Containers can be configured to use volumes to store and manage persistent data. This decouples the data from the container itself, allowing the data to survive container restarts or updates.  
  
- Docker Images and Volumes: Docker images do not typically interact directly with volumes. Images define the application and its dependencies, while volumes store persistent data. However, images can be designed to include pre-configured data, which can then be used when a container is launched.  
  
In summary, Docker images define what a software application consists of, containers are the running instances of those images that provide isolation, and volumes are used to manage and persist data between containers. These concepts work together to facilitate consistent, portable, and efficient application deployment and management.


