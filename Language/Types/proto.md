---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
3 Rules of Prototypal Inheritance 

no circular reference allowed (person.__proto__ cant be gutiarist) 

__proto__ must be object or null 

an object can only directly inherit from one object  

your at school and have a paper but no pen but you have a friend with another friend who has a pen 

you with paper > friend and his > friend with pen() 

youObj = { 

paper: "" 

} 

friendObj = { 

otherFriend: this.friendWithPen.tool 

} 

friendWithPen = { 

tool: pen() 

} 

obj.setPrototypeOf(friendWithPen, friendObj) 

youObj.paper 

youObj.otherFriend > friendWithPen.tool.pen()  

// otherFriend is a shared ref between youObj and friendObj 

youObj.__proto__ 

 // returns obj friendObj = {otherFriend: this.friendWithPen.tool } 

As we can see, behavior delegation or object delegation is the more natural way to model objects in JavaScript. It leverages the prototype lookup process to enable peered objects to delegate behavior with each other without strictly declaring class hierarchy or tightly-coupled composition, like in traditional object-oriented languages. 

this is know as prototype inheritance but isn't really inheritance more so object delegation  

function Dog () {} 

// Dog is a constructor prototype represents a new instance of dog using "new" keyword   

Dog.prototype.breed = "bulldog" // similar to new Dog() 

let myDoggie = new Dog() 

myDoggie.prototype has no prototype but Dog does which is object with breed because myDoggie is a vairable that stores an instance of new Dog() 

function cat () {} has a prototype object 

let bear = {} // no prototype undefined but has __proto__ which is global 

__proto__ is the property that on an object points out prototype that has been set for that object  

prototype is the property on a function which is only available for functions were it is set as the property if you are using new keyword