---
tags: 
author:
  - jacgit18
Status: refinement
Started: 
EditDate: 
Relates: "[[Coupling vs Cohesion]]"
---
## Best to Worst 

Data coupling: When one function passes data to another function that may be used for calculation. Although this is quite common, the passed data must have the same interpretation across the two functions. 

**Control coupling**: When one function controls the flow of another function. 

**External**: When communicating with an external system. 

**Common coupling**: Is when two classes access the same shared data (e.g., a global variable). 

**Content coupling**: Is when one class modifies the content of another class. For example, in C++, friend classes can access each other’s private members. However, the benefit of friend classes is that they can increase the performance of a large-scale program by removing one layer of interaction. 

## Others 

**Routine call coupling**: When one function calls another function without passing any data as arguments. Almost every program has a function that is calling another function(s), which is why it is impossible to completely remove coupling. 

**Type-use coupling**: When a data member of class B is of class A type. 

**Stamp coupling**: When the signature of one of Class B's functions has class A as its argument or return type. 

**Import coupling**: When a library is imported for use inside a program. For example, when include and import statements are used in #Ctt and #Java, respectively.

C++ = Ctt