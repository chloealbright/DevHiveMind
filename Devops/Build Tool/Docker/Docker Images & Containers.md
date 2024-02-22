---
tags:
  - Docker
author:
  - jacgit18
Comments: This documentation discusses uses cases of Docker images.
Status: Done
Started: 2024-02-22
EditDate: 
Relates:
---
![[Docker.png]]

A Docker image stands as a compact, self-sufficient, executable software entity encapsulating everything necessary for software execution — code, runtime, libraries, and system tools. Typically constructed from a Dockerfile, a text file with assembly instructions, these images are immutable, signifying that alterations prompt the creation of a new version rather than modifying the existing one.

Images are constructed at build time and remain read-only, akin to a stopped container in conceptualization.

Docker base images serve as blueprints for an operating system, forming the foundation of the overall image. This composite structure encompasses OS files, application files, and a manifest, represented by a JSON file detailing the interconnection of all elements.

## Container
![[Kernal OS.jpg]]
A container is a dynamic runtime manifestation of a Docker image. It furnishes an isolated environment for executing applications, guaranteeing consistency of the application and its dependencies across diverse environments. While containers share the host system's operating system kernel, they possess their distinct isolated filesystem, processes, and networking. Portable and adaptable, containers can seamlessly transition between various environments without necessitating alterations to the application code.

In essence, a container defines an isolated segment of an operating system with applied resource usage limits, representing a live instance of an image in execution.