---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Libraries contain modules full of packages full of Java classes

From Small to Big

In order from small to big, it goes: Package -> Module -> Library.

A package contains many classes (.java files) and is basically a folder in your Java projects.

A module contains many packages (folders with .java files). A module is basically a single purpose library.

A library contains many modules (a module is usually packaged as a single .jar file). A library can contain many modules, but they are usually all connected by some theme.

Package

A package is a namespace that organizes a set of related classes and interfaces. Conceptually you can think of packages as being similar to different folders on your computer. You might keep HTML pages in one folder, images in another, and scripts or applications in yet another. Because software written in the Java programming language can be composed of hundreds or thousands of individual classes, it makes sense to keep things organized by placing related classes and interfaces into packages. [4](https://docs.oracle.com/javase/tutorial/java/concepts/package.html)

Module

A module is a collection of related Java packages and associated resources with a descriptor file, which contains information about which packages/resources are exposed by this module, which packages are used by current module and some other information. A Java module is a packaging mechanism that enables you to package a Java application or Java API as a separate Java module. A Java module is packaged as a modular JAR file. A Java module can specify which of the Java packages it contains that should be visible to other Java modules which uses this module. A Java module must also specify which other Java modules is requires to do its job.

Java modules is a [new feature in Java 9](http://tutorials.jenkov.com/java/index.html#new-in-java-9) via the Java Platform Module System (JPMS). The Java Platform Module System is also sometimes referred to as Java Jigsaw or Project Jigsaw depending on where you read. Jigsaw was the internally used project name during development. Later Jigsaw changed name to Java Platform Module System. [1](http://tutorials.jenkov.com/java/modules.html)

Library

A Java library is just a collection of classes that have been written by somebody else already. You download those classes and tell your computer about them, and then you can use those classes in your code. This lets you expand what Java can do and rely on code that other people have tested instead of doing everything yourself. [2](https://happycoding.io/tutorials/java/libraries) A library is a collection of related functionality, whereas a module only provides a single piece of functionality. Which means that, if you have a system with both modules and libraries, a library will typically contain multiple modules. For example, you might have a collections library which contains a List module, a Set module and a Map module inside a single library. A single library might contain many .jar files, whereas a single module is just one .jar file. 