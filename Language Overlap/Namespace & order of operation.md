---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Namespace refers to the programming paradigm of providing scope to the identifiers (names of types, functions, variables, etc) to prevent collisions between them. For instance, the same variable name might be required in a program in different contexts. Using namespaces in such a scenario will isolate these contexts such that the same identifier can be used in different namespaces. In this article, we will discuss how namespaces can be initialized and used in JavaScript. JavaScript does not provide namespace by default. However, we can replicate this functionality by making a global object which can contain all functions and variables. 

You only can go up a scope chain  

The highest scope chain is the global which can only access itself 

The next is outer scope the outer scope is like a parent function it has access to itself and the global 

 and the inner scope is the lowest scope and can access the outer scope and global scope 

for(var i = 0; i < 5; i++){ 

  console.log(i) = 4 

} 

console.log(i) = 5 // will run since were are function scoped 

for(let j = 0; j < 5; j++){ 

  console.log(j) = 4 

} 

console.log(j) = 5 // wont run because were blocked scoped 

const is also blocked scoped 

order of operation 

------------------- 

console.log(typeof 1) is number 

console.log(typeof (typeof 1)) is string