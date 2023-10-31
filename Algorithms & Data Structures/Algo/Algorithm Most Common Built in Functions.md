---
tags:
  - MicroCodebaseDecision
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
## Common Math 

**Link common built-in methods to other code

```javascript
Math.abs(-1) = 1 

Math.ceil(5.95)  always rounds a number up to the next largest integer. = 6 

Math.floor(5.95)  returns the largest integer less than or equal to a given number. = 5 

Math.round(1.5) = 2 > 1.4 > 1 

Math.cbrt(5) = returns base of the exponent passed which is 1.709975946676697 and exponent is always 3 so 1.709975946676697^3 = 5 always returns odd also happens to be a decimal if bigger it would return whole number 

Math.sqrt(2) = 1.4142135623730951 // exponent 2 base is what the power 2 gives us 2 which always even no matter what number given 

Math.pow(2,3) = 2^3 = 8 

Math.max(value0...valueN) = max value 

let min = Infinity                                                                                               

Math.min(min...valueN) = min value  
```

## Common [[Primitive Types]]

### Number 
```javascript
123.456.toFixed() = 123                                                123.456.toFixed(1) = 123.5 automatically rounds 

Number.parseFloat('4.567abcdefgh') = 4.567          
Number.parseInt('4.567abcdefgh') = 4 

// rm special characters 
let text = "A(B){C};:a.b*!c??!1<>2@#3"                     let newSring = text.replace(/[\d\W_]+/g,"");
// \d get rid of nums 
let reg = newSring.replace(/\d/g, "")  
```


[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseInt) 

### String 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) 
```javascript
charCodeAt(a) = 97 

charCodeAt(Num) to fromCharCode(Letter) 

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
```
### String Regex 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) 

[https://regexlearn.com/cheatsheet](https://regexlearn.com/cheatsheet) 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) 
```javascript
String.match(regexp) or .matchAll(regexp) 

String.split() .split(separator) .split(separator, limit) 

let name = "Alphonse Gabriel Capone";                                                                 

let nameArray = name.split(' ') 

const spltNames ={ 

     firstName:  nameArray[0], 

     middleName: nameArray[1], 

     lastName: nameArray[2] 

} 

    console.log (spltNames) 

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
```javascript
Array.entries() returns a new Array Iterator object that contains the key/value pairs for each index in the array. 

Array.fill(value) (value, start) (value, start, end) start & end Optional 

Array.flat(depth) depth is optional 

Array.includes(searchElement, fromIndex(Optional))        

Array.join(separator(Optional)) 

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

```javascript
(element, index, array) =>  Arrow function                                                                       

(callbackFn, thisArg) Callback function                                   

(function(element, index, array) { /* ... */ }, thisArg) Inline callback  

Array.every() test if every element in array pass a condition and returns a Boolean value. 

Array.filter() test if every element in array pass a condition return new array with the elements that pass the test or empty array if failed 

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

 < 0        sort a before b:  a(1) - b(2) = -1 lower value placed first                                                                                                         

> 0        sort b before a:  b(2) - a(1)  = 1 higher value placed first                          

=== 0        keep original order of a and b 
```
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) 

## Object iterate using for In loop 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects) 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) 

Map(uses has()):                                                                   
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) 

Set(uses has()):                                                                        
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)




