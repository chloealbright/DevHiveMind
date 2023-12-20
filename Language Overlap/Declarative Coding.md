---
tags:
  - CodebaseDecision
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---

Declarative meaning "what should be done at a high level with focus on the logic and concepts and the end result in mind ex: "a table for two" no steps included  

This is divided into things like Functional, Logic, and Data Driven programing. 

-  Functional program is mathematical based and is centered around pure functions which are typically tiny, composable functions and uses recursion and can be hard to scale but still have some benefits many benefits. 
    
    -  Functional programming language typically uses stored data, frequently avoiding loops in favor of recursive functions.The functional programing’s  primary focus is on the return values of functions, and side effects and different suggests that storing state are powerfully discouraged. For example, in an exceedingly pure useful language, if a function is termed, it’s expected that the function not modify or perform any o/p. It may, however, build algorithmic calls and alter the parameters of these calls. Functional languages are usually easier and build it easier to figure on abstract issues, however, they’ll even be “further from the machine” therein their programming model makes it difficult to know precisely, but the code is decoded into machine language (which are often problematic for system programming). 
        
    
-   Logic not used a lot except for research [https://towardsdatascience.com/logic-programming-rethinking-the-way-we-program-8706b2adc3f1](https://towardsdatascience.com/logic-programming-rethinking-the-way-we-program-8706b2adc3f1) 
    
-   Data Driven Development centered around database Schema. 
    

Declarative is complex but good for math and data problems and is hard to scale

Languages can also be Declarative, these are languages that specify what the program should accomplish, rather than how it should accomplish it. Examples include SQL and Prolog.

Other Declarative Languages

1.  XSLT (Extensible Stylesheet Language Transformations): A declarative language used for transforming XML documents into other formats, such as HTML, PDF, or plain text.
    
2.  CSS (Cascading Style Sheets): A declarative language used for describing the presentation of HTML or XML documents, such as fonts, colors, layout, and positioning.
    
3.  Datalog: A declarative logic programming language used for querying and reasoning about databases and knowledge bases.
    
4.  YAML (YAML Ain't Markup Language): A declarative language used for describing data structures and configurations in a human-readable and machine-friendly format.
    
5.  GraphQL (Graph Query Language): A declarative language used for describing and querying data in a GraphQL API, specifying the data requirements and structure in a single request.

*JavaScript use operators between the two operators the spread falls under Declarative coding*
## Spread Operator 
```javascript
const numbers = [1, 2, 3]; 

console.log(...numbers); // return whole array 

let numbersOne = {prop1: 1, prop2: "val2"} 

let numbersTwo = {...numbersOne, prop3: "val3"} 

console.log(numbersTwo);
```