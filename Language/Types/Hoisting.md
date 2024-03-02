---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
when and how code is declared and/or initialized



JavaScript Hoisting refers to the process whereby the interpreter appears to move the declaration of functions, variables or classes to the top of their scope, prior to execution of the code. 

Hoisting allows functions to be safely used in code before they are declared. 

Variable and class declarations are also hoisted, so they too can be referenced before they are declared. Note that doing so can lead to unexpected errors, and is not generally recommended. 

catName("Tiger"); 

function catName(name) { 

  console.log("My cat's name is " + name); 

} 

/* 

The result of the code above is: "My cat's name is Tiger" 

*/ 

function catName(name) { 

  console.log("My cat's name is " + name); 

} 

catName("Tiger"); 

/* 

The result of the code above is the same: "My cat's name is Tiger" 

*/ 

// Works still local not global 

function catName() { 

mame ="mark" 

Var name; 

  console.log("My cat's name is " + name); 

} 

catName(); 

Variable hoisting 

Hoisting works with variables too, so you can use a variable in code before it is declared and/or initialized. 

However JavaScript only hoists declarations, not initializations! This means that initialization doesn't happen until the associated line of code is executed, even if the variable was originally initialized then declared, or declared and initialized in the same line. 

Until that point in the execution is reached the variable has its default initialization (undefined for a variable declared using var, otherwise uninitialized). 

console.log(num); // Returns 'undefined' from hoisted var declaration (not 6) 

var num; // Declaration 

num = 6; // Initialization 

console.log(num); // Returns 6 after the line with initialization is executed. 

The same thing happens if we declare and initialize the variable in the same line. 

console.log(num); // Returns 'undefined' from hoisted var declaration (not 6) 

var num = 6; // Initialization and declaration. 

console.log(num); // Returns 6 after the line with initialization is executed. 

If we forget the declaration altogether (and only initialize the value) the variable isn't hoisted. Trying to read the variable before it is initialized results in ReferenceError exception. 

console.log(num); // Throws ReferenceError exception - the interpreter doesn't know about `num`. 

num = 6; // Initialization 

Note however that initialization also causes declaration (if not already declared). The code snippet below will work, because even though it isn't hoisted, the variable is initialized and effectively declared before it is used. 

a = 'Cran'; // Initialize a 

b = 'berry'; // Initialize b 

console.log(a + "" + b); // 'Cranberry' 

Variables declared with let and const are also hoisted but, unlike var, are not initialized with a default value. An exception will be thrown if a variable declared with let or const is read before it is initialized. 

console.log(num); // Throws ReferenceError exception as the variable value is uninitialized 

let num = 6; // Initialization 

Note that it is the order in which code is executed that matters, not the order in which it is written in the source file. The code will succeed provided the line that initializes the variable is executed before any line that reads it. 

Classes defined using a class declaration are hoisted, which means that JavaScript has a reference to the class. However the class is not initialized by default, so any code that uses it before the line in which it is initialized is executed will throw a ReferenceError. 

Function and class expression hoisting 

Function expressions and class expressions are not hoisted. 

The expressions evaluate to a function or class (respectively), which are typically assigned to a variable. In this case the variable declaration is hoisted and the expression is its initialization. Therefore the expressions are not evaluated until the relevant line is executed.





Hoisting more specific 

Functions create new execution context 

It has two phasess compile and execution 

The compiled phase plays role in hoisting 

By creating a space and memory for your functions 

So since it's in memory before you compile that is why if you create a variable without 

A variable type declaration and declare it after with the same name it runs without any issues 

Hoisting does not work when you assign things to variables I can't method name equals method brackets arrow function 

Then the execution phase occurs 

Or other functions where you store a function in a variable because hosting works differently in that context depending if you're using  var const let 

Like even if you have a function with a VAR variable storing it it won't work because it's still a assignment and get skipped because it's not in memory like a function would be






