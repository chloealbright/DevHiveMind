
## "S"ingle Responsibility Principle

Single Responsibility Principle is another SOLID design principle and represents “S” on the SOLID acronym. As per SRP, there should not be more than one reason for a class to change, or a level should always handle single functionality.

> _The key benefit of this principle is that it reduces coupling between the individual component of the software and Code._

For example, If you put more than one functionality in one Class in Java, it introduces **coupling** between two functionality, and even if you change one feature, there is a chance you broke coupled functionality, which requires another round of testing to avoid any surprise on the production environment.

## S — ingle Responsibility Principle

An object should have one and only one responsibility.

You don’t need to have an object that does different or many tasks. An object can have many behaviors and methods, but all of them are relevant to it’s single responsibility.

So, whenever there is a change that needs to happen, there will be only one class to be modified, this class has one primary responsibility.


## Open Closed Design Principle

According to tho this OOP design principle, “Classes, methods or functions should be Open for extension (new functionality) and Closed for modification.”

This is another beautiful SOLID design principle, coined by Uncle Bob on his classic [**Clean Codebook**](http://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882?tag=javamysqlanta-20), which prevents someone from changing already tried and tested code.

> _The key benefit of this design principle is that already tried and tested code is not touched which means they won’t break._

Here is a Java code example that _violates_ the Open-Closed Design Principle of Programming:

[  
](https://javarevisited.blogspot.com/2018/02/10-courses-to-prepare-for-programming-job-interviews.html)



## Liskov Substitution Principle (LSP)

According to the Liskov Substitution Principle, Subtypes must be substitutable for supertype I mean methods or functions which use superclass type must be able to work with the [object](http://javarevisited.blogspot.com/2012/12/what-is-object-in-java-or-oops-example.html) of subclass without any issue”.

LSP is closely related **to the Single responsibility principle** and **Interface Segregation Principle**.

> _If a class has more functionality than subclass might not support some of the functionality and does violate LSP._

In order to follow [LSP SOLID design principle](https://click.linksynergy.com/deeplink?id=JVFxdTr9V80&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fsolid-principles-object-oriented-design-architecture%2F), derived class or subclass must enhance functionality, but not reduce them. LSP represents “L” on the SOLID acronym.




##  Interface Segregation Principle (ISP)

The interface Segregation Principle states that a client should not implement an [interface](http://javarevisited.blogspot.com/2012/04/10-points-on-interface-in-java-with.html) if it doesn’t use that.

This happens mostly when one interface contains more than one functionality, and the client only needs one feature and no other.

There is no doubt that Interface design is a tricky job because once you release your interface, you can not change it without breaking all implementation. Well, Java 8’s [default or defender method](https://javarevisited.blogspot.com/2014/07/default-defender-or-extension-method-of-Java8-example-tutorial.html#axzz5kO8vmDxy) feature does provide a way for interface evolution, but not all Programming languages support those features.

> _Another benefit of this design principle in Java is, the interface has the disadvantage of implementing all method before any class can use it so having single functionality means less method to implement._


## Dependency Injection or Inversion principle

Don’t ask for dependency; it will be provided to you by the framework. This has been very well implemented in the [Spring framework](http://www.java67.com/2017/11/top-5-free-core-spring-mvc-courses-learn-online.html), one of the most popular Java frameworks for writing real-worth applications.

> _The beauty of this design principle is that any class which is injected by DI framework is easy to test with the mock object and easier to maintain because object creation code is centralized in the framework and client code is not littered with that._

There are multiple ways to implemented [**Dependency injection**](http://javarevisited.blogspot.com/2012/12/inversion-of-control-dependency-injection-design-pattern-spring-example-tutorial.html) like using bytecode instrumentation, which some AOP (Aspect Oriented Programming) framework like AspectJ does or by using proxies just like used in Spring.

You can further see the [**SOLID Principles of Object-Oriented Design and Architecture**](https://click.linksynergy.com/deeplink?id=JVFxdTr9V80&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fsolid-principles-object-oriented-design-architecture%2F) course on Udemy to learn more about this useful principle. It also represents “D” on the SOLID acronym.