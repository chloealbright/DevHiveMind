---
tags:
  - CodebaseDecision
---
Imperative meaning the  how to achieve something sequentially step by step low level easier to trace what is going on. 

This is divided into things like Procedural, Object-oriented, and  Parallel approaches. 

-   Procedural step by step can be re-used in different parts of program but can get messy and robust with more advanced complex problems I.E Leetcode question with a lot of conditions. 
    

-   Object-oriented more organized and structured  
    

-   Parallel programming no supported in JavaScript with the help of web workers [https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers) 
    

Imperative is simple scale-able and easy to get into but can get messy also is proably used behind the scenes when defining built in declarative code that is used in languages 


Languages can also lean more towards Imperative code like 

1.  JavaScript: A popular client-side language used for creating dynamic and interactive web applications, as well as server-side with Node.js.
    
2.  PHP: A server-side language widely used for creating dynamic web pages, e-commerce sites, and web applications.
    
3.  Ruby: A high-level, dynamic, and object-oriented language that is often used for web development, automation, and data analysis.
    
4.  Swift: A programming language developed by Apple for building iOS, macOS, watchOS, and tvOS applications.
    
5.  Go: A modern and efficient language developed by Google for building scalable and concurrent systems.
    
6.  Rust: A systems programming language that combines low-level control with high-level abstractions, with a focus on safety, speed, and concurrency.
    
7.  Fortran: A high-level language designed for numerical and scientific computing, still widely used in high-performance computing and simulation.
    
8.  Ada: A language designed for safety-critical and real-time systems, with strong typing and modular design.
    
9.  Visual Basic: A language and development environment for building Windows applications, macros, and scripts.
    
10.  Objective-C: A language for developing iOS and macOS applications, popularized by Apple and now largely replaced by Swift.


## Rest Operator
*The rest parameter syntax allows a function to accept an indefinite number of arguments as an array, providing a way to represent variadic functions in JavaScript and is imperative in nature*

```javascript
function sum(...b) { 

return b  

} 

console.log(sum(1, 2, 3)); // return whole array 
```

