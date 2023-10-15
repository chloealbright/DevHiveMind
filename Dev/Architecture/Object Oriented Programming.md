# Object and Class Comparison

- Compare and contrast an Object and a Class.

# Java Access Modifiers

- In Java, what are access modifiers?
  - Access modifiers are keywords in Java that help to restrict the scope of a class, constructor, variable, method, or data member.
    - `public` - accessible from everywhere in the program and from outside classes
    - `private` - only accessible from within the class they are declared in
    - `protected` - only accessible from within the class they are declared in and subclasses
    - `default` - only accessible within the same package

# Principles of Object-Oriented Programming

- What are the principles of object-oriented programming? What is encapsulation? What is polymorphism?
  - Object-Oriented Programming is a methodology or paradigm for designing a program using classes or objects.
  
## Abstraction

- Abstraction
  - The function and uses of a class are known
  - The actual implementation is hidden from the user.
    - This can be done using an abstract class or an Interface to define the behavior of a class without implementing it.
  - Abstraction can be achieved by using abstract classes and interfaces.
  - Deferring the behavior of an object to its child classes

## Encapsulation

- Encapsulation
  - All data and methods are stored in an appropriate class
  - Instance variables (data) are kept private and use accessor methods (getters/setters) to control access to them
  - The separation and containerization of attributes/methods into a single data object unit.
  - Allows restricted access to members and methods of a class to only those that need it, through keywords such as private, protected, and public.

## Inheritance

- Inheritance
  - Certain classes can inherit the variables/methods from parent classes. Which is also known as a parent-child relationship.
  - This is usually represented as an is-a relationship in Java and is done using the extends keyword to inherit from classes or the implements keyword for interfaces.
  - The property of an object that requires all the properties and behavior of its parent object
    - There are three types of inheritance - single, multilevel, and hierarchical.
  - Allows re-use of code by allowing child classes to inherit code (members and methods) from parent classes.

## Polymorphism

- Polymorphism
  - Means “many forms,” which allows methods with similar signatures to accomplish different tasks.
  - It consists of either compile time or runtime polymorphism.
    - Compile time polymorphism involves method overloading when two methods with the same name have different required parameters.
    - Run time polymorphism is resolved through method overriding, called through the reference variable of a superclass or parent class. Overriding methods have the same signature.

# Abstract Class vs. Interface

- What is the difference between an abstract class and an interface?
  - An abstract class permits you to make a functionality that subclasses can implement or override
  - An interface only permits you to state functionality but not to implement it.
  - A class can extend only one abstract class, while a class can implement multiple interfaces.
  - An abstract class is a class that contains the keyword abstract, while an Interface is a class with a method without a body that uses the keyword implement.
  - Neither creates an object in java.

# Inheritance vs. Abstraction

- What are the differences between inheritance and abstraction?
  - The key difference between the two principles lies in how abstraction focuses on the privacy of functionality, while inheritance focuses on sharing functionality (and reusability).

# Wrapper Class

- What is a wrapper class?
  - A class that encapsulates primitive data types into objects
  - Some classes and data structures can only handle objects

# Testing Private Methods

- How do you test a private method?
  - To test a private method, create an instance of that class and try to print the output of the variable or method that was private.
    - You could try to call the private method in a class that should have access and asserts that the call failed.

# Other Concepts

- What is method overloading?
- What is a constructor?
- In Java, what is an Interface?
- What is an Abstract class?

# Vending Machine Design

- What classes and methods would you use to build a vending machine, and how would you deliver this machine to a client? The objective is to see how you can take a real-world example and abstract it into Object-Oriented Programming principles.
  - [Link to solution](https://javarevisited.blogspot.com/2016/06/design-vending-machine-in-java.html#axzz7eES4C5Xg) has a solution but think of it as a template rather than gospel.
