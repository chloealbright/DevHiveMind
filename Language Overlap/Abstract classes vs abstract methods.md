Abstract classes and abstract methods are related concepts in Java, but they serve different purposes.

Abstract classes:
- An abstract class is a class that cannot be instantiated, meaning you cannot create objects directly from it.
- It is declared using the `abstract` keyword in its class definition.
- Abstract classes can contain a mix of abstract and non-abstract methods.
- Abstract classes can have constructors and member variables.
- Abstract classes can provide default implementations for some methods.
- Subclasses of an abstract class must either implement all the abstract methods defined in the superclass or be declared as abstract themselves.
- Abstract classes are useful for creating a common base class with shared functionality that can be extended by multiple subclasses.

Abstract methods:
- An abstract method is a method declaration without an implementation.
- It is declared using the `abstract` keyword in the method signature.
- Abstract methods are defined in abstract classes or interfaces.
- Abstract methods do not have a method body and end with a semicolon.
- Subclasses that extend an abstract class or implement an interface containing abstract methods must provide their own implementation for those abstract methods.
- Abstract methods define a contract or interface that subclasses or implementing classes must adhere to.
- Abstract methods are useful when you want to enforce that certain methods must be implemented by subclasses or implementing classes.

In summary, abstract classes provide a way to define common functionality and behavior that can be shared among multiple subclasses. They can contain both abstract and non-abstract methods. Abstract methods, on the other hand, are method declarations without implementations and are used to define a contract that subclasses or implementing classes must fulfill. Abstract methods are typically defined within abstract classes or interfaces.

subclass is basically the class that is before extend or being extended from



- What is the difference between an interface and an abstract method? 

    - An abstract class permits you to make a functionality that subclasses can implement or override 

    - An interface only permits you to state functionality but not to implement it. 

    - A class can extend only one abstract class while a class can implement multiple interfaces. 

    - An **abstract** class is a class that contains the keyword **`abstract`** while an **Interface** is class with method without a body, that uses the keyword **`implement`**. 

    - Neither creates an object in java.