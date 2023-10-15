![[Docker.png]]

Use Docker prune to start from scratch when dealing with a bad image

  
Use Alpine image if you want to build a custom image so you've build off to something clean  
  
  
Avoid using latest because I might not actually be the latest


Do a Docker image command to make sure your images are correct meaning if you pull latest or some other tag it can appear as two individual images for some reason  
  
  
To verify this you can do a darker image LS dash dash digests to compare the digest to see if they're the same especially if you have multiple images showing up  
  
  
One image can have multiple tags associated with that's why you should do this often to verify

## Docker Images:


A Docker image is a lightweight, standalone, executable software package that includes everything needed to run a piece of software, including the code, runtime, libraries, and system tools. Docker images are typically built from a Dockerfile, which is a text file containing instructions to assemble the image. Images are immutable, meaning they cannot be changed once created. Instead, if changes are needed, a new image version is built.  

Images are build time and are read only you can think of a image as a stopped container  
  

Docker base images  are blueprints of a operating system an the overall Image consist of OS file and objects app files and manifest which is a JSON file describing how everything fits together
## Containers:
A container is a runtime instance of a Docker image. Containers provide an isolated environment for running applications, ensuring that the application and its dependencies are consistent across different environments. Containers share the host system's operating system kernel but have their own isolated filesystem, processes, and networking. They are portable and can be easily moved between different environments without changes to the application code.  


A container is an isolated area of an OS with resources usage limits applied

Containers are running instances of images

![[Kernal OS.jpg]]

![[Namespace docker.jpg]]

![[Control Groups 1.jpg]]
## Volumes:
Volumes in Docker are a way to manage persistent data. A volume is a directory or file that exists outside the container's filesystem but can be accessed and used by the container. Volumes are used to store data that needs to persist across container restarts, updates, or removals. They are especially useful for databases, configuration files, and other stateful data.  
  
### Relationships:  
- Docker Images and Containers: Docker images serve as blueprints for creating containers. Containers are instantiated from Docker images. Each container runs an instance of an image, allowing you to run multiple instances of the same application with isolated environments.  
  
- Containers and Volumes: Containers can be configured to use volumes to store and manage persistent data. This decouples the data from the container itself, allowing the data to survive container restarts or updates.  
  
- Docker Images and Volumes: Docker images do not typically interact directly with volumes. Images define the application and its dependencies, while volumes store persistent data. However, images can be designed to include pre-configured data, which can then be used when a container is launched.  
  
In summary, Docker images define what a software application consists of, containers are the running instances of those images that provide isolation, and volumes are used to manage and persist data between containers. These concepts work together to facilitate consistent, portable, and efficient application deployment and management.


