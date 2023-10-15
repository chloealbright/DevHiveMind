![[unnamed (59).gif]]
with BFS/DFS examples


Binary iterative & Binary recursive code 

Binary starts from The Middle and modifying that middle based on the low on the high or left on the right of the array and you can focus on a particular value on the high end or the low end  

This ends up rendering the math min and max to be not needed in the case 

Binary Search(divide and conquer): Search a sorted array by repeatedly dividing the search interval in half. Begin with an interval covering the whole array. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise narrow it to the upper half. Repeatedly check until the value is found or the interval is empty. Binary is good for large data set. 

Binary search is used when data is sorted while the data can be unsorted or sorted for linear search depending if you are applying it to a index or elements of a array  

Binary search is limited as it can be implemented only on those data structures that have two-way traversal. 

BINARY O(log N) 
```javascript
var search = function(nums, target) { 

    let lo = 0, hi = nums.length-1; 

    while (lo < hi) { 

        let mid = lo + Math.floor((hi-lo+1)/2); 

        if (target < nums[mid]) { 

            hi = mid - 1 

        } else { 

            lo = mid;  

        } 

    } 

    return nums[lo]==target?lo:-1; 

}; 




Array 

const searchIter = (nums, target) =>{ 

    let lo = 0; 

    let hi = nums.length-1; 

    while (lo < hi) { 

// right/lower mid-upper  

        let mid = lo + Math.floor((hi - lo + 1) / 2);  

        if (target < nums[mid]) { 

            hi = mid - 1 // index 

        } else { 

            lo = mid; // index 

        } 

    } 

    return nums[lo]==target?lo:-1; 

}; 





Array Rec
const searchRec = (nums, target) =>{ 

    return findTarget(nums, target, 0, nums.length - 1); 

}; 

const findTarget = (nums, target, start, end) =>{ 

    if (start > end) { 

        return - 1; 

    } 

    const mid = Math.floor((end - start) / 2) + start; 

    if (nums[mid] == target) { 

        return mid; 

    } else if (nums[mid] > target) { 

        return findTarget(nums, target, 0, mid - 1); 

    } else { 

        return findTarget(nums, target, mid + 1, end); 

    } 

} 

console.log(searchRec([-1,0,3,5,9,12], 9,));  

// output index were 9 is  so 4 

console.log(searchRec([-1,0,3,5,9,12], 2,));


```