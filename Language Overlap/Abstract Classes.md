An abstract class is a fundamental concept in object-oriented programming that cannot be instantiated; you cannot create objects directly from it. Its primary purpose is to serve as a blueprint for other classes by defining common attributes and methods shared among its subclasses. In contrast, a concrete class is one that can be instantiated, allowing the creation of objects.

# Structural model
![[2023-06-17 12.38.06 medium.com 7a1fbbfaa1b5.png]]


Abstract classes typically feature the abstract keyword in their declaration and should contain at least one abstract method, i.e., a method without a body. They can also have multiple concrete methods. The inheriting classes are obliged to implement the abstract methods, ensuring a consistent structure across subclasses.

The key reasons for using abstract classes include:

1. Offering default functionality for subclasses.
2. Providing a template for future specific classes.
3. Defining a common interface for its subclasses.
4. Facilitating code reusability.

In the context of Java, abstraction is the process of presenting only essential information to a user. This abstraction can be achieved using abstract classes or interfaces. The keyword "abstract" is used for classes and methods. Abstract classes cannot be used to create objects; access is only granted through inheritance. Abstract methods, which lack a method body, can only be used in abstract classes. These abstract classes can contain a combination of abstract and regular methods.
