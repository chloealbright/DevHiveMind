---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[Linear(Sequential) v Binary search.gif]]

## Linear/Sequential Search:

^d39416

Linear search involves going through each element of an array or data structure one by one, starting from the beginning. This method checks each element sequentially to `find the desired value`.

In essence, linear search is a specific application of [[Linear Iteration vs Linear Recursion  vs Binary Iteration vs Binary Recursion| linear iteration ]]  where the goal is to find a particular value. However, linear iteration can involve various types of processing, not just searching. Linear search is a common use case for linear iteration, but it's not the only use case.

**Use Cases:**
- Linear search can be applied to any linear data structure, such as an array or a linked list, and is not limited by data order.

**Differences:**
- Linear search is a straightforward sequential approach, examining each element or node exactly once.

**Performance:**
- Linear search is suitable for small data sets.

```javascript
// Linear Search O(N)
function indexEqualsValueSearch(arr) {
    let low = 0;
    let high = arr.length;
    let mid = arr.length / 2;
    let min = Infinity;

    for (let start = 0; start < high; ++start) {
        if (arr[start] === start) {
            min = Math.min(min, arr[start]);
        }
    }

    return min === Infinity ? -1 : min;
    // Check current index and value to see if they match and find the lowest matching value
}
```
## Binary Search:
Binary search, on the other hand, operates by dividing the search interval in half repeatedly. It begins with an interval covering the whole array or sorted data structure. If the value being sought is less than the item in the middle of the interval, the search narrows down to the lower half. If the value is greater, it narrows down to the upper half. This process continues until the value is found or the interval becomes empty. Binary search is highly efficient but requires the data to be sorted.

```javascript
// Binary Search O(log N)
var search = function (nums, target) {
    let lo = 0, hi = nums.length - 1;
    while (lo < hi) {
        let mid = lo + Math.floor((hi - lo + 1) / 2);
        if (target < nums[mid]) {
            hi = mid - 1;
        } else {
            lo = mid;
        }
    }
    return nums[lo] == target ? lo : -1;
};
```

**Use Cases:**
- Binary search is ideal when dealing with sorted data, as it efficiently narrows down the search space.
- Binary search is limited as it can be implemented only on those data structures that have two-way traversal. 

**Differences:**
- Binary search is based on the "divide and conquer" approach, where it repeatedly divides the search space in half.

**Performance:**
- Binary search excels with larger data sets due to its efficient nature.

## Search Types:
A linear search involves iterating through a data structure in a linear manner, examining each element or node once. This search method is not dependent on the shape or structure of the data. If you skip elements or do not examine them all, it is a different type of search. In contrast, binary search is specifically designed for sorted data structures.



