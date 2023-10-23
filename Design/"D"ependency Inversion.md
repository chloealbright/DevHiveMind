---
tags:
  - SOLID
  - refine
---


Don’t ask for dependency; it will be provided to you by the framework. This has been very well implemented in the [Spring framework](http://www.java67.com/2017/11/top-5-free-core-spring-mvc-courses-learn-online.html), one of the most popular Java frameworks for writing real-worth applications.

> _The beauty of this design principle is that any class which is injected by DI framework is easy to test with the mock object and easier to maintain because object creation code is centralized in the framework and client code is not littered with that._

There are multiple ways to implemented [**Dependency injection**](http://javarevisited.blogspot.com/2012/12/inversion-of-control-dependency-injection-design-pattern-spring-example-tutorial.html) like using bytecode instrumentation, which some AOP (Aspect Oriented Programming) framework like AspectJ does or by using proxies just like used in Spring.

You can further see the [**SOLID Principles of Object-Oriented Design and Architecture**](https://click.linksynergy.com/deeplink?id=JVFxdTr9V80&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fsolid-principles-object-oriented-design-architecture%2F) course on Udemy to learn more about this useful principle. It also represents “D” on the SOLID acronym.


## D — ependency Inversion Principle

Try to minimize the dependency between objects by using abstraction.

If for example you have a _App_ class that depends on very specialized classes; _Database_ and _Mail_ (dependencies).

Instead, we could have _App_ object that deals with _Service_ class, which is more abstract, rather than something very specific. So, now the _App_ class is not dependent on the concrete classes, but on abstraction.

And the benefit of that is we are able to replace and extend the functionality of _Service_ class without changing the _App_ class at all.

Perhaps we can replace the _Database_ and _Mail_ classes, or add additional classes like _Logger_ and _Auth_ as well.


In the SOLID principles of object-oriented programming, the "D" stands for "Dependency Inversion," not "Dependency Injector." The SOLID principles are a set of five design principles that aim to create more maintainable and understandable software. Dependency Inversion is the fifth principle, and it emphasizes that high-level modules (abstractions) should not depend on low-level modules (concrete implementations), but both should depend on abstractions.  
  
In contrast, "Dependency Injector" typically refers to a design pattern or mechanism used to implement Dependency Injection, which is a related concept but not part of the SOLID principles. Dependency Injection is a technique that helps achieve the Dependency Inversion principle by injecting dependencies (often through constructor parameters) into a class rather than having the class create or manage its dependencies internally.