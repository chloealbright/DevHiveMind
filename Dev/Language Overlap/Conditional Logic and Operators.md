---
tags:
  - CodebaseDecision
---
This relates to [[Flow of Control]]
### isLooselyEqual ==

Exclude type check

Converts types & compare value


### isStrictlyEqual===

Includes type check in comparison



### Value Comparison Operators

In javascript, the <mark style="background: #BBFABBA6;">==</mark> operator does the type conversion of the operands before comparison, whereas the <mark style="background: #BBFABBA6;">===</mark> operator compares the values and the data types of the operands. The <mark style="background: #FFF3A3A6;">Object.is()</mark> method determines whether two values are the same value: <mark style="background: #FFF3A3A6;">Object.is(value1, value2)</mark>.

Object.is() is not equivalent to the <mark style="background: #BBFABBA6;">==</mark> operator. The <mark style="background: #BBFABBA6;">==</mark> operator applies various coercions to both sides (if they are not the same type) before testing for equality (resulting in such behavior as <mark style="background: #BBFABBA6;">"" ==</mark> false being true), but Object.is() doesn't coerce either value.

Object.is() is also not equivalent to the === operator. The only difference between Object.is() and === is in their treatment of signed zeros and NaN values. The === operator (and the == operator) treats the number values -0 and +0 as equal but treats NaN as not equal to each other.


## Conditional shortcuts 

```javascript
// check if value exist 

address && action like console.log  

same as if(address) console.log 

if else shortcut  

return (name || 'no name') 

Low-cost merge of arrays 

arr1 =[1,2] 

arr2 =[3,4 

arr1.push.apply(arr1,arr2) 

Default value with || 

let ogName = 'jake' 

let ogAge =null 

let name = ogName || 'fake name'  // jake 

let age = ogAge || 99 // 99

```


## Short circuit evaluation 

go left to right 

if first is true don,t visit the next check 

(variable true and method call) 

No if keyword needed 

Check the first condition if it's false we don't check the other condition 

Which is a method called that returns boolean 

Similar with or operator 

Setting a variable to itself when you pass has a function parameter or a default value just in case you don't pass a value 

```javascript
Name = Name || bob
```

### Optional Chaining Operator uses  Null Coalescing Operator ??

Check if data is in object very useful when dealing with Api  

example: 
```javascript
const person = { 

name: joe, 

age: 23 

vehicle:{ 

} 

} 

// Ternary version 

const vehicleYear = person.vehicle ?  person.vehicle.year : undefined 

//Optional Chaining Operator  version both properties not in object but if they were you would get vale of them 

const vehicleYear = person.vehicle? .year  // should be this 

const vehicleYear = person.vehicle? .year  ?? 1980 // you can set a default value if it doesnt exist 

const warrantyDate = person.vehicle? .warranty?.expireDate   

//can be used with methods to 

person.vehicle? .miles() 

person.vehicle? .miles?.() // check if it is a function
```