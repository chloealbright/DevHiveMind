Gradle uses DSL over xml which is for Maven  
  
  
There Are tools that convert gradle to Maven and vice versa in terms of the pom XML and the gradle build file


-   What is Gradle? 
    
-   Explain Gradle’s Build Lifecycle. 
    
-   What is the use of the Gradle Java Plugin? 
    
-   How do you create a build scan in Gradle? 
    
-   Why would you choose Gradle over Maven or Ant? While choosing one build tool over the other would depend on the project requirements and protocol to be followed, Gradle has some distinct advantages over the other two tools. 
    
    -   It combines the flexibility of Ant and convention over the configuration capabilities of Maven 
        
    -   It checks for updates in inputs and outputs and executes incremental builds. Hence a faster build time 
        
    -   Uses Groovy, a DSL that is easy to read and write in 
        
-   What is the equivalent of Pom.xml (Maven) in Gradle? What is the build script file name? 
    
-   What is the difference between a Gradle Build.gradle script and a Maven build.xml script?



Gradle was created in 2008 to solve some of the shortcomings of building projects with Maven.

Gradle’s founder, Hans Dockter, took inspiration from Maven but had a vision for a more modern build tool. The main features he added included:

	code-based build script to replace XML build file: using the Groovy language (and now Kotlin) makes defining build configurations less verbose than using lengthy XML tags

	easily customisable build model: this is modified directly from the build script. Add custom build logic on the fly without having to develop a separate plugin (see Maven vs. Gradle customisation comparison below).

	incremental build and other performance enhancements: makes building applications much faster, especially when making minor code changes that don’t require a full rebuild (see Gradle vs. Maven performance comparison below).

![[GTimeline.png]]

Gradle also runs inside the JVM. Out-of-the-box it supports building Java, Groovy, Scala, and even C++ applications. 3rd party plugins can be used for other languages like Kotlin.

With Gradle you decide if you want to write build scripts in Groovy or Kotlin. There are lots of similarities between the 2 languages.

The build scripts contain configuration such as:

-   the project’s group, name, and version
-   the plugins to apply
-   dependencies of the application

In Gradle a task is a unit of work to get done in your build. It’s the equivalent of a Maven goal.

Once the build script is created, you can interact with Gradle via the Gradle CLI. Running ./gradlew test executes all tasks required to test your application, including:

-   classes: compiles code and copies resources
-   testClasses: compiles all test code and copies test resources
-   test: actually runs the tests themselves

Gradle models all the tasks in your project in a task graph, where a task can have dependencies on other tasks. Gradle uses this to ensure each task executes at most once. If the task has been executed in a previous build and nothing has changed, Gradle saves time by not executing it again.

The Gradle build tool is an open-source free-to-use product, distributed under the Apache License. It’s maintained by Gradle Inc., who also offer other products and services as part of their paid Gradle Enterprise service.

## Project structure

Unlike Maven, Gradle requires several other files and directories to be added to your repository in addition to build.gradle.

1.  gradle directory contains the wrapper code and properties (more on the Gradle wrapper shortly)
2.  gradlew & gradlew.bat scripts for running a Gradle build via the wrapper
3.  settings.gradle contains extra project settings like the project name