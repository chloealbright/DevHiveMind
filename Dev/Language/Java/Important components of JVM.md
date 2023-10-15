1) Class Loader 

The class loader is a subsystem used for loading class files. It performs three major functions viz. Loading, Linking, and Initialization. 

2) Method Area 

JVM Method Area stores structure of class like metadata, the code for Java methods, and the constant runtime pool. 

3) Heap 

All the Objects, arrays, and instance variables are stored in a heap. This memory is shared across multiple threads. 

4) JVM language Stacks 

Java language Stacks store local variables, and its partial results. Each and every thread has its own JVM language stack, created concurrently as the thread is created. A new frame is created when method is invoked, and it is removed when method invocation process is complete. 

5) PC Registers 

PC registers store the address of the Java virtual machine instruction, which is currently executing. In Java, each thread has its separate PC register. 

6) Native Method Stacks 

Native method stacks hold the instruction of native code depends on the native library. It allocates memory on native heaps or uses any type of stack. 

7) Execution Engine 

It is a type of software that is used to test software, hardware, or complete systems. The test execution engine never carries any information about the tested product. 

8) Native Method interface 

The Native Method Interface is a programming framework. It allows Java code, which is running in a JVM to call by libraries and native applications. 

9) Native Method Libraries 

Native Libraries is a collection of the Native Libraries (C, C++), which are needed by the Execution Engine.



compare see if uyou should keep
-   JDK and JRE: The JDK enables programmers to create core Java programs that can be run by the JRE, which included JVM and class libraries. 
    
-   Class Libraries: It is a group of dynamically loadable libraries that Java program can call at run time. 
    
-   Compilers: It is a Java program that accepts text file of developers and compiles into Java class file. It is the common form of output given by compiler, which contains Java byte code. In Java, the primary compiler is Javac. 
    
-   Debuggers: Debugger is a Java program that lets developers test and debug Java programs. 
    
-   JavaDoc: JavaDoc is documentation made by Sun Microsystems for the Java. JavaDoc can be used generating API documentation in HTML file from the source program