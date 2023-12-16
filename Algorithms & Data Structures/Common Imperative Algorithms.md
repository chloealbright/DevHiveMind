---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
### [[Imperative Coding]] Example

```javascript
function LengthCheck(inputArray) {
  let result = false;

  if (inputArray && inputArray.length) {
    const trimmedArray = inputArray.trim().split(" ");
    const lastElement = trimmedArray.pop();
    const lastElementLength = lastElement.trim().length;

    result = Boolean(lastElementLength);
  }

  return result;
}

// Example usage
let myArray = "  some text   ";
console.log(checkAltLength(myArray)); // Outputs: true
```


```javascript
const deepClone = (obj) => {
  if (typeof obj !== "object" || obj === null) return obj;
  const newObj = Array.isArray(obj) ? [] : {};
  for (let key in obj) {
    const value = obj[key];
    newObj[key] = deepClone(value);
  }
  return newObj;
};
```


```Javascript
const removeDuplicates = (nums) => { 
    const unique = new Set(nums); 

    if(unique.size === nums.length) return false; // only false if no duplicates exist 
    
    return true; 
} 

let theNum = [1, 2, 3, 1]; 
console.log(containsDuplicate(theNum))
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
