---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
command to run a maven wrapper on a specific port

./mvnw spring-boot:run -Dspring-boot.run.arguments=--server.port=8090


-   Why was [Maven](https://maven.apache.org/what-is-maven.html) created?  
    
    -   We wanted a standard way to build the projects, a clear definition of what the project consisted of, an easy way to publish project information, and a way to share JARs across several projects. 
        
-   What is a [Pom.xml]([https://maven.apache.org/guides/introduction/introduction-to-the-pom.html#:~:text=A Project Object Model or,Maven to build the project.&text=Other information such as the,such can also be specified.)](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html#:~:text=A%20Project%20Object%20Model%20or,Maven%20to%20build%20the%20project.&text=Other%20information%20such%20as%20the,such%20can%20also%20be%20specified.)) (Project Object Model) file? Which Build Tool uses it?  
    
    -   A Project Object Model or POM is Maven's fundamental unit of work. It is an XML file that contains information about the project and configuration details used by Maven to build the project.

Maven was created in 2002 as a direct response to the frustrations of building Java applications using its predecessor, Apache Ant.

3 key improvements that Maven’s creator, Jason van Zyl, included are:

	default directory structure in Java projects.: helps developers easily move between projects

	standardize how Java applications are built: the default Maven lifecycle consists of a series of phases (e.g. compile, test, and package). Developers don’t have to rewrite build logic in new projects & can build projects on the Maven command line interface (CLI) in a standard way.

	store dependencies externally: dependencies move out of version control and into a remote repository known as Maven Central. This makes updating dependency versions simpler.

![[Maven Timeline.png]]

Maven runs within the Java Virtual Machine (JVM) and it’s core functionality builds Java applications only. Using 3rd party plugins like the kotlin-maven-plugin you can build Kotlin projects, the scala-maven-plugin for Scala projects, and other language plugins exist too.

<mark style="background: #FFB86CA6;">A Java virtual machine is a virtual machine that enables a computer to run Java programs as well as programs written in other languages that are also compiled to Java bytecode. The JVM is detailed by a specification that formally describes what is required in a JVM implementation.</mark>

Maven projects are defined with an XML build file containing at a basic level:

	the project group, artifact id, and version

	what plugins to apply

	the project’s dependencies

You’ll see a Maven build file example later, but once created you can interact with the project via the Maven CLI.

For example, running mvn test executes the default Maven lifecycle, including all phases up to and including test.

	validate: ensures the Maven project is correct

	compile: transforms Java source code into bytecode

	test: executes tests to verify application functionality

Each phase has goals attached, which correspond to code that actually does the work. e.g. the compile phase contains the compiler:compile goal. You’ll learn more about how phases and goals work later.

Finally, Maven is a free-to-use open source project whose source code is available on GitHub. It’s part of the Apache software foundation, which supports open-source software with help from donations