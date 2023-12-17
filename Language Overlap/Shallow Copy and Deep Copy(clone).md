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
https://medium.com/@manjuladube/understanding-deep-and-shallow-copy-in-javascript-13438bad941c  

Shallow copy is a bit-wise copy of an object. A new object is created that has an exact copy of the values in the original object. If any of the fields of the object are references to other objects, just the reference addresses are copied i.e., only the memory address is copied. 

let xArray = [1,2,3] 

let yArray = xArray // stores memory ref  

so if push to yArray both arrays will be pushed to  

let zArray = [...yArray , 10] // will be [1,2,3,10] 

yArray would stay  [1,2,3] 

// with object.assign(target, source) 

const tArray = Object .assign( [ ], zArray) // yArray would stay  [1,2,3,10] 

tArray === zArray // returns false different memory ref 

// if they are nested they still share ref 

let Jray = [1,2,3] 

Jray.push([4,5,6]) // [1,2,3,[4,5,6] ]  

let vArray = [...Jray] // [1,2,3,[4,5,6] ]  

vArray[4].push(7)   

Jray // has same length after pushing 7 

vArray // has same length after pushing 7 

// Array from and slice create shallow copies 

// This Allows to mutate things when you shouldn't with object freeze 

const obj = { 

"first": 44, 

"sec": 12, 

"third": {"a": 1, "b": 2} 

} 

// shallow freeze 

Object.freeze(obj) 

obj.third.a = 8 // changes a to 8 

The Object.freeze() method freezes an object. A frozen object can no longer be changed; freezing an object prevents new properties from being added to it, existing properties from being removed, prevents changing the enumerability, configurability, or writability of existing properties, and prevents the values of existing properties from being changed. In addition, freezing an object also prevents its prototype from being changed. freeze() returns the same object that was passed in. 

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