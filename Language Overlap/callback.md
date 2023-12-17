---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
  
when passing callbacks in the context of using third-party library that require you passing a call back function something in the library can change like maybe it takes another parameter that you didn't put in initially or maybe it doesn't use the call back anymore whatever the case is when using callbacks it can create a black box affect why you don't know what's going on in a particular library when you are passing in that call back  
  
This can end up breaking an app where part of its functionality when things like this happen that is why you sometimes have to debug or log what's going on when you are using functionality for me another library to verify it's not an issue with your actual code but with the library itself like in the case where Morgan was giving off weird HTTP error  
  
known as a inversion of control  
  
  
But promises tend to help with these issue

## higher Order & callback Function 

()=> (dispatch)=> 

A higher order function is a function that takes a function as an argument, or returns a function. Higher order function is in contrast to first order functions, which don’t take a function as an argument or return a function as output. 

Earlier we saw examples of .map() and .filter(). Both of them take a function as an argument. They're both higher order functions 

A callback function is a function that is passed to another function as an argument with the expectation that the other function will  call it inside the outer function to complete some kind of routine or action. 

So a callback is not necessarily itself a higher-order function, but a function which receives a callback as an argument is. Consider a very common case, the DOM event listener: 

when passing a function as a parameter avoid  

get(arr, calc())  //you are passing but also calling function 

get(arr, calc)// this way is passing referencing the function 

function greeting(name) { 

  alert('Hello ' + name); 

  } 

function processUserInput(callback) { 

  var name = prompt('Please enter your name.'); 

    callback(name); 

    } 

processUserInput(greeting);