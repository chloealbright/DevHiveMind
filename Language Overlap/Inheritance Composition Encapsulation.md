---
tags:
  - ClassStructure
---
With inheritance you just access what another class can do

Composition is when one class has a field with a reference to an object of another class and used

A closure is an example of encapsulation: it encapsulates the body of code together with the lexical scope. The only means of access into the capsule is through the function: the function is like a "method", and the elements of the captured lexical environment are like "slots" in an object.

## Inheritance

Obviously, you’ll want to use inheritance in all object-oriented languages, C++, C#, Java, Go… Wait. No, Go is a no-go, it doesn’t have any inheritance. Anyways - some languages support object-oriented paradigms fuller than others. C++ for example offers multiple inheritances. That’s right - every class can have multiple parents. Standard even says that every compiler has to support at least 1024 parents.

Quick Reminder: Inheritance extends a class with new fields and methods by creating a child from chosen class. This child has a new name, and “inherits” all properties from its parent. Think of it as embedding a parent class into its child.

Now, as programmers we often write new classes, and sometimes - it’s time to make a choice: should these two classes be related and how? There are some commonly known rules that’ll help you decide, and also some less commonly known rules. I’ll cover both, so stay with me.

### Types of Inheritance in JavaScript

Inheritance is a very wide topic in JavaScript, as there are different ways to implement it. For instance, there’s the prototypal, pseudoclassical and functional inheritance. Let’s look briefly at how these inheritance types differ and how they work with polymorphism in JavaScript.

1. Prototypal inheritance is a type of inheritance that adds new properties and methods to an existing object. This inheritance makes use of prototype objects i.e. object.prototype

```javascript
	let Car = { color: "Red", }; 
	let BMW = { make: "BMW", }; 
	BMW.__proto__ = Car; 
	// we can find both properties in BMW now: 
	console.log("This is a " + BMW.color + " " + BMW.make);
```
2. Pseudo classical Inheritance is similar to prototypal inheritance. This type of inheritance emulates classical inheritance using prototypal inheritance. However, if you’re programming with ES6, the use of pseudo classical inheritance isn’t encouraged since you can use conventional classes (the class keyword). In pseudo classical inheritance, we try to create a class with a function that is intended to be called with the new keyword. To understand this better, we’ll be using our car example. Let’s imagine we have a car object as shown in the code below:
```javascript
	function Car(make, color, speed) { 
	this.make = make; 
	this.color = color; 
	this.speed = speed; 
	}
```

We can create sub-types of different car makes objects with prototype using the new keyword:

```javascript
var Toyota = new Car ("Toyota", "Red", "100mph");
var Bentley = new Car ("Bentley", "White", "120mph");
var BMW = new Car ("BMW", "Green", "90mph");
```

3.Functional inheritance involves inheriting features with the use of an augmenting function to an object instance:

### [[Composition over Inheritance#Composition Example | Composition]]

So, two classes are definitely connected, but are they connected via inheritance or composition? (Composition is when one class has a field with a reference to an object of another class).

In this case, we’ll follow the Is-A-Has-A relationship guideline. Say that we have a few classes: Star, Color, and Shape. Star Is-A Shape, so it could be an inheritance relationship, but Star HAS-A Color, so it’s a composition. Shape is not-a Color, but maybe could have-a color if we’d be so inclined. Another very common example has a Car, Truck, and Engine classes - can you arrange these in possible hierarchies?

Okay, I’ve mentioned the basic common rules - what is that less known, more insightful reason to avoid inheritance? Gang of Four or fathers of design paradigms call inheritance a white-box reuse, that all the implementation details of the parent class are visible to the child. While composition is called black-box reuse - each class’s implementation is closed, encapsulated from another.

a composition basically describing a class reference to one or more objects of other classes in instances

By leveraging composition we also achieve two other things. One: we follow another important rule of clean code: single responsibility. If a class inherits from too many parents - most likely it no longer serves a single purpose. Two: our code complexity metric called Depth of Inheritance Tree (or DIT for short) will remain low. Too complex code is a nemesis of every programmer. Staying vigilant will help you and your colleagues get more quality sleep at night.

### Encapsulation(Private access modifier alt)

Encapsulation as we know is another key feature of OOP, and when one class inherits from another - the parent class gives up part of its encapsulation to create a child class. This has good and bad sides: it’s easier to write such a child class. However, (and this is important) things might get tricky when you’ll try to change the representation or implementation of the parent class. Because it’s so easy to depend on a parent - most child classes will.

Other issue is the permanent nature of such a relation: inheritance is forever: when you decide on a child class in compile-time, you won’t be able to change it runtime, you will have to destroy an object and create another, unlike a composition, where you can swap and switch however you like.

in JavaScript a way to create a private  variable is through encapsulation by creating a method that has a variable then you return another function that returns that other variable essentially using the scope to make it private also known as closure but you can use typescript for private variable

[https://www.youtube.com/watch?v=nnwD5Lwwqdo&list=WL&index=14&ab_channel=WebDevSimplified](https://www.youtube.com/watch?v=nnwD5Lwwqdo&list=WL&index=14&ab_channel=WebDevSimplified)