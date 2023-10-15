## Flashcard
#modifiers
which access modifier allows code visible to all classes;; public  
What access modifier is limited to classes;; private  
what modifier is limited to package;; protected  
where can protected classes be accessed;; package and subclass
Which access modifier has more scope private or protected;; protected  
UML sign for access [[Protected]] modifier;; hashtag  
UML sign for access private modifier;; minus  
UML sign for access public modifier;; plus  
UML sign for mandatory;; asterisk  
UML sign for optional;; O
UML sign for static member for attributes and methods;; underline or bold and underline

## Modifiers 
***access modifiers for attributes, classes, methods, and constructors (member):

- **no-modifier** -  this default to what is known as "*package-private*" making it visible only within its packages (named groups of related classes). 

### UML Class Signs

^7de0bf

 ```java
 * Mandidtory
 O Optional
```


-  **public** - code is visible to all classes everywhere. 
```java
+ public
```

-  **private** - members can only be accessed in their class. 
```java
- private
```

-  **[[Protected]]** - member can only be accessed within its package and by a subclass of its class in another package used a lot with UUID.
```java
# protected
```

> Your access modifier strategy should use the most restrictive access level that makes sense for the specific member.  Also, avoid public fields except for constants.


## Non-Access Modifiers 

**These are the non-access modifiers for classes: 

-   Abstract - class cannot be used to create objects. 
-   Final - class cannot be inherited by other classes. 

**These are the non-access modifiers for attributes and methods: 

-  Abstract - only be used in an abstract class and can only be used on methods. 

- final - both cannot be overridden or modified. 
  
-  [[Static methods | static ]]- both belong to the class and not the object. also in uml is represented by being underlined and a little bold. static members are used so, there will be one and only one copy of the member.
 
-  transient - both are skipped when serializing the object containing them. 
 
-  synchronized - methods can only be accessed by one thread at a time. 

-  Volatile - the value of an attribute is read from main memory and not cached thread-locally.









