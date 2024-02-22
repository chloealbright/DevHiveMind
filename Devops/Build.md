---
tags:
  - devops
author:
  - jacgit18
Comments: This documentation discusses software build.
Status: Refinement
Started: 
EditDate: 
Relates:
---
"In the programming realm, a 'build' signifies a specific version of a software program, typically a pre-release iteration identified by a unique build number rather than a formal release number. Essentially, it's a collection of executable code tailored for end-users.

Building an application involves pivotal steps like compiling source code, assembling necessary components, and creating an executable software version. This encompasses compiling code, linking libraries, packaging assets, and producing installation packages or container images.

The 'Build' encapsulates the entire procedure necessary to create a 'deliverable' of your software. In Java, this often involves generating sources, compiling and testing sources, executing various tests (including unit and integration tests), packaging software into formats like JAR, WAR, EJB-JAR, or EAR, running health checks using static analyzers (e.g., Checkstyle, Findbugs, and PMD), and generating reports. Notably, compilation is just one facet of the broader build process, with modern best practices advocating for full automation using tools like Maven or Ant. This process can be executed continuously, known as Continuous Integration.

