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



Gradle employs a domain-specific language (DSL) rather than XML, a departure from Maven's XML-centric approach. There are tools available to convert Gradle to Maven and vice versa, translating between Gradle build files and Maven's pom XML.

**Gradle Overview:**
- Created in 2008 to address Maven's limitations.
- Utilizes a Groovy-based DSL for build scripts, enhancing readability and conciseness.
- Offers a customizable build model directly from the script, allowing dynamic addition of custom build logic.

**Gradle's Build Lifecycle:**
- Introduces an incremental build feature for faster application building, particularly advantageous for minor code changes.

**Gradle Java Plugin:**
- Enhances flexibility with a code-based build script, replacing Maven's XML verbosity.
- Supports easy customization of the build model within the script itself.

**Creating a Build Scan in Gradle:**
- Gradle allows the creation of build scans to analyze and optimize builds.

**Choosing Gradle Over Maven or Ant:**
- Gradle combines Ant's flexibility with Maven's convention over configuration.
- Implements efficient input and output checks for incremental builds, resulting in faster build times.
- Utilizes Groovy, a DSL known for its readability and ease of use.

**Equivalent of Pom.xml in Gradle:**
- The equivalent to Maven's pom.xml in Gradle is the build.gradle script. It defines project configurations in Groovy or Kotlin.

**Difference Between Gradle Build.gradle and Maven build.xml:**
- Gradle's build.gradle script is code-based, leveraging a DSL for conciseness.
- Maven's build.xml script, in contrast, is XML-centric and may require separate plugins for customizations.

Hans Dockter, Gradle's founder, envisioned a modern build tool with a code-based build script, incremental builds, and an easily customizable build model, addressing Maven's limitations and contributing to improved performance.