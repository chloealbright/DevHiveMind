An abstract class is a class that can’t be instantiated; can’t create objects from it. It exists only for being inherited.

It exists to provide a generic class, that has some common attributes, and methods shared across all inherited classes, and you will never instantiate an object from that class. On the other side, a **concrete** class can be instantiated.


![[Object-Oriented Analysis And Design#Abstract]]


typically bad practice in JavaScript 

A class which has the abstract keyword in its declaration is called abstract class. Abstract classes should have at least one abstract method. , i.e., methods without a body. It can have multiple concrete methods. 

Abstract classes allow you to create blueprints for concrete classes. But the inheriting class should implement the abstract method. 

Abstract classes cannot be instantiated. 

Important Reasons For Using Abstract Class 

Abstract classes offer default functionality for the subclasses. 

Provides a template for future specific classes 

Helps you to define a common interface for its subclasses 

Abstract class allows code reusability. 

## Java

Abstraction is the process of showing only essential information to a user. Abstraction can be done with abstract classes or interfaces.  Use the keyword abstract for classes and methods.  An abstract class cannot be used to create objects, and access only comes by inheritance, and an abstract method can only be used in an abstract class and doesn’t have a body because it is inherited. Abstract classes can contain abstract and regular methods.