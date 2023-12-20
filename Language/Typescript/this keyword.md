---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
In JavaScript, the this keyword is a little different compared to other languages. It refers to an object, but it depends on how or where it is being invoked. It also has some differences between strict mode and non-strict mode. 

-   In an object method, this refers to the object 
    
-   Alone, this refers to the global object 
    
-   In a function, this refers to the global object 
    
-   In a function, in strict mode, this is undefined 
    
-   In an event, this refers to the element that received the event 
    
-   Methods like call(), apply(), and bind() can refer this to any object


"this" Methods are properties of an object which are functions. The value of this inside a method is equal to the calling object. In simple words, this value is the object “before dot”, the one used to call the method.


"this" in a function 

The keyword this when used in a function refers to the global object. 

The keyword this when used alone refers to the global object. 

The keyword this when used in an event handler refers to the element that received the event. 

The keyword this when used in an arrow function refers to the parent object.






'this' keyword references the object that is executing the current function/method 

a method is function part of a object/class  

If a function is not part of object/class it references the global object in the case of a browser and node that would be window object 

const video = { 

title:'a' 

play(){ 

console.log(this)  

      } 

} 

video.play() // prints video object 

video.stop = function(){ 

console.log(this)  

} 

video.stop() // prints video object 

function not part of object/class  

function playvid(){ 

console.log(this)  

} 

playvid() // prints window object 

Function Video(title){ 

this.title = title 

console.log(this)  

} 

const v = new Video('b')// logs new empty object called Video with title 

callback anonymous function 

forEach takes two parameters 

const video = { 

title:'a', 

tag: [a, b,c ] 

showTag(){ 

// this.tags reference video object 

this.tags.forEach(function(tag){ 

console.log(this.title) // prints window not video object so cant access title 

console.log(this.title, tag)  

}, this )  

// the this changes object from window to video only specific to forEach callback 

      } 

} 

video.showTag() 

so you want to bind the function to object when it comes to situations like this 

const video = { 

title:'a', 

tag: [a, b,c ] 

showTag(){ 

this.tags.forEach(function(tag){ 

console.log(this.title) 

console.log(this.title, tag)  

}, this )  

      } 

} 

video.showTag() 

const vid = video.showTag.bind(video) // creates new instance of showTag and set this to video object 

vid()