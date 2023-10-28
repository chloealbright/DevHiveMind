---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Object is similar to Map—both let you set keys to values, retrieve those values, delete keys, and detect whether something is stored at a key. For this reason (and because there were no built-in alternatives), Object has been used as Map historically. 

**Accidental Keys  

A Map does not contain any keys by default. It only contains what is explicitly put into it. 

An Object has a prototype, so it contains default keys that could collide with your own keys if you're not careful. 

**Key Types  

A Map's keys can be any value (including functions, objects, or any primitive).  

The keys of an Object must be either a String or a Symbol. 

**Key Order 

The keys in Map are ordered in a simple, straightforward way: A Map object iterates entries, keys, and values in the order of entry insertion. 

Although the keys of an ordinary Object are ordered now, this was not always the case, and the order is complex. As a result, it's best not to rely on property order. 

**Size 

The number of items in a Map is easily retrieved from its size property.  

The number of items in an Object must be determined manually. 

**Iteration 

A Map is an iterable, so it can be directly iterated. 


Object does not implement an iteration protocol, and so objects are not directly iterable using the JavaScript for...of statement (by default). 

An object can implement the iteration protocol, or you can get an iterable for an object using Object.keys or Object.entries. 

The for...in statement allows you to iterate over the enumerable properties of an object. 



**Performance  

Performs better in scenarios involving frequent additions and removals of key-value pairs. 

Not optimized for frequent additions and removals of key-value pairs. 

**Serialization and parsing  

No native support for serialization or parsing. 

(But you can build your own serialization and parsing support for Map by using JSON.stringify() with its replacer argument, and by using JSON.parse() with its reviver argument. 

Native support for serialization from Object to JSON, using JSON.stringify(). 

Native support for parsing from JSON to Object, using JSON.parse().