---
tags:
  - devops
author:
  - jacgit18
  - chatgpt
Comments: This documentation discusses CI/CD.
Status: Done
Started: 
EditDate: 2024-02-22
Relates:
---
### Continuous Integration & Deployment

CI, strictly defined, involves frequently merging developer changes into the main branch, often "several times a day." While CI encompasses steps like linting, building, testing, packaging, and deployment, the industry often focuses on what occurs post-merge.

In practical CI, the process may deviate from strict definitions to foster development speed and creativity. A robust CI system, such as GitHub Actions, automates these steps seamlessly, maintaining the integrity of development workflows.

While deployment isn't inherently part of the CI process, real-world scenarios demand considerations. Testing packages during CI ensures code integrity, even if deployment actions are deferred. The deployment process should ideally remain consistent across different branches, promoting efficiency and reliability.

#### Continuous Delivery & Continuous Deployment  

The terms **Continuous Delivery** and **Continuous Deployment** (CD) describe CI practices that extend to deployments. CD ensures the main branch is deployable continuously, often coupled with automated deployments triggered by merges into the main branch.

The line between CI and CD can blur. For instance, tests ensuring the main branch's deployability can be seen as both CI (frequent merges) and CD (deployability assurance).

The terms **CI** and **CI/CD** are often used interchangeably, acknowledging the interconnected nature of these practices.

#### **Types of CI Setups**

To meet CI/CD requirements, a dedicated server for running tasks minimizes unpredictability risks. Two options exist: hosting a self-owned server or utilizing a cloud service.

1. **Jenkins (Self-hosted):**
   - Pros: Flexibility, control, extensive plugin support.
   - Cons: Complexity in setup, potential for boilerplate code, hardware failure risks.

2. **[[GitHub Actions]] and Cloud-based Solutions:**
   - Pros: Simplified setup, no environment worries, easy configuration.
   - Cons: Limited customization for complex tasks, resource constraints, build time billing.

**Choosing Between Self-hosted and Cloud-based Solutions**

- **Cloud-based Solutions:** Ideal for small to medium projects with standard requirements. Simplicity in configuration, cost-effectiveness, and no need for an elaborate setup make it suitable for smaller projects.

- **Self-hosted CI:** Preferable for larger projects with specific resource needs. More control over resources and suitability for extensive projects and teams make it a choice for larger enterprises.



## Build Then Deploy 

The term Build is a generic term, that describes the overall process which includes compiling. In other words, the Compiler compiles and linker links the object files created by the compiler into e.g. an executable application (or a library). 

A Building can (and usually does) involve several steps, such as pre-processing, compiling, linking, converting data files, running automated tests, packaging, etc. 

Building is done when preparing an application for release 

## Compile: 

	It is a more specific term. 

	It means that through the help of the compiler we convert the high-level language, i.e. source code into an object file. 

	Compiling is part of a build process. 

	Compiling is done at any time the compiler is involved in translating programming language code to machine code. 

An artifact can be an archive file or a directory structure that includes the following structural elements: Compilation output for one or more of your modules. Libraries included in module dependencies. Collections of resources (web pages, images, descriptor files, and so on) 

A developer could do this themselves, but it would be a tedious manual process involving: 

	compiling the code 

	packaging it up 

	publishing the final artifact 

Build tools automate these processes and make building software faster and simpler. 

Due to the requirements of modern applications, Maven and Gradle also do a lot more. Including running the application locally, ensuring tests pass, analyzing the code, and much more. 

### Maven vs. Gradle performance comparison 

Gradle introduced several performance optimizations missing from Maven to improve build performance. 

To see what difference they make, we’ll compare Maven vs. Gradle performance in these scenarios. 

1.  clean, then full build with tests: simulates build on fresh code checkout or CI server 
    
2.  build with tests without clean: simulates rebuild with no changes 
    
3.  small code change, then build with tests: simulates rebuild after developer makes a change 
    

Each scenario was tested across the 2 project types below. An average was taken of 3 results. 

Where the Gradle build task is shown below, the package phase was used in Maven. 