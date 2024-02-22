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



## Maven vs. Gradle customization comparison

Once your project is setup to compile your application and run the tests, you might want to add more functionality. Both Maven and Gradle offer plugins to, for example, run static code analysis on calculate test code coverage.

What about further customisation though?

To customise a Maven build you only have 1 option, which is to write your own plugin. Writing custom plugins means creating a separate project and publishing the plugin artifact to be used in any project.

With Gradle there are 3 levels of customisation.

1.  build script: define tasks, methods, and classes to reuse within the build script
2.  project: put code in the special buildSrc directory to reuse across multiple subprojects
3.  cross-project: create a separate project and publish a reusable plugin, as with Maven

Customisation example

Gradle’s build script, coupled with its dynamic build model, allows more customisation than Maven. For example, we can easily register a task to print the dependency count.

```
tasks.register('countDependencies') {
doLast { println "Dependency count: ${configurations.getByName('compileClasspath').getAllDependencies().size()}" 
		}
		 }
```

```
$ ./gradlew countDependencies 
> Task :countDependencies 
> Dependency count: 6 BUILD SUCCESSFUL in 1s 
> 1 actionable task: 1 executed
```

To add similar custom behaviour in Maven involves creating an entire separate project.

Being able to reuse build logic so easily in Gradle is important to reduce duplication and improve maintainability, especially for larger multi-module projects.

Finally, both Maven and Gradle support multi-module projects for when your projects grows in size. In Maven the sub-modules are defined in the pom.xml build file itself whereas in Gradle they go in the settings.gradle file.

Maven is used more but Gradle is getting more adoption

## Choosing between Maven & Gradle

Now you know the differences between Maven and Gradle, maybe you already have a preference?

If not, here are some further recommendations based on your situation.

Using Gradle on a brand new project

For a brand new project use Gradle instead of Maven, because it’s:

-   faster
-   more concise
-   easier to customise
-   promotes build code reuse
-   improves the developer experience

In summary, Gradle increases developer productivity allowing businesses to more effectively add value to their customers.

If you want to use Gradle for your next project and don’t know where to start, I recommend my extremely helpful all-in-one [Gradle Hero course](https://learn.tomgregory.com/courses/gradle-hero). It helps you master building Java applications with Gradle as quickly as possible.

Considering a Maven to Gradle migration

For a Maven to Gradle migration there are some other factors to consider.

-   resourcing: Maven is more universally known than Gradle, so your team may take some time to get up to speed
-   timeline: migrating projects takes time, so consider the lifespan of your application and the frequency you change it
-   futureproof: Gradle is becoming more popular, has more active development, and has more modern features than Maven

For an application that sees regular development, I recommend a migration to Gradle to save time for developers. If you consider all the development hours spent waiting for Maven builds to complete, suddenly the time investment to perform the migration can seem insignificant.

Migrating your project might be quicker than you think. To learn about the steps involved see [How to do a Maven to Gradle migration on a Java Spring Boot project](https://tomgregory.com/how-to-do-a-maven-to-gradle-migration-on-a-java-spring-boot-project/).

For applications that see very infrequent development (e.g. less than a few changes per year), sticking with Maven may still be the best option.

For some inspiration, here’s the experience of the Spring Boot team who migrated from Maven to Gradle in early 2020.

Migrating the build to Gradle has undoubtedly been a success. As noted above, a full Maven-based build was taking an hour or more, both on CI and on developers’ own machines. Over the last four weeks, the mean successful build time with Gradle has been 9 minutes 22 seconds, 

Andy Wilkinson, [Migrating Spring Boot’s Build to Gradle](https://spring.io/blog/2020/06/08/migrating-spring-boot-s-build-to-gradle)

Your team and Gradle

If you know you want to migrate to Gradle, but need to convince your team, here are some benefits from different team-members’ perspectives.