In Java, it is possible to define a class within another class, such classes are known as nested classes. They enable you to logically group classes that are only used in one place, thus this increases the use of encapsulation, and creates more readable and maintainable code.

The scope of a nested class is bounded by the scope of its enclosing class. Thus in below example, class NestedClass does not exist independently of class OuterClass.

A nested class has access to the members, including private members, of the class in which it is nested. But the enclosing class does not have access to the members of the nested class.

A nested class is also a member of its enclosing class.

As a member of its enclosing class, a nested class can be declared private, public, protected, or package private(default).

Nested classes are divided into two categories:

static nested class : Nested classes that are declared static are called static nested classes.

inner class : An inner class is a non-static nested class.

```java
class OuterClass  
{  
...  
    class NestedClass  
    {  
        ...  
    }  
}
```

![[classes.png]]

In the case of normal or regular inner classes, without an outer class object existing, there cannot be an inner class object. i.e., an object of the inner class is always strongly associated with an outer class object. But in the case of static nested class, Without an outer class object existing, there may be a static nested class object. i.e., an object of a static nested class is not strongly associated with the outer class object.As with class methods and variables, a static nested class is associated with its outer class. And like static class methods, a static nested class cannot refer directly to instance variables or methods defined in its enclosing class: it can use them only through an object reference.They are accessed using the enclosing class name.

[https://www.geeksforgeeks.org/local-inner-class-java/](https://www.geeksforgeeks.org/local-inner-class-java/)

[https://www.geeksforgeeks.org/anonymous-inner-class-java/](https://www.geeksforgeeks.org/anonymous-inner-class-java/)



Type of packages 

These are the types of packages: 

-   Built-in - are a part of the Java API and are free to use. 
    
-   User-defined - created by the developer. 
    

To use a package in a class, use the keyword import and the package name with dot notation. 

Java Inner Classes 

[Java Inner classes](https://docs.oracle.com/javase/tutorial/java/javaOO/nested.html) (nested classes) allow developers to define a class within another.  Java Inner classes are a way to group classes only used in one place, increase encapsulation and lead to more readable and maintainable code. 

Java Enums 

[Java Enums](https://docs.oracle.com/javase/tutorial/java/javaOO/enum.html) represent a group of constants.  Use the keyword enum and separate the constants with commas.  Enum constants are in uppercase letters. 

Java User Input 

Java User Input is captured using the [Scanner](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Scanner.html) class.  Scanner can parse primitive types and strings.  It breaks down the input into tokens using a delimiter pattern.




Each java file needs at least one class and cant have multiple classes  

Yes, we can have multiple classes in same java file. But, there is one restriction over here, which is that you can have as many classes in one file but only one public class is allowed. If we try to declare 2 classes as public in the same file, the code will not compile. 

The reason being is you need to name the file with the name of the class which is declared as public and we cannot have the same file with different names, and also that public class should be containing the main method as the compiler will check for the main method first. So, there is no chance to have two public classes in one file. 

If we want to access the methods, instances of the other classes we can just make their respective objects in the public file and simply access them. 



public class test{ 

public static void main(String...s){ 

System.out.println("Hello Guys"); 

} 

} 

class test1{} 

class test2{}