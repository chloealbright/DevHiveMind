---
tags:
  - SOLID
---

According to the Liskov Substitution Principle, Subtypes must be substitutable for supertype I mean methods or functions which use superclass type must be able to work with the [object](http://javarevisited.blogspot.com/2012/12/what-is-object-in-java-or-oops-example.html) of subclass without any issue”.

LSP is closely related **to the Single responsibility principle** and **Interface Segregation Principle**.

> _If a class has more functionality than subclass might not support some of the functionality and does violate LSP._

In order to follow [LSP SOLID design principle](https://click.linksynergy.com/deeplink?id=JVFxdTr9V80&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fsolid-principles-object-oriented-design-architecture%2F), derived class or subclass must enhance functionality, but not reduce them. LSP represents “L” on the SOLID acronym.


## L — iskov Substitution Principle

A super class can be replaced by any of it’s inheriting sub classes at any parts of the system without any change in the code.

It means that the sub classes should extend the functionality of the super class without overriding it.

That’s why we’ve mentioned ealier in [Class Diagram](https://medium.com/omarelgabrys-blog/e7535090824c) that it’s not a good case practice to override the methods of the super class in inheritance.

1. **Java:**
   ```java
   // Before LSP
   class Bird {
       void fly() {
           // logic to fly
       }
   }
   
   class Penguin extends Bird {
       void fly() {
           // Penguins can't fly
           throw new UnsupportedOperationException("Penguins can't fly");
       }
   }
   
   // After LSP
   interface FlyingBird {
       void fly();
   }
   
   class Bird implements FlyingBird {
       void fly() {
           // logic to fly
       }
   }
   
   class Penguin implements FlyingBird {
       void fly() {
           // Penguins can't fly
           throw new UnsupportedOperationException("Penguins can't fly");
       }
   }
   ```

2. **Python:**
   ```python
   # Before LSP
   class Bird:
       def fly(self):
           # logic to fly
           pass
   
   class Penguin(Bird):
       def fly(self):
           # Penguins can't fly
           raise NotImplementedError("Penguins can't fly")
   
   # After LSP
   from abc import ABC, abstractmethod
   
   class FlyingBird(ABC):
       @abstractmethod
       def fly(self):
           pass
   
   class Bird(FlyingBird):
       def fly(self):
           # logic to fly
           pass
   
   class Penguin(FlyingBird):
       def fly(self):
           # Penguins can't fly
           raise NotImplementedError("Penguins can't fly")
   ```

In these examples, before adhering to LSP, the `Penguin` subclass broke the expectation that all birds can fly. After applying LSP, the code ensures that subclasses (`Penguin`) can be substituted for their base class (`Bird`) without causing unexpected behavior or violating the contract defined by the base class.