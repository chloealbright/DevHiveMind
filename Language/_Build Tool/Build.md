---
tags:
  - refine
---
In a programming context, a build is a version of a program that, as a rule, is a pre-release version and is identified by a build number rather than by a release number. Simply put, a software build is a set of executable code that is ready for use by customers. 

Build is a compiled version of a program. Compile means, convert (a program) into a machine-code or lower-level form in which the program can be executed. 



Building an application involves compiling the source code and assembling all the necessary components to create an executable version of the software.  

This process often includes tasks such as compiling code, linking libraries, packaging assets, and creating installation packages or container images.  




The "Build" is a process that covers all the steps required to create a "deliverable" of your software. In the Java world, this typically includes: 

	Generating sources (sometimes). 
	
	Compiling sources. 
	
	Compiling test sources. 
	
	Executing tests (unit tests, integration tests, etc). 
	
	Packaging (into jar, war, ejb-jar, ear). 
	
	Running health checks (static analyzers like Checkstyle, Findbugs, PMD, test coverage, etc). 
	
	Generating reports. 

So as you can see, compiling is only a (small) part of the build (and the best practice is to fully automate all the steps with tools like Maven or Ant and to run the build continuously which is known as Continuous Integration).

## Build Tools 

-   What deployment tools 
    -   we went over Jenkins, Terraform, Ansible, GitHub Actions, and Docker in the Simulator but didn’t officially code it. (But you’re interested to learn!)  
        
        -   Jenkins - used to build and test software projects continuously and make it easier for developers to integrate changes to the project 
            
        -   Ansible - configuration management tool that automates provisioning, config management, 
            
        -   Terraform - infrastructure as code tool that helps safely create, change and improve infrastructure 
            
        -   Docker - packages an application and its dependencies into a container that can be run on 
            
        -   AWS 
            
        -   GitHub Actions