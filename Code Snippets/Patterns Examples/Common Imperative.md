### [[Imperative Coding]] Example

```Javascript
Permutations 

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





Reverse/ Dequeue Array 

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




reverse string 

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







remove duplicates 

let theNum = [1, 2, 3, 1]; 

// Example 2: 

// Input: nums = [1,2,3,4] 

// Output: false 

// Example 3: 

// Input: nums = [1,1,1,3,3,4,3,2,4,2] 

// Output: true 

// 0(1) 

const containsDuplicate = (nums) => { 

    const unique = new Set(nums); 

    if(unique.size === nums.length) return false; // only false if no duplicates exist 

    return true; 

} 

console.log(containsDuplicate(theNum))





lc39 knapsack 

var combinationSum = function(candidates, target) { 

  var result = [] 

  if(!candidates || !target || target < 1 || candidates.length == 0){return [[]]} 

  else if(candidates.length == 1){ 

      if(target < candidates[0]){return []} 

      else if(target % candidates[0] === 0){ 

          let div = target/candidates[0] 

          return [[...Array(div)].fill(candidates[0])] 

  } 

  combinationSumRecursive(candidates, target, [], candidates.length, result) 

  return result 

}; 

var combinationSumRecursive = function (A, target, temp, n, result){ 

  if (target === 0){ 

      result.push([...temp]) 

      return 

  } 

  if(n === 0){ return} 

  if(A[n-1] > target){ 

      return combinationSumRecursive(A, target,temp, n-1, result) 

  } 

  temp.push(A[n-1]) 

  combinationSumRecursive(A, target-A[n-1], temp, n, result) 

  temp.pop() 

  combinationSumRecursive(A, target, temp, n-1, result) 

} 

console.log(combinationSum([2,3,5], 8))






Merge interval 

class Interval { 

  constructor(start, end) { 

    this.start = start; 

    this.end = end; 

  } 

} 

const merge = (firstList, secondList) =>{ 

  const result = []; 

  let [intervalOneIdx ,intervalTwoIdx] =[ 0, 0]; 

WHILE 

(intervalOneIdx < firstList.length && intervalTwoIdx < secondList.length){ 

      const [firstIntStart, firstIntEnd] = firstList[intervalOneIdx]; 

      const [secondIntStart, secondIntEnd] = secondList[intervalTwoIdx]; 

let firstCompare = 

(firstIntStart >= secondIntStart && firstIntStart <= secondIntEnd); 

 let secondCompare = 

 (secondIntStart >= firstIntStart && secondIntStart <= firstIntEnd); 

// if first list's ith and second list's jth intervals intersect, add the intersection to the result 

      if( firstCompare || secondCompare ) { 

result.push([ 

Math.max(firstIntStart,  secondIntStart), 

Math.min(firstIntEnd, secondIntEnd)] 

); 

      } 

  // if first interval is ended before second interval, move to the next interval of the first list 

      if(firstIntEnd < secondIntEnd) { 

          ++intervalOneIdx; 

      } else { 

// if the second interval is ended before the first interval, move to the next interval of the second list 

          ++intervalTwoIdx; 

      } 

  } 

  return result; 

  }; // end loop 

let firstList= [[0,2],[5,10],[13,23],[24,25]]; 

// let firstList= [new Interval(0, 2), new Interval(5, 10), new Interval(13, 23), new Interval(13, 23)]; 

let secondList = [[1,5],[8,12],[15,24],[25,26]]; 

// let secondList= [new Interval(1, 5), new Interval(8, 12), new Interval(15, 24), new Interval(25, 26)]; 

console.log(merge(firstList, secondList));








Merge sort find middle left right 

const numbers = [99, 44, 6, 2, 1, 5, 63, 87, 283]; 

function mergeSort (array) { 

  if (array.length === 1) { 

    return array 

  } 

  // Split Array in into right and left 

  const length = array.length; 

  const middle = Math.floor(length / 2) 

  const left = array.slice(0, middle) 

  // const left = array.slice(0, 1 + middle ) gets one more then right 

  const right = array.slice(middle) 

  // const right = array.slice(middle + 1) 

  console.log('left:', left); 

  console.log('right:', right); 

  return merge( 

    mergeSort(left), 

    mergeSort(right) 

  ) 

} 

function merge(left, right){ 

  const result = []; 

  let leftIndex = 0; 

  let rightIndex = 0; 

  while(leftIndex < left.length && 

        rightIndex < right.length){ 

     if(left[leftIndex] < right[rightIndex]){ 

       result.push(left[leftIndex]); 

       leftIndex++; 

     } else{ 

       result.push(right[rightIndex]); 

       rightIndex++ 

    } 

  } 

  // console.log(left, right) 

  return result.concat(left.slice(leftIndex)).concat(right.slice(rightIndex)); 

}







Binary iterative & Binary recursive code  

(trees and graphs are kind of binary by nature so non linear) 

Array 

const searchIter = (nums, target) =>{ 

    let lo = 0; 

    let hi = nums.length-1; 

    while (lo < hi) { 

        let mid = lo + Math.floor((hi - lo + 1) / 2); // right/lower midupper 

        if (target < nums[mid]) { 

            hi = mid - 1 // index 

        } else { 

            lo = mid; // index 

        } 

    } 

    return nums[lo]==target?lo:-1; 

}; 

const searchRec = (nums, target) =>{ 

    return findTarget(nums, target, 0, nums.length - 1); 

}; 

const findTarget = (nums, target, start, end) =>{ 

    if (start > end) { 

        return - 1; 

    } 

    const mid = Math.floor((end - start) / 2) + start; 

    if (nums[mid] == target) { 

        return mid; 

    } else if (nums[mid] > target) { 

        return findTarget(nums, target, 0, mid - 1); 

    } else { 

        return findTarget(nums, target, mid + 1, end); 

    } 

} 

console.log(searchRec([-1,0,3,5,9,12], 9,)); // output index were 9 is  so 4 

console.log(searchRec([-1,0,3,5,9,12], 2,));




```