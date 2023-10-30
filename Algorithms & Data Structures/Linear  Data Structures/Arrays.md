---
tags:
  - linear
author: jacgit18
Status: init
Started: 
EditDate: 
Relates:
---
![[unnamed (25).gif]]


An array is a linear data structures data that can be accessed sequentially & can be considered a special object that is a chunk of memory 

Arrays are object literals or key value pairs 

```java
ArrayList <Object> x = new ArrayList <Object>(); 
ArrayList [][] = new ArrayList();

// Typescript
let v: string = new Array(); 
let a: [][] = new Array<Array<Object>>(); 
```

### Use arrays for 

pushing(), poping(), and lookingup() data because it is O(1) most of the time and it is ordered 

### Don't use arrays for 

	inserting() or deleting() because it is O(n) 

also depending on the language the array can be a static meaning  fixed size so you will need to override it and make it dynamic which makes it O(n) or more 

## Array 

length/size is usually hardcoded depending on the language  so it doesn't dynamically increase or decrease in size so in order to resize you have to copy to new memory with a different array size which is inefficient in terms of steps  

Are very fast because of indexing especially when doing binary search and sorting 

ARRAY & STRINGS similar since they have sub-arrays & sub-strings and you can use array brackets to iterate and other string methods 

for string manipulation questions ask if it is an ASCII string or a Unicode string 
[https://www.rapidtables.com/code/text/unicode-characters.html](https://www.rapidtables.com/code/text/unicode-characters.html)  

JavaScript does not provide the multidimensional array natively. However, you can create a multidimensional array by defining an array of elements, where each element is also another array. For this reason, we can say that a JavaScript multidimensional array is an array of arrays. 

If dealing with a nested array and you don't have to visit all of the indexes you can just use one loop as opposed to nested for loop 

## Tip 

Java Arraylist versus array

Basically it's more dynamic and grows as opposed to an array has a fixed size and it's not dynamic Just use arraylist better


Use map over for each method for your array 

If you can't use reverse and limit use .sort 

When dealing with nested array/matrix questions think about work in the outer row loop in terms of adding things also you will probably use a hash table a lot in question with matrix's to keep track of elements visited which is like memoization  

Fixed length you may be dealing with a matrix or array with elements of a fixed length so it may be some form of Merge Interval where values are unsorted or sorted overall 

```javascript
[...string]. arrayMethod to manipulate and can store in array for array destructing 
```

reassigning array length to a smaller length to shrink array  

```javascript
var array = [1, 2, 3, 4, 5, 6];    length of 6 array.length = 3 array now [1,2,3] 
```

sort by length of array element 

if you have an array of string and you want to check the sub string of words in array you can use string methods or store current word in variable 

```javascript
const char = substring[right]; 

// If comparing two arrays you can depending on what your asked to do you can  

// Store array value at current index in a variable use for of which gets value with out worrying about index in this case we care about index only for sequence array  

function isValidSubsequence(array: number[], sequence: number[]) { 

let index = 0 

WHEN LOOPing Ask YourSelf IF YOU need to Mess with index 

  for(let num of array) if(num === sequence[index]) index++ 

  return index === sequence.length; 

}
```


Arrays are a special type of object.


Use arrays for pushing(), poping(), and lookingup() data because it is O(1) most of the time and it is ordered  
  
dont use arrays for inserting() or deleting() because it is O(n)  
  
also depending on the language the array can be a static meaning fixed size  
so you will need to override it and make it dynamic which makes it O(n) or more  
  
is a linear data structures data that can be accessed sequentially  
  
  
Array size is usually hardcoded so it doesn't dynamically increase or decrease in size so in order to resize you have to copy to new memory with a different array size which is inefficient in terms of steps  
  
An array is a chunk of memory
  
Inserting into an array is big o of n  
  
Are very fast because of indexing especially when doing binary search and sorting  
  
JavaScript does not provide the multidimensional array natively. However, you can create a multidimensional array by defining an array of elements, where each element is also another array. For this reason, we can say that a JavaScript multidimensional array is an array of arrays.



## Better way to check if array exist and its length 

Optional chaining and ternary 

The optional chaining operator (?.) enables you to read the value of a property located deep within a chain of connected objects without having to check that each reference in the chain is valid. 

The ?. operator is like the . chaining operator, except that instead of causing an error if a reference is nullish (null or undefined), the expression short-circuits with a return value of undefined. When used with function calls, it returns undefined if the given function does not exist. 

This results in shorter and simpler expressions when accessing chained properties when the possibility exists that a reference may be missing. It can also be helpful while exploring the content of an object when there's no known guarantee as to which properties are required. 

Optional chaining cannot be used on a non-declared root object, but can be used with an undefined root object. 

```javascript
myArray = [] 

myArray?.length ? true : false 

// check array position 

  myArrayTwo = [{"id": 1}] 

  myArrayTwo?.[0]?.id ? true : false 

// using null coalescing operator 

  myArrayTwo?.[0]?.id ?? "no property" // returns id value 

  myArrayTwo?.[0]?.name ?? "no property" // returns"no property" 

fakeArray ="[jgjgj]" 

Array.isArray(fakeArray) // returns true 

//if not sure of type 

Array.isArray(myArrayTwo) && myArrayTwo[0]?.id ? true : false 

Array.isArray(myArrayTwo) && myArrayTwo[0]?.name ? true : false
```




Array 

boundary is -1 and 1 after array length 

Do we have to increment the entire length of the array  

If dealing with a nested array and you don't have to visit all of the indexes you can just use one loop as opposed to nested for loop 

min/ max 

  // if sorted Split Array in into left-Low and Right-High after finding middle index  binary search 


```javascript
const length = array.length; 

const middle = Math.floor(length / 2) 

you can create a array of left and right based on middle  

//if array length is odd  

//  left-Low has one more value then Right-High  

const left = array.slice(0, middle)  

const right = array.slice(middle) 

// Right-High has one more value then left-Low  

const left = array.slice(0, 1 + middle ) 

const right = array.slice(middle + 1) 

or  

check if  mid < target val 

and reassign hi to be one less then mid  index (mid - 1) 

else lo equal mid index 

         [-1,0,3,5,9,12], 9) 

search (nums, target)  

       lo = 0, 

       hi = nums.length-1; 

  while (lo < hi)  

      let mid = lo + Math.floor((hi - lo + 1) / 2);  

      if target < nums[mid] 

          hi = mid - 1 // index 

       else  

          lo = mid; // index 

      return nums[lo]==target?lo:-1; 

map(key, value) > Set(rm duplicates) > stack Push, pop at end/top 

queue(rm stuff at beginning ) queue.shift 

enqueue(add stuff at beginning ) queue.unshift 

array convert to string or 2d array
```

# High level example of Array/Matrix 

-1         +1  
<mark style="background: #FF5582A6;">-1</mark> <mark style="background: #FFF3A3A6;">0 1 2 3</mark> <mark style="background: #FFB86CA6;">4</mark> 
<mark style="background: #FF5582A6;">ob</mark> 1 2 3 4 <mark style="background: #FFB86CA6;">un</mark> 
![[Pasted image 20231029104453.png]]