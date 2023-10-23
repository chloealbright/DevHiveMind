[["S"ingle Responsibility Principle]]
[["O"pen Closed Design Principle]]
[["L"iskov Substitution Principle]]
[["I"nterface Segregation Principle]]
[["D"ependency Inversion]]

## "O"pen Closed Design Principle

According to tho this OOP design principle, software entities like (“Classes, modules, methods, functions, etc...) should be Open for extension (new functionality) and Closed for modification.”

Whenever you need to add additional behaviors, or methods, you don’t have to modify the existing one, instead, you start writing new methods.

Because, _What if you changed a behavior of an object, where some other parts of the system depends on it?_. So, you need to change also every single part in the software that has a dependency with that object, and check the logic, and do some extra testing.

> _The key benefit of this design principle is that already tried and tested code is not touched which means they won’t break._







## Liskov Substitution Principle (LSP)

According to the Liskov Substitution Principle, Subtypes must be substitutable for supertype I mean methods or functions which use superclass type must be able to work with the [object](http://javarevisited.blogspot.com/2012/12/what-is-object-in-java-or-oops-example.html) of subclass without any issue”.

LSP is closely related **to the Single responsibility principle** and **Interface Segregation Principle**.

> _If a class has more functionality than subclass might not support some of the functionality and does violate LSP._

In order to follow [LSP SOLID design principle](https://click.linksynergy.com/deeplink?id=JVFxdTr9V80&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fsolid-principles-object-oriented-design-architecture%2F), derived class or subclass must enhance functionality, but not reduce them. LSP represents “L” on the SOLID acronym.


## L — iskov Substitution Principle

A super class can be replaced by any of it’s inheriting sub classes at any parts of the system without any change in the code.

It means that the sub classes should extend the functionality of the super class without overriding it.

That’s why we’ve mentioned ealier in [Class Diagram](https://medium.com/omarelgabrys-blog/e7535090824c) that it’s not a good case practice to override the methods of the super class in inheritance.


##  Interface Segregation Principle (ISP)

The interface Segregation Principle states that a client should not implement an [interface](http://javarevisited.blogspot.com/2012/04/10-points-on-interface-in-java-with.html) if it doesn’t use that.

This happens mostly when one interface contains more than one functionality, and the client only needs one feature and no other.

There is no doubt that Interface design is a tricky job because once you release your interface, you can not change it without breaking all implementation. Well, Java 8’s [default or defender method](https://javarevisited.blogspot.com/2014/07/default-defender-or-extension-method-of-Java8-example-tutorial.html#axzz5kO8vmDxy) feature does provide a way for interface evolution, but not all Programming languages support those features.

> _Another benefit of this design principle in Java is, the interface has the disadvantage of implementing all method before any class can use it so having single functionality means less method to implement._

## I — nterface Segregation Principle

==Interfaces should be specific rather than doing many and different things.==

That’s because any implementing class will only implement the specific needed interfaces rather than being forced to implement methods that it doesn’t need it.

So, large interfaces should be decomposed into smaller, more specific ones.
