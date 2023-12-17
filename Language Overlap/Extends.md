---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Extends: In Java, the extends keyword is used to indicate that the class which is being defined is derived from the base class using inheritance. So basically, extends keyword is used to extend the functionality of the parent class to the subclass. In Java, multiple inheritances are not allowed due to ambiguity. Therefore, a class can extend only one class to avoid ambiguity. 

```java
class One { 

    public void methodOne() { 

        // Some Functionality 

    } 

} 

class Two extends One { 

    public static void main(String args[]){ 

        Two t = new Two(); 

        // Calls the method one 

        // of the above class 

        t.methodOne(); 

    } 

}
```