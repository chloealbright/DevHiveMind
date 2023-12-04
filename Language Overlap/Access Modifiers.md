---
tags:
  - accessModifier
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---

## Flashcard
#modifiers
which access modifier allows code visible to all classes;; public  
What access modifier is limited to classes;; private  
what modifier is limited to package;; protected  
where can protected classes be accessed;; package and subclass
Which access modifier has more scope private or protected;; protected  
UML sign for access [[Protected in Depth]] modifier;; hashtag  
UML sign for access private modifier;; minus  
UML sign for access public modifier;; plus  
UML sign for mandatory;; asterisk  
UML sign for optional;; O
UML sign for static member for attributes and methods;; underline or bold and underline

## Modifiers 
 Access modifiers are keywords in certain languages that help to restrict the scope of ***attributes, classes, methods,and constructors (member):

- **no-modifier** - this is `default` to what is known as "*package-private*" making it visible only within its packages (named groups of related classes). 


## Class Diagram 
#todo/Med/Dev 
- [ ] *This can repurposed for function diagram which would increase number of tables also do this in obsidian you can also have big boxes to represent folders/modules
![[Class Diagram.png]]
### UML Class Signs

^7de0bf

 ```java
 * Mandidtory  
 O Optional
```
>[!note] Example 
> "astrick sign" function-name
> 0 function-name

-  **public** - code is accessible from everywhere in the program and from outside classes. 
```java
+ public
```

### Private
- The `private` access modifier serves the essential purpose of restricting access to class members, which includes both variables and methods within the same class where they are defined. When a member is declared as `private`, it can only be accessed and modified within the class in which it is defined. This encapsulation effectively hides these members from other classes and objects. 

- Private members play a crucial role in upholding the principle of encapsulation by concealing the internal implementation details of a class. This not only helps in maintaining data integrity but also prevents direct manipulation of the class's internal state by external code, thereby enhancing the overall robustness and security of the program or system.
```java
- private
```

-  **[[Protected in Depth | Protected]]** - member can only be accessed within its package and by a subclass of its class in another package used a lot with UUID.
```java
# protected
```

>[!note] Side Note
>Your access modifier strategy should use the most restrictive access level that makes sense for the specific member.  Also, avoid public fields except for constants.


## Non-Access Modifiers 

**These are the non-access modifiers for classes: 

-   Abstract - class cannot be used to create objects. 
-   Final - class cannot be inherited by other classes. 

**These are the non-access modifiers for attributes and methods: 

- Abstract - only be used in an abstract class and can only be used on methods. 

- Final - both cannot be overridden or modified. 
  
-  [[Static methods | static ]]- both belong to the class and not the object. also in uml is represented by being underlined and a little bold. static members are used so, there will be one and only one copy of the member.
 
-  transient - both are skipped when serializing the object containing them. 
 
-  synchronized - methods can only be accessed by one thread at a time. 

-  Volatile - the value of an attribute is read from main memory and not cached thread-locally.









