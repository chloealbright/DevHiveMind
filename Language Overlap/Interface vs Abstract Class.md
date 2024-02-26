---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
An abstract class permits you to make functionality that subclasses can implement or override whereas an interface only permits you to state functionality but not to implement it. A class can extend only one abstract class while a class can implement multiple interfaces.  
  
Abstract class is Abstract & concrete methods,  
An abstract class defines the identity of a class.  
classes can inherit only one Abstract Class, can be overridden  
abstract Class can have an access modifier.  
the class can have data fields.  
An abstract class allows you to define both fields and constants  
An abstract class can inherit a class and multiple interfaces.  
An abstract class can declare constructors and destructors.  
An abstract class has protected and public abstract methods.  
  
should be used To avoid independence, should be used when various implementations of the same kind share a common behavior.  
  
Interface  
Implement several Interfaces  
Abstract methods  
the interface cannot contain data fields.  
An interface is abstract so that it can’t provide any code.  
use for Future enhancement  
It is better to use interface when various implementations share only method signature. Polymorphic hierarchy of value types.  
  
Interfaces help to define the peripheral abilities of a class.  
No fields can be defined  
An interface can inherit multiple interfaces but cannot inherit a class.  
An interface cannot declare constructors or destructors.  
An interface can have only public abstract methods.  
  
While adding new stuff to the interface, it is a nightmare to find all the implementors and implement newly defined stuff.  
  
The interface does not have access modifiers. Everything defined inside the interface is assumed public modifier.  
  
  
  
```java
interface Pet {  
public void test();  
}  
class Dog implements Pet {  
public void test() {  
System.out.println("Interface Method Implemented");  
}  
public static void main(String args[]) {  
Pet p = new Dog();  
p.test();  
}  
}  
  
  

abstract class Shape {  
int b = 20;  
abstract public void calculateArea();  
}  
  
public class Rectangle extends Shape {  
public static void main(String args[]) {  
Rectangle obj = new Rectangle();  
obj.b = 200;  
obj.calculateArea();  
}  
public void calculateArea() {  
System.out.println("Area is " + (b * b));  
}  
}
```