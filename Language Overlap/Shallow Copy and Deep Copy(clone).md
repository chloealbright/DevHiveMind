---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[Shallow and Deep Copy.gif]]




Deep copy solves this 

A deep copy copies all fields, and makes copies of dynamically allocated memory pointed to by the fields. A deep copy occurs when an object is copied along with the objects to which it refers. 

// several libraries  like lodash, ramda and others has this built-in 

const Score = { 

"first": 44, 

"sec": 12, 

"third": {"a": 1, "b": 2} 

} 

// One liner 

const newScore = JSON.parse(JSON.stringify(Score))  

Score === newScore // ref different memory so false which we want 

// this doesn't works with Dates, function, undefined, Infinity, RegExps, Maps, 

Sets, Blobs, FileLists, ImageDates, and other complex data types 

// better way 

const deepClone = (obj) =>{ 

if (typeof obj !== "object" || obj === null) return obj 

// create array or object to hold values 

const newObj = Array.isArray(obj) ? [] : {} 

for(let key in obj){ 

const value = obj[key] 

// recursive call for nested objects & arrays 

newObj[key] = deepClone(value) 

} 

return newObj 

} 

testArray = [44,22] 

const newA = deepClone(testArray) 

testArray === newA //false good 

testObj  = { 

"first": 44, 

"sec": 12, 

"third": {"a": 1, "b": 2} 

} 

const objay = deepClone(testObj) 

objay === testObj //false good 

// if you have a function with shallow copy that makes it impure deep copy fixes that 

const pure =(array, score=87, deepClone) =>{ 

const newArray = deepClone(array) 

newArray.push(score) 

return newArray 

} 

const impure =(array, score=87) =>{ 

array.push(score) 

return newArray 

} 

shallow shares ref so since object, arrays, and other data structures are mutable if one OBJ/DS  gets a new value push or added, the other array like in the examples will be mutated the same