---
tags:
  - OO
author:
  - jacgit18
Status: refinement
Started: 2023-10-29
EditDate: 2023-10-29
Relates:
---
## Abstraction
  - The function and uses of a class are known
  - The actual implementation is hidden from the user.
    - This can be done using an abstract class or an Interface to define the behavior of a class without implementing it.
  - Abstraction can be achieved by using abstract classes and interfaces.
  - Deferring the behavior of an object to its child classes
## Abstract Class vs. Interface

- What is the difference between an abstract class and an interface?
  - An abstract class permits you to make a functionality that subclasses can implement or override
  - An interface only permits you to state functionality but not to implement it.
  - A class can extend only one abstract class, while a class can implement multiple interfaces.
  - An abstract class is a class that contains the keyword abstract, while an Interface is a class with a method without a body that uses the keyword implement.
  - Neither creates an object in java.

## Inheritance vs. Abstraction

- What are the differences between inheritance and abstraction?
  - The key difference between the two principles lies in how abstraction focuses on the privacy of functionality, while inheritance focuses on sharing functionality (and reusability).
# Structural model
![[Abstract class Diagram.png]]


Abstract classes typically feature the abstract keyword in their declaration and should contain at least one abstract method, i.e., a method without a body. They can also have multiple concrete methods. The inheriting classes are obliged to implement the abstract methods, ensuring a consistent structure across subclasses.

The key reasons for using abstract classes include:

1. Offering default functionality for subclasses.
2. Providing a template for future specific classes.
3. Defining a common interface for its subclasses.
4. Facilitating code reusability.

In the context of Java, abstraction is the process of presenting only essential information to a user. This abstraction can be achieved using abstract classes or interfaces. The keyword "abstract" is used for classes and methods. Abstract classes cannot be used to create objects; access is only granted through inheritance. Abstract methods, which lack a method body, can only be used in abstract classes. These abstract classes can contain a combination of abstract and regular methods.
