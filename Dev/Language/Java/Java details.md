JVM is a part of Java Run Environment (JRE). It cannot be separately downloaded and installed. To install JVM, you need to install JRE.

Java EE(Enterprise edition) is basically a add-on of libraries or API to support enterprise code development or services and isn't in development anymore but has been token over by eclipse and it's called Jakarta EE

Java SE is also refereed to as API's 
  
But the JRE is still being used  
  
Java ME is a subset of JRE for embedded systems used in the internet of things  

Android is also a Java environment but it's provided by Google It also uses the job of programming language but the runtime environment is a little different

Oracle JDK and OpenJDK

>[!note] Java packages are always written in lowercase letters. Not like Java classes, where the first letter is usually a capital letter.

## Important reasons of using JRE:

-   JRE contains class libraries, JVM, and other supporting files. It does not contain any tool for Java development like a debugger, compiler, etc.
-   It uses important package classes like math, swingetc, util, lang, awt, and runtime libraries.
-   If you have to run Java applets, then JRE must be installed in your system.

## Important reasons of using JVM:
-   JVM provides a platform-independent way of executing Java source code.
-   It has numerous libraries, tools, and frameworks.
-   Once you run Java program, you can run on any platform and save lots of time.
-   JVM comes with JIT(Just-in-Time) compiler that converts Java source code into low-level machine language. Hence, it runs more faster as a regular application.

important features of JDK:

-   It enables you to handle multiple extensions in a single catch block.
-   JDK includes all features that JRE has.
-   It contains development tools such as a compiler, debugger, etc.
-   JDK provides the environment to develop and execute Java source code.
-   It can be installed on Windows, Unix, and Mac operating systems.
-   Diamond operator can be used in specifying a generic type interface instead of writing the exact one.

important features of JRE:

-   Java Runtime Environment is a set of tools using which the JVM actually runs.
-   JRE contains deployment technology, including Java Web Start and Java Plug-in.
-   Developers can easily run the source code in JRE, but he/she cannot write and compile the Java program.
-   It includes integration libraries like Java Database Connectivity (JDBC), Remote Method Invocation (RMI), Java Naming and Directory Interface (JNDI), and more.
-   JRE has JVM and Java HotSpot virtual machine client.
- Jre doesnt need to be installed since included in JDK

important features of JVM:

-   It enables you to run applications in a cloud environment or in your device.
-   Java Virtual Machine converts byte code to the machine-specific code.
-   It provides basic java functions like memory management, security, garbage collection, and more.
-   JVM runs the program by using libraries and files given by Java Runtime Environment.
-   JDK and JRE both contain Java Virtual Machine.
-   It can execute the java program line by line hence it is also called as interpreter.
-   JVM is easily customizable for example, you can allocate minimum and maximum memory to it.
-   It is independent from hardware and the operating system. So, you can write a java program once and run anywhere.



-   What does static mean in Java?

-   static is used for memory management
-   It can be used with classes, variables, methods, and blocks
-   They belong to the class instance of a specific instance



You could ask like what are J2EE Technologies.

Here quick Answer is Servlet, JSP and EJB.

Source from Google:

J2EE applications are made up of components. A J2EE component is a self-contained functional software unit that is assembled into a J2EE application with its related classes and files and that communicates with other components. The J2EE specification defines the following J2EE components:

-   Application clients and applets are components that run on the client.
-   Java Servlet and JavaServer Pages (JSP) technology components are Web components that run on the server.
-   Enterprise JavaBeans (EJB) components (enterprise beans) are business components that run on the server.

J2EE components are written in the Java programming language and are compiled in the same way as any program in the language. The difference between J2EE components and "standard" Java classes is that J2EE components are assembled into a J2EE application, verified to be well formed and in compliance with the J2EE specification, and deployed to production, where they are run and managed by the J2EE server.