
## Interface Segregation Principle (ISP)

The interface Segregation Principle states that a client should not implement an [interface](http://javarevisited.blogspot.com/2012/04/10-points-on-interface-in-java-with.html) if it doesn’t use that.

This happens mostly when one interface contains more than one functionality, and the client only needs one feature and no other.

There is no doubt that Interface design is a tricky job because once you release your interface, you can not change it without breaking all implementation. Well, Java 8’s [default or defender method](https://javarevisited.blogspot.com/2014/07/default-defender-or-extension-method-of-Java8-example-tutorial.html#axzz5kO8vmDxy) feature does provide a way for interface evolution, but not all Programming languages support those features.

> _Another benefit of this design principle in Java is, the interface has the disadvantage of implementing all method before any class can use it so having single functionality means less method to implement._

## I — nterface Segregation Principle

==Interfaces should be specific rather than doing many and different things.==

That’s because any implementing class will only implement the specific needed interfaces rather than being forced to implement methods that it doesn’t need it.

So, large interfaces should be decomposed into smaller, more specific ones.





interface is a blueprint that can be used to implement a class. The interface does not contain any concrete methods (methods that have code). All the methods of an interface are abstract methods. 

An interface cannot be instantiated(represent as or by an instance.). However, classes that implement interfaces can be instantiated. Interfaces never contain instance variables but, they can contain public static final variables (i.e., constant class variables) 

Important Reasons For Using Interfaces 

Interfaces are used to achieve abstraction. 

Designed to support dynamic method resolution at run time 

It helps you to achieve loose coupling. 

Allows you to separate the definition of a method from the inheritance hierarchy


Use Interfaces when you know there's going to be several implementation of something

## Programming for Interface not implementation

A programmer should always _program for the interface and not for implementation; this_ will lead to flexible code, which can work with any new implementation of the interface.

In concrete words, you should use interface type on variables, return types of a method, or argument type of techniques in Java-like using `SuperClass` type to store object instead using `SubClass`.

I mean

`List numbers= getNumbers();`

instead of

`ArrayList numbers = getNumbers();`


The Interface Segregation Principle (ISP) in object-oriented design suggests that a class should not be forced to implement interfaces it does not use. Here are examples in Java, Python, and C#:

### Java:

```java
// Interface
interface Worker {
    void work();
    void eat();
}

// Violation of ISP
class SuperWorker implements Worker {
    @Override
    public void work() {
        // ... doing super work
    }

    @Override
    public void eat() {
        // ... eating in a super way
    }
}

// Adhering to ISP
interface Workable {
    void work();
}

interface Eatable {
    void eat();
}

class NormalWorker implements Workable, Eatable {
    @Override
    public void work() {
        // ... doing normal work
    }

    @Override
    public void eat() {
        // ... eating in a normal way
    }
}
```

### Python:

```python
# Interface
class Worker:
    def work(self):
        pass

    def eat(self):
        pass

# Violation of ISP
class SuperWorker(Worker):
    def work(self):
        # ... doing super work

    def eat(self):
        # ... eating in a super way

# Adhering to ISP
class Workable:
    def work(self):
        pass

class Eatable:
    def eat(self):
        pass

class NormalWorker(Workable, Eatable):
    def work(self):
        # ... doing normal work

    def eat(self):
        # ... eating in a normal way
```

### C#:

```csharp
// Interface
interface IWorker
{
    void Work();
    void Eat();
}

// Violation of ISP
class SuperWorker : IWorker
{
    public void Work()
    {
        // ... doing super work
    }

    public void Eat()
    {
        // ... eating in a super way
    }
}

// Adhering to ISP
interface IWorkable
{
    void Work();
}

interface IEatable
{
    void Eat();
}

class NormalWorker : IWorkable, IEatable
{
    public void Work()
    {
        // ... doing normal work
    }

    public void Eat()
    {
        // ... eating in a normal way
    }
}
```

In the examples adhering to the Interface Segregation Principle, I've split the original `Worker` interface into smaller interfaces (`Workable` and `Eatable`) to avoid forcing classes to implement methods they don't need. This way, classes can implement only the interfaces that are relevant to them, promoting a more modular and maintainable design.


# Java Diamond Problem

using interfaces solves this problem 

In Java, the Diamond Problem occurs in the context of multiple inheritance when a class inherits from two classes that have a common ancestor. If both parent classes have a method with the same name, and the child class doesn't override that method, it becomes ambiguous for the compiler to decide which method to call.

Here's a simple example to illustrate the Diamond Problem:

```java
class A {
    void method() {
        System.out.println("Method from class A");
    }
}

class B extends A {
}

class C extends A {
}

class D extends B, C { // This would cause a compilation error in Java
}
```

In the example above, if a class `D` tries to extend both `B` and `C`, it would result in a compilation error because Java doesn't support multiple inheritance through classes.

One way to solve the Diamond Problem in Java is by using interfaces. Here's an example:

```java
interface A {
    void method();
}

class B implements A {
    public void method() {
        System.out.println("Method from class B");
    }
}

class C implements A {
    public void method() {
        System.out.println("Method from class C");
    }
}

class D implements B, C {
    // Here, D needs to provide its own implementation of the 'method' to resolve ambiguity.
    public void method() {
        System.out.println("Method from class D");
    }
}
```

In this solution, interfaces are used instead of classes, and the class `D` implements both interfaces `B` and `C`. This way, the compiler doesn't face the ambiguity of conflicting method names, and the class `D` provides its own implementation of the method to resolve the issue.