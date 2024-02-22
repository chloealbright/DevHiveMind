---
tags:
  - devops
author:
  - jacgit18
  - chatgpt
Comments: This documentation discusses software build.
Status: Done
Started: 
EditDate: 2024-02-22
Relates:
---
In programming, a 'build' refers to a specific version of a software program, identified by a unique build number. It involves compiling source code, linking libraries, packaging assets, and creating executable software. The 'Build' encompasses the entire process of delivering your software, including steps like generating sources, compiling and testing, packaging into formats like JAR or WAR, and performing health checks. Modern practices favor full automation through tools like Maven or Ant, enabling Continuous Integration for seamless development workflows.

#### Application Build Process InDepth
1. **Source Code Generation:** Develop the source code for the software.

2. **Compilation:** Translate the source code into machine-readable code (e.g., bytecode or machine code).

3. **Testing:** Execute various tests, including unit and integration tests, to ensure the code functions as intended.

4. **Library Linking:** Connect necessary libraries and dependencies to the compiled code.

5. **Asset Packaging:** Bundle assets such as images, configuration files, or other resources with the compiled code.

6. **Executable Software Creation:** Combine all components into an executable software version.

7. **Packaging:** Package the software into specific formats like JAR (Java Archive), WAR (Web Application Archive), EJB-JAR (Enterprise JavaBeans Archive), or EAR (Enterprise Archive).

8. **Health Checks:** Run health checks using static analyzers (e.g., Checkstyle, Findbugs, PMD) to ensure code quality.

9. **Report Generation:** Generate reports detailing the results of tests and analysis.

10. **Automation:** Modern best practices advocate for full automation using build tools like Maven or Ant.

11. **Continuous Integration:** Execute the entire build process continuously to integrate changes seamlessly into the software, known as Continuous Integration.

These steps collectively constitute the comprehensive process of building and delivering software.