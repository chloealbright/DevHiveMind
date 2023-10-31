---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (21).gif]]

Linear search goes one by one starting from the beginning of an array  
  
Binary starts from The Middle and modifying that middle based on the low on the high or left on the right of the array and you can focus on a particular value on the high end or the low end  
  
This ends up rendering the math min and max to be not needed in the case  
  
Binary Search: Search a sorted array by repeatedly dividing the search interval in half. Begin with an interval covering the whole array. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise narrow it to the upper half. Repeatedly check until the value is found or the interval is empty.  
  
  
Binary search is used when data is sorted while the data can be unsorted or sorted for linear search depending if you are applying it to a index or elements of a array  
  
Linear can be applied to any linear data structure such as an array, linked list, etc.  
  
Binary search is limited as it can be implemented only on those data structures that have two-way traversal.  
  
Linear is based on the sequential approach. Binary is based on the divide and conquer approach.  

  
linear is good for small data sets and binary for large data set  


a search is considered linear if you iterate through a data structure in a linear manner, meaning you examine each element or node in the structure exactly once. It's not related to the shape or structure of the data itself. If you're iterating through a non-linear data structure in a way that examines each element once, it's still a linear search. If you skip elements or don't examine them all, it could be a different type of search, like a binary search for a sorted data structure.

  
LINEAR O(N)  
function indexEqualsValueSearch(arr) {  
let low = 0  
let high = arr.length  
let mid = arr.length / 2;  
let min = Infinity;  
  
for(let start = 0; start < high; ++start ) {  
  
if(arr[start] === start){  
min = Math.min(min, arr[start] )  
  
}  
  
  
}  
  
return min === Infinity ? -1 : min  
  
// check current index and value to see if they match and find lowest match min  
  
}  
  
BINARY O(log N)  
var search = function(nums, target) {  
let lo = 0, hi = nums.length-1;  
while (lo < hi) {  
let mid = lo + Math.floor((hi-lo+1)/2);  
if (target < nums[mid]) {  
hi = mid - 1  
} else {  
lo = mid;  
}  
}  
return nums[lo]==target?lo:-1;  
};