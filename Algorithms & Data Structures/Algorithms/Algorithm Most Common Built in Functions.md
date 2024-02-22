---
tags:
  - MicroCodebaseDecision
author:
  - jacgit18
Status: 
Started: 
EditDate: 2024-02-19
Relates:
---
## Common Math 

### Absolute value
```javascript
Math.abs(-1) = 1 
```
### Rounding Numbers
```javascript
Math.ceil(5.95) = 6 // Up
Math.floor(5.95) = 5 // Down
Math.round(5.95) = 6 // Closest 
```

### Power
```javascript
Math.pow(2,3) = 2^3 = 8 
```

### Square Root 
returns base of the exponent passed 
```javascript
Math.sqrt(25) = 5 
```

### Cube Root 
returns base of the exponent passed 
```javascript
Math.cbrt(64) = 4^3 = 4 
```
### Max
```javascript
Math.max(value0...valueN) = max value 
```

### Min
```javascript
let min = Infinity                        
Math.min(min...valueN) = min value  
```

## Common [[Primitive Types]]

### Numbers

#### Number Decimal place
```javascript
123.456.toFixed() = 123           
123.456.toFixed(1) = 123.5 automatically rounds 
```

#### Number From String
```javascript
Number.parseFloat('4.567abcdefgh') = 4.567          
Number.parseInt('4.567abcdefgh') = 4 
```

#### Check if Number
```javascript
Number.isNaN('4.567abcdefgh') = false          
```


### String 
#### Character to Ascii Code
```javascript
'ab'.charCodeAt(1) = 98
'ab'.charCodeAt() = 97 // default to zero
```


#### Ascii Code to 
```javascript
'ab'.charCodeAt(1) = 98
'ab'.charCodeAt() = 97 // default to zero
```


#### Ends With
```javascript
const str1 = 'Cats are the best!';


str1.endsWith('best!') // Expected output: true
str1.endsWith('best', 17)// Expected output: true
// best starts at index 13 but spelling is completed at index 17 or end of string

// 'best' appears at or before the 17th

const str2 = 'Is this a question?';
str2.endsWith('question');// Expected output: false

```

#### Split
```javascript
let name = "Alphonse Gabriel Capone";

.split() 
.split(separator) 
.split(separator, limit) 

let nameArray = name.split(' ') 
["Alphonse", "Gabriel", "Capone"]

const spltNames ={ 
     firstName:  nameArray[0], 
     middleName: nameArray[1], 
     lastName: nameArray[2] 
} 
```


```javascript

const alpha = Array.from(Array(26)).map((e, i) => i + 65); 

const alphabet = alpha.map((x) =>{ String.fromCharCode(x)); 

String.includes(searchString, position(OPITIONAL) )  
// or  
String.indexOf(searchString, position(OPITIONAL) ) 
//or  
lastIndexOf() 

const str = 'searchString, or not to be, that is the question.'   
str.includes('searchString', 0))// true but false if 1 was passed array also has a includes 

' Hello world! '.trim() = "Hello world!" or trimEnd() or trimStart() 

String.slice(beginIndex, endIndex(OPITIONAL) ) 

toLowerCase() or toUpperCase() 


// rm special characters 
let text = "A(B){C};:a.b*!c??!1<>2@#3"                     let newSring = text.replace(/[\d\W_]+/g,"");
// \d get rid of nums 
let reg = newSring.replace(/\d/g, "")  

```

The difference between `""` and `" "` lies in the content of the string.  
  
- `""` represents an empty string with zero characters.  
- `" "` represents a string containing a single space character.  
  
So, `""` is an empty string, while `" "` is a string with a space character in it.

#### String Regex 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) 

[https://regexlearn.com/cheatsheet](https://regexlearn.com/cheatsheet) 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) 

String.match(regexp) or .matchAll(regexp) 

```javascript

String.search(regexp) 

String .replace(regexp, newSubstr) .replaceAll       String .replace(regexp,replacerFunction)  .replaceAll                                              String .replace(substr, newSubstr) .replaceAll        String .replace(substr, replacerFunction) .replaceAll
```
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace) 

```javascript
RegExp.prototype.test()  executes a search for a match between a regular expression and a specified string returns true or false 

const str = 'table football';   
const regex = new RegExp('foo*');                                                           
const globalRegex = new RegExp('foo*', 'g');                           
regex.test(str) 

RegExp.prototype.exec(string)              
const regex1 = RegExp('foo*', 'g');        

const str1 = 'table football, foosball';         
regex1.exec(str1)

```
The string against which to match the regular expression. If the match succeeds, the exec() method returns an array or null if fail 

## Common Array/Object Types 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) 


### Array to String 
```javascript
Array.join(optionalSeparator) 
```


```javascript
Array.entries() returns a new Array Iterator object that contains the key/value pairs for each index in the array. 

Array.fill(value) (value, start) (value, start, end) start & end Optional 

Array.flat(depth) depth is optional 

Array.includes(searchElement, fromIndex(Optional))        



Array.reverse() 

shift()  // removes the first element or 
unshift()  // adds one or more elements to the beginning of an array 

slice(start, end) start & end Optional returns a shallow copy of a portion of an array ```
## Optional                                           

 ```javascript   
                                         splice(start)                                                                                          
splice(start, deleteCount)                                                                      

splice(start, deleteCount, item1)                                                      

splice(start, deleteCount, item1, item2, itemN)                              

items are elements to add to the array, beginning from start. 

Array.toString() method returns a string representing the specified array  

```

### Callback function supports these params thisArg is Optional                                                                

#### Array Filter
This method empowers you to assess if each element in an array meets a specific condition, yielding a new array with the elements that fulfill the test or an empty array if the condition isn't met.
```javascript
const words = ["apple", "banana", "grape", "kiwi"];
const shortWords = words.filter(word => word.length < 6);
// Result: shortWords = ["apple", "grape", "kiwi"]
```





```javascript
(element, index, array) =>  Arrow function                                                                       

(callbackFn, thisArg) Callback function                                   

(function(element, index, array) { /* ... */ }, thisArg) Inline callback  

Array.every() test if every element in array pass a condition and returns a Boolean value. 



Array.find() or findIndex() returns the first element/index in the provided array that satisfies the provided testing function If no values satisfy the testing function, undefined/-1 is returned. 

Array.map() method creates a new array populated with the results of calling a provided function on every element in the calling array like multiplying each element by 2 in the array. 

Array.some() method tests whether at least one element in the array passes the test implemented by the provided function. It returns true if, in the array, it finds an element for which the provided function returns true; otherwise it returns false. It doesn't modify the array. 
```

## More advanced callback function 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flatMap](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flatMap) 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from) 
```javascript
Array.sort() 

.sort(a,b) .sort(compareFunc) .sort(inlineCompFunc)

< 0       sort a before b:  a(1) - b(2) = -1 lower value placed first                        
 
> 0       sort b before a:  b(2) - a(1)  = 1 higher value placed first       

=== 0     keep original order of a and b 
```

- `< 0`: When the comparison function returns a value less than zero (e.g., a negative number), it indicates that element `a` should be sorted before element `b`. In other words, element `a` will come before element `b` in the sorted array.

- `> 0`: When the comparison function returns a value greater than zero (e.g., a positive number), it means that element `b` should be sorted before element `a`. This results in element `b` appearing before element `a` in the sorted array.



[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) 

## Object iterate using for In loop 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects) 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) 

Map(uses has()):                                                                   
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) 

Set(uses has()):                                                                        
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)




