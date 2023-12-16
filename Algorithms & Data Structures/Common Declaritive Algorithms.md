---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
### [[Declarative Coding]] Example

**Array Map Method:** is apart of array wrapper class don't confuse it with map data structure.

```javascript
const LengthCheck = (inputArray) => {
  return Boolean(
    inputArray?.length &&
    inputArray
      .trim()
      .split(" ")
      .pop()
      .trim()
      .length
  );
};

// Example usage
let myArray = "  some text   ";
console.log(altLengthCheck(myArray)); // Outputs: true
```


```javascript
const deepClone = (obj) => {
  if (typeof obj !== "object" || obj === null) return obj;

  return Array.isArray(obj)
    ? obj.map(deepClone)
    : Object.fromEntries(Object.entries(obj).map(([key, value]) => [key, deepClone(value)]));
};
```


```javascript
const removeDuplicates = (nums) => {
  return Array.from(new Set(nums));
};

let theNum = [1, 2, 3, 1];
let uniqueNums = removeDuplicates(theNum);
console.log(uniqueNums);
```




```javascript
// Odd Even Check
const result = (number % 2 === 0)
  ? Math.sqrt(num)
  : Math.cbrt(num).toFixed(3);

// Circumference function
function circumference(r) {
  if (Number.isNaN(Number.parseFloat(r))) {
    return 0;
  }
  return parseFloat(r);
}
console.log(circumference('4.567abcdefgh')); // prints 4.567
```

```javascript
// Count Characters
const charCounter = (characterString) => {
  let maxRepeat = 0;
  let minRepeat = Infinity;
  let letterFreq = {}, uniqueChars = 0;

  for (let currChar of characterString) {
    if (!letterFreq[currChar]) {
      uniqueChars++;
      letterFreq[currChar] = 1;
    } else {
      letterFreq[currChar]++;
    }
    maxRepeat = Math.max(maxRepeat, letterFreq[currChar]);
    minRepeat = Math.min(minRepeat, letterFreq[currChar]);
  }

  return ['Letter Count: ', letterFreq, `UniqCharacter: ${uniqueChars}, MinRepeatCharacters: ${minRepeat}, MaxRepeatCharacters: ${maxRepeat}`];
};
console.log(charCounter('cbaebabacd'));


Letter Count:  { c: 2, b: 3, a: 3, e: 1, d: 1 }                                                              

UniqCharacter: 5, MinRepeatCharacters: 1  

MaxRepeatCharacters: 3 
```

```javascript
// Range
const between = (x, min, max) => {
  return x >= min && x <= max;
};

const x = 0.002;
if (between(x, 0.001, 0.009)) {
  // do something
}
```

```javascript
// Filter By Number
function filterByNumber(obj) {
  if (typeof (obj) === null) return true;
  else return false;
}
const number = [1, null, 3, 4, 5, "null", 9];
number.filter(filterByNumber).map((x) => x);
```

```javascript
// Generate Array
let AlphaBet = Array(26).fill(0);

const Row = 9, Col = 9;
const val = 0;
const boardNestedArray = Array.from(Array(Row), () => Array(Col).fill(val));

let arr = [
  [0, 1, 1, 1, 1, 1, 1, 1, 1],
  [1, 1, 1, 1, 1, 1, 1, 1, 1],
  [2, 1, 1, 1, 1, 1, 1, 1, 1],
  [3, 1, 1, 1, 1, 1, 1, 1, 1],
  [4, 1, 1, 1, 1, 1, 1, 1, 1],
  [5, 1, 1, 1, 1, 1, 1, 1, 1],
  [6, 1, 1, 1, 1, 1, 1, 1, 1],
  [7, 1, 1, 1, 1, 1, 1, 1, 1],
  [8, 1, 1, 1, 1, 1, 1, 1, 1]
];

[1, 2, 3, 4, 6, 7, 3, undefined];
```
-1 (Out of bounds), 0, 1, 2, 3, 4, 5, 6, 7 (doesn't exist) need to push

**Note:**
You can't just access the column since you would be accessing indexes from multiple arrays. Access both row & column using `matrix[currRow].length` or `curCol >= matrix.length`.

```javascript
// String.ToCharArray() equivalent in JavaScript
"012345"
  .split('') // Splits into chars, returning ["0", "1", "2", "3", "4", "5"]
  .join(',') // Joins each char with a comma, returning "0,1,2,3,4,5"

// Generate Array
var arr = Array.from(Array(10).keys()); // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```