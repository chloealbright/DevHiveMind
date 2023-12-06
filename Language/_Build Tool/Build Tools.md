![[Maven v Gradle.png]]

Both ***Maven*** and ***Gradle*** fall into the category of build tools. They’re designed to automate the work involved to take your application’s source code and transform it into an ***artifact*** to be published. 

In JavaScript the tools would be something like ***Yarn, NPM, PNPM, webpack bundler, gulp, babel, parcel, browserify, grunt, or requireJS ***

The outfolder is like a build folder for your code run in intelliJ

A bundler is JavaScript equivalent to a build tool 

<mark style="background: #FFF3A3A6;">The term "build" has different meanings in different languages. In some interpreted languages such as Python or Ruby , there is actually no need for a build step at all. </mark>

<mark style="background: #FFF3A3A6;">In general when we talk about building we mean preparing software to run on the platform where it's intended to run. This might mean, for example, that if you've written your application in TypeScript, and you intend to run it on Node, then the build step might be transpiling the TypeScript into JavaScript. </mark>

<mark style="background: #FFF3A3A6;">This step is much more complicated (and required) in compiled languages such as C and Rust where the code needs to be compiled into an executable. </mark>

<mark style="background: #FFF3A3A6;">In part 7 we had a look at webpack that is the current de facto tool for building a production version of a React or any other frontend JavaScript or TypeScript codebase. 
</mark>


## ***Build*** Then ***Deploy*** 

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

### Small Java project 
10 subprojects each with 50 main classes and 50 test classes. 1,000 class total. 
![[Small build performance.png]]

### Medium Java project
100 subprojects each with 100 main classes and 100 test classes. 20,000 class total. 
![[Medium build performance.png]]
From <[https://tomgregory.com/maven-vs-gradle-comparison/](https://tomgregory.com/maven-vs-gradle-comparison/)>  

Both Maven and Gradle require a build file to configure a project. 

To compare how they look, below is Maven’s pom.xml and Gradle’s Groovy build.gradle for a simple Java Spring Boot application 

Xml vs kind of like json 

Maven’s pom.xml is 62 lines, so almost twice the length of the 35 line build.gradle. This difference is mainly because XML is just more wordy. 

With such a large size difference, for many the build.gradle is easier to read and more maintainable than the pom.xml. 

For example, in Gradle a pull request to add a new dependency is a 1 rather than 4 line change. 

## Maven vs. Gradle usability comparison 

To build applications with Maven a local Maven installation is required, which Gradle avoids through it’s wrapper script. The Gradle wrapper means that engineers can clone a repository and immediately build the project without installing Gradle. This also makes Gradle easier to use on CI servers. 

Once everything is setup, to run a Maven build you pass a phase to the Maven command (e.g. mvn package). With Gradle you pass a task to the Gradle wrapper (e.g. ./gradlew build). 

Maven creates build artifacts within a target directory, whereas Gradle uses a build directory.

![[Build Workflow.png]]

The console output for Maven shows all info level log statements and test output. Gradle has a dynamic console, which shows only the task it’s currently working on with a final success/failure message.

Which console is better is subjective, but some may find Gradle’s console easier to read as it’s more concise. If detailed output is needed, you can enable it via the command line options.

![[Maven-vs-gradle-build-run.gif]]

For ongoing support with Maven it’s not obvious where to go. You cannot raise issues on the GitHub repository and the Slack channel is only for contributors.

For Gradle support you can ask questions on the Gradle forum, Gradle community Slack channel, or raise issues on the Gradle repository itself. You can also debug Gradle build scripts directly from your IDE to solve issues yourself.

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

## Side-by-side feature comparison

![[Maven & Gradle Comparison.png]]

![[Maven and Gradle Technical.png]]