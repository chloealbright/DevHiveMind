---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
### [[Imperative Coding]] Example

```Javascript
// Permutations 

let findPermutations = (string) => { 

  if (!string || typeof string !== "string"){ 

    return "Please enter a string" 

  } else if (string.length < 2 ){ 

    return string 

  } 

  let permutationsArray = [] 

  for (let i = 0; i < string.length; i++){ 

    let char = string[i] 

    if (string.indexOf(char) != i) 

    continue 

    let remainingChars = string.slice(0, i) + string.slice(i + 1, string.length) 

    for (let permutation of findPermutations(remainingChars)){ 

      permutationsArray.push(char + permutation) } 

  } 

  return permutationsArray 

}

```


```Javascript
// Reverse/ Dequeue Array 

const dequeue = (arr) => { 

  const length = arr.length; 

  let result = []; 

  let space = '  '; 

  let indexStartOfWord; 

  for (let i = 0; i < length; i++) { 

    result.push(arr.pop()); 

  } 

  return result; 

} 

['hello', 'world', 'have'] 

['have', 'world', 'hello']



```

```Javascript
// reverse string 

function reverseNoClosureJustRec (str) { 

  if (str === "") { 

      return ""; 

  } else { 

      return reverseNoClosureJustRec(str.substr(1)) + str.charAt(0); 

  } 

} 

    // We are using closure here so that we don't add the above variables to the global scope. 

function reverseRecursiveWay(str) { 

    let arrayStr = str.split(""); 

    let reversedArray = []; 

    function addToArray(array) { 

      if(array.length > 0) { 

        reversedArray.push(array.pop()); 

        addToArray(array); 

      } 

      return; 

    } 

    addToArray(arrayStr); 

    return reversedArray.join(""); 

  } 

function reverseIterative(str){ 

  if(!str || typeof str != 'string' || str.length < 2 ) return str; 

  let backwards = []; 

  let totalItems = str.length - 1; 

  for(let i = totalItems; i >= 0; i--){ 

    backwards.push(str[i]);// this is the same result as str.split() 

  } 

  return backwards.join(''); 

}
```

```Javascript
let theNum = [1, 2, 3, 1]; 

const RemoveDuplicates = (nums) => { 

    const unique = new Set(nums); 

    if(unique.size === nums.length) return false; // only false if no duplicates exist 

    return true; 

} 

console.log(containsDuplicate(theNum))

```