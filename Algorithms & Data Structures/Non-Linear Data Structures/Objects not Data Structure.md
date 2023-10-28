---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
is non linear but not a Data Structure

An object is an instance of a class. A class can model various things from the real world. It's an abstraction of something (car, socket, map, connection, student, teacher, you name it).


An object is not a data structure on its own; it is an instance of a class in object-oriented programming (OOP). A class can be used to define a custom data structure that can be linear or nonlinear, depending on how the data is organized and accessed.  

Object is the building blocks for a data structure  
  
For example, a simple class that represents a linked list can be used to create a linear data structure, where elements are stored in a specific order and accessed sequentially. On the other hand, a class that represents a binary search tree can be used to create a nonlinear data structure, where elements are organized in a hierarchical structure and accessed using a specific search algorithm.  
  
Therefore, whether an object represents a linear or nonlinear data structure depends on how it is implemented within a class in the context of the application.


Avoid modifying objects copy them  

Can't iterate over an object with a regular for loop so either use the for loop that iterates through objects or store object in an array so you can loop with the regular for loop or while loop


while loop can iterate through objects/json & when you don't know length of what your iterating through

With nested objects like JSON it can be tree like in terms of repetitive work and going through a file directory so you can do recursion then you get into memiozation


```javascript
// object literal 

var person = {  

  firstName: "Allie",    

  lastName: "Grater",    

  age: 50                

}; 

Vs  

var person = new Object() 

person.firstName="Allie" 

person.lastName="Grater" 

person.age = 50 

The same

```



```javascript
# Switch case with dictionaries 

// switch cases with dict alt use object instead of switch case more readable 

const opt = "all"; 

const filtDic = { 

// what to default to 

// conditional logic when to break or continue 

    all: "All items", 

    cat1: "cat1 items", 

    cat2: "cat2 items", 

    cat3: "cat3 items", 

    cat4: "cat4 items" 

} 

console.log(filtDic[opt]) 

console.log(filtDic['cat4'])




# dictionary/JSONCheck 

function dictionaryCheck(dict) { 

  let results = {}; // can use array or something else 

  let currKey = ""; 

   function recTraverse(dict) { 

    Object.keys(dict).forEach(key => { 

  // array would be considered object 

      let DataVal = dict[key]; 

      let objectType = typeof(DataVal) === 'object' 

      let booleanType = typeof(DataVal) === 'boolean' 

      let stringType = typeof(DataVal) === 'string' 

    // typeof(val) === "string" ? "string" : "number" 

      if (objectType) { 

  // do something then pass current obj recursively 

        recTraverse(dict[key]); 

      } else { 

       // do other things then check next key 

      } 

    }); 

  } 

   recTraverse(dict); 

  return results; 

}





# Use destructuring/spread for simple object reassignment 

const state = { 

  a:3, 

  b:7 

} 

function changeState(state){ 

  const newObj = {}; 

  for(let key in state){ 

      newObj[key] = state[key] 

  } 

  newObj['a'] += 5; 

  return newObj; 

} 

function changeStateTwo(state){ 

 // alt 

  return {...state, a: state.a + 5}; 

} 

console.log(changeState(state)) 

console.log(changeStateTwo(state))






```





In JavaScript, objects can be created in several ways, including using object literals, constructor functions, and classes. While objects created using object literals do not have a class, objects created using constructor functions or classes are instances of their respective classes.  
  
In JavaScript, classes were introduced in ECMAScript 2015 (ES6) and provide syntactic sugar over constructor functions. When a class is defined, it is essentially a blueprint for creating objects that share the same properties and methods. Objects created using the new keyword and the class name are instances of the class.  
  
For example, consider the following code that defines a class and creates an instance of it:  
  
javascript  
Copy code  
class Person {  
constructor(name, age) {  
[this.name](http://this.name/) = name;  
this.age = age;  
}  
  
sayHello() {  
console.log(`Hello, my name is ${[this.name](http://this.name/)} and I am ${this.age} years old.`);  
}  
}  
  
const john = new Person('John', 30);  
  
  
In this example, john is an instance of the Person class, created using the new keyword and the Person class constructor function. The sayHello() method defined in the Person class is available on the john object and can be called like this: john.sayHello().



# Map

In computer science, "map" and "object" can have different meanings depending on the context and programming language being used.  
  
In general, a map is a data structure that stores a collection of key-value pairs, where each key is unique and used to retrieve the associated value. Maps are used to efficiently retrieve and manipulate data based on keys, and they are often implemented using hash tables or other similar data structures.  
  
An object, on the other hand, is a fundamental concept in object-oriented programming (OOP) that represents an instance of a class. Objects are typically used to represent real-world entities or concepts and contain data (in the form of instance variables) and behavior (in the form of methods).  
  
In some programming languages, objects can be used to implement maps or key-value pairs, where the object's instance variables represent the values associated with the keys. In this case, the object is acting as a map or dictionary.  
  
So, while there can be some overlap between the concepts of maps and objects, they are not necessarily the same thing. The use of these terms depends on the specific programming language and context in which they are being used.



"Map" is a general term that can refer to any data structure that allows for the mapping of keys to values. Depending on the implementation, a map may or may not be considered a linear data structure.  
  
For example, in some programming languages, a "map" data structure is a synonym for a "dictionary" or "hash map," which are implemented using a hash table and are therefore not considered linear data structures.  
  
In other cases, a map might be implemented using an ordered data structure, such as a balanced binary search tree, which would make it a non-linear data structure. In this case, the keys would be stored in a specific order to allow for efficient search and traversal.  
  
So, whether a map is considered a linear data structure or not depends on the implementation details of the specific map in question.

