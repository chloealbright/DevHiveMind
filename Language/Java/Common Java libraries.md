---
tags:
  - Java
  - library
author:
  - jacgit18
  - chatgpt
Comments: This documentation discusses common library used in Java ecosystem.
Status: Done
Started: 
EditDate: 2024-03-03
Relates:
---
**Google Guava: A Comprehensive Overview**

Google Guava serves as a versatile library, offering an array of features to enhance Java development.

1. **Additional Collections:**
   - Guava extends Java collections, providing additional utilities and classes that streamline common tasks.

2. **Caching:**
   - Guava facilitates efficient caching mechanisms, aiding in the optimization of data retrieval and storage.

3. **IO Helpers:**
   - The library includes utilities for simplified input/output operations, making file handling and processing more straightforward.

**Apache Commons: A Multi-Purpose Library**

Apache Commons encompasses a broad range of reusable Java components.

1. **Collection:**
   - Commons provides enhanced collection classes and utilities, augmenting the capabilities of standard Java collections.

2. **CSV:**
   - The CSV component assists in parsing and manipulating CSV (Comma-Separated Values) data.

3. **IO:**
   - Commons IO simplifies common I/O tasks with utility classes for file handling, stream management, and more.

**Apache Log4j & Logging Library: Logging Excellence**

1. **Logging Library:**
   - Log4j stands out as a reliable logging library, offering flexible and configurable logging capabilities for Java applications.

**Distributed System Libraries:**

1. **Netty:**
   - Netty is a robust networking framework, providing a high-performance and asynchronous communication foundation.

2. **Akka:**
   - Akka supports the development of distributed and concurrent applications, utilizing the actor model for scalable and fault-tolerant systems.

**Data Processing Libraries:**

1. **Apache Hadoop:**
   - Hadoop facilitates the distributed processing of large datasets, supporting parallel processing and fault tolerance.

2. **Apache Spark:**
   - Spark is a fast and versatile data processing engine, suitable for both batch and real-time processing.

**DL4J - Deep Learning for Java:**

1. **Deep Learning Library:**
   - DL4J empowers Java developers with tools for building and training deep neural networks.

**Not Distributed Systems:**

1. **RxJava - Reactive Programming:**
   - RxJava introduces reactive programming principles, enabling developers to handle asynchronous and event-based scenarios seamlessly.

2. **Apache Camel: Enterprise Integration Excellence**

   - Camel simplifies Enterprise Application Integration (EAI) by providing a comprehensive set of connectors and transport options.

**Data Access Library:**

1. **JDBC:**
   - The Java Database Connectivity (JDBC) API allows direct interaction with databases, providing a standardized interface for database connectivity.

**Additional Considerations:**

- Guava, Commons, and other libraries mentioned fulfill specific niches, and their selection depends on project requirements and goals.
- Leveraging ORMs like Hibernate or SQL DSLs, as mentioned, enhances data access capabilities in Java applications.

In summary, the Java libraries mentioned cater to diverse needs, from basic collections to advanced data processing and deep learning, offering developers a rich set of tools for various application scenarios.



 technologies/tools used in Java server-side development

Jackson JSON/XML

JPA and Hibernate

Thymeleaf templating

Graphite and Grafana monitoring

Log4j and JSON for structured logging

Splunk distributed logging collection

Elasticsearch logstash kibana

Hystrix curcuit breakers

Spring Cloud Config

Eureka service discovery

Pivotal or AWS hosting

Flyway or Liquibase database change management

Sonar, findbugs, PMD static code analysis

JUnit, Mockito, AssertJ for TDD

RestAssured web service end to end tests with Cucumber and Serenity reports

Selenium browser testing

Litmus email html rendering testing

Jenkins CI

Embedded Tomcat or Jetty

Java 8 upwards




Internationalization Tool 

Internationalization is the process of designing an application so that it can be adapted to various languages and regions without engineering changes. 

For this purpose, the JDK brings native2ascii. This tool converts a file with characters supported by JRE to files encoded in ASCII or Unicode escapes. 

4.4. Remote Method Invocation (RMI) Tools 

RMI tools enable remote communication between Java applications thus providing scope for development of distributed applications. 

RMI enables an object running in one JVM to invoke methods on an object running in another JVM. These tools include: 

4.5. Java IDL and RMI-IIOP Tools 

Java Interface Definition Language (IDL) adds Common Object-Based Request Broker Architecture (CORBA) capability to the Java platform. 

These tools enable distributed Java web applications to invoke operations on remote network services using industry standard Object Management Group (OMG) – IDL. 

Likewise, we could use Internet InterORB Protocol (IIOP). 

RMI-IIOP, i.e. RMI over IIOP enables programming of CORBA servers and applications via the RMI API. Thus enabling connection between two applications written in any CORBA-compliant language via Internet InterORB Protocol (IIOP). 

These tools include: 

4.6. Java Deployment Tools 

These tools help in deploying Java applications and applets on the web. They include: 

4.7. Java Plug-in Tool 

JDK provides us with htmlconverter. Furthermore, it's used in conjunction with the Java Plug-in. 

On the one hand, Java Plug-in establishes a connection between popular browsers and the Java platform. As a result of this connection, applets on the website can run within a browser. 

On the other hand, htmlconverter is a utility for converting an HTML page containing applets to a format for Java Plug-in. 

4.8. Java Web Start Tool 

JDK brings javaws. We can use it in conjunction with the Java Web Start. 

This tool allows us to download and launch Java applications with a single click from the browser. Hence, there is no need to run any installation process. 

4.9. Monitoring and Management Tools





We can see that the major releases of Java SE came approximately every two years until Java SE 7. It took five years to move from Java SE 6, and another three after that to reach Java SE 8. 

Since Java SE 10, we've come to expect new releases every six months. However, not all releases will be the Long-Term-Support (LTS) releases. As a result of Oracle's release plan, the LTS product releases will only happen every three years. 

Java SE 17 is the latest LTS version, and Java SE 8 received free public updates until December 2020 for non-commercial usage. 

This development kit got its current name after Oracle bought Sun Microsystems in 2010. Before that, the name was SUN JDK, and it was the official implementation of the Java programming language. 



OpenJDK is behind Oracle JDK when it comes to java SE version Oralce is at 17lts while open is at 11  

## Release Schedule 

As we mentioned, ***Oracle will deliver releases every three years, while OpenJDK will be released every six months. ***

Oracle provides long term support for its releases. On the other hand, OpenJDK only supports the changes to a release until the next version is released. 

There's no real technical difference between the two, since the build process for Oracle JDK is based on that of OpenJDK. 

When it comes to performance, ***Oracle's is much better regarding responsiveness and JVM performance.*** It puts more focus on stability because of the importance it gives to its enterprise customers. 

OpenJDK, in contrast, delivers releases more often. As a result, we can encounter problems with instability. Based on [community feedback](https://www.reddit.com/r/java/comments/6g86p9/openjdk_vs_oraclejdk_which_are_you_using/), we know some OpenJDK users have encountered performance issues. 

***Oracle JDK is fully developed by the Oracle Corporation, whereas OpenJDK is developed by Oracle, OpenJDK, and the Java Community.*** However, top-notch companies like Red Hat, Azul Systems, IBM, Apple Inc., and SAP AG also take an active part in its development. 

As we can see from the link in the previous subsection, when it comes to ***popularity with the top companies that use Java Development Kits in their tools,*** such as Android Studio or IntelliJ IDEA, ***Oracle JDK used to be the more preferred, but both of those companies have switched to the OpenJDK based JetBrains*** [builds](https://bintray.com/jetbrains/intellij-jdk/). 

Furthermore, major Linux distributions (Fedora, Ubuntu, Red Hat Enterprise Linux) provide OpenJDK as the default Java SE implementation. 

### Differences between Amazon Corretto JDK and OpenJDK 

One popular implementation of the Java Development Kit is Amazon Corretto. Although it is based on OpenJDK, there are a few differences between them. 

Amazon Corretto is a free, multi-platform, production-ready distribution of the OpenJDK. It is developed, maintained, and supported by Amazon Web Services (AWS) and is designed specifically for running Java applications on AWS and other cloud platforms. Amazon Corretto provides long-term support (LTS) and security updates at no cost. 

Another key difference between OpenJDK and Amazon Corretto JDK is that Amazon Corretto includes additional features and optimizations that are specifically designed to improve performance, security, and reliability in production environments.