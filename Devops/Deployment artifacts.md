---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
In terms of deployment, the admin code and processes may or may not be bundled within the same versioned artifact (such as a container image or a deployable package) as the main application code. Depending on the level of separation required and the deployment strategy, you might choose to package admin code separately or include it in the same artifact.




Deployment artifacts refer to the packaged and versioned components of your application that are ready to be deployed to a target environment. These artifacts encapsulate all the necessary code, configurations, dependencies, and other resources required to run your application. Deployment artifacts are typically created during the build process and are used to ensure consistent and reproducible deployments.

Here are some common types of deployment artifacts:

1. **Binary Executables**: For applications written in compiled languages like C++, Rust, or Go, the deployment artifact could be the compiled binary executable of the application.

2. **JAR/WAR/EAR Files**: In Java applications, deployment artifacts often take the form of JAR (Java Archive), WAR (Web Application Archive), or EAR (Enterprise Archive) files that contain the compiled bytecode, resources, and configuration files.

3. **Docker Images**: Docker containers provide a way to package an application and its dependencies together. A Docker image is a deployment artifact that includes the application, its runtime, libraries, and other necessary components.

4. **Package Managers**: For languages like Python, Node.js, or Ruby, deployment artifacts could be packages or modules managed by language-specific package managers like pip, npm, or gem.

5. **Compressed Archives**: Deployment artifacts could be compressed archives (e.g., ZIP, TAR) containing the application code, configuration files, and any required assets.

6. **Virtual Machine Images**: In some cases, deployment artifacts might include virtual machine images (e.g., VMDK, VHD) that encapsulate the entire environment necessary to run the application.

7. **Cloud-Specific Formats**: Cloud platforms often have specific formats for deployment artifacts, such as AWS Lambda deployment packages, Google Cloud Function ZIP files, or Azure Functions deployment packages.

8. **Compiled Assets**: For web applications, deployment artifacts could include compiled assets like CSS files, JavaScript bundles, and static HTML files.

Deployment artifacts play a crucial role in ensuring consistent and reliable deployments across different environments, such as development, testing, staging, and production. By using versioned and packaged artifacts, you can avoid issues caused by differences in dependencies or configurations between environments. Automated deployment pipelines can take these artifacts and deploy them to the appropriate environment using continuous integration and continuous deployment (CI/CD) practices.