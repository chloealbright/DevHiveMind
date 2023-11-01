---
tags:
  - MicroCodebaseDecision
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
> [!note] The pattern names are just visual abstraction of the pattern
## Sliding Window

- **Definition:** Sliding Window is a pattern for efficiently processing arrays or strings by maintaining a "window" of elements.
- **Key Elements:**
  - Input array or string.
  - WindowStart and WindowEnd.
	  -  You may check if it is greater than diff between WindowEnd to WindowStart  + 1 
  - Window size conditions to increments and decrements or both.
  - Iteration by array length.
  - Target sum  
- **Potential Problem Goals**
	- You may also leverage min and max other Math methods depending on what you're doing 
	- You may return something like length, minLength, maxLength in terms of window size 
- **Use Cases:**
  - Contiguous sub-arrays or sublists.
  - Finding the smallest, longest, or other subarray.
- **Hints:** 
	- Look for keywords like "contiguous," "subarray," and "sublist."
	- Typically we use all of the elements within the sliding window for the problem like too combine things or do some type of action within window range 

Two pointer and Sliding window can be interchangeable solution but one would just be more efficient then the other depending on the what the problem solution demands typically pointer is used for comparison while window is used for other action like adding or doing some other action with the elements in the range of the window but not specifically comparison
## Two Pointer

- **Definition:** The Two Pointer pattern involves using two pointers to traverse arrays or strings.
- **Commonalities & Common things to Leverage**
	- Similar attributes to Sliding window 
	- Math methods like min, max, etc...
- **Common Sub Steps:**
	- Iterate through array with while loop with condition of while left is less then right pointer 
	- Maybe swap values 
- **Key Elements:**
  - Input array or string.
  - Left and right pointers.
- **Use Cases:**
  - Comparing values at two pointers.
  - Fast-slow pointer variations.
  - Very useful when dealing with cyclic Linked Lists or Arrays. 
 > [!important]  Used to compare the values at the two pointers instead of all the elements between the pointers. 
- **Use Sorting:** Sort the input arrays/lists if necessary before applying the Two Pointer technique. 

>[!note] Two pointer can be applied to two arrays or strings or a combination of a string and a array or used to find numbers in a range just like Sliding window  


## Fast & Slow Pointers

- **Definition:** Fast & Slow Pointers help detect cycles in linked lists.
- **Steps:**
  1. Check if head exist `fastPointer or fastPointer.next exist return false `
  2. check if `slowPointer equal fastPointer or slowPointer equal fastPointer.next  return true `
  3. Initialize slow and fast pointers.
	  - Create/Store linked list HEAD in slowPointer variable 
	  - Create/Store linked list HEAD in fastPointer variable 
  4. Iterate through the list.
  5. Update `slowPointer `to `slowPointer.next `
  6. Update `fastPointer` to `fastPointer.next.next `
- **Use Cases:** Detecting cycles in linked lists.


## Cyclic Sort

- **Definition:** Cyclic Sort is used to find missing, duplicate, or specific values in an array.
- **Steps:**
  1. Initialize an index.
  2. Find the current and decremented subarrays.
  3. Swap elements as needed.
  4. Increment the index.
- **Use Cases:** Sorting-related problems.

## Merge Intervals

- **Definition:** Merge Intervals involves merging overlapping intervals in an array of pairs.
- **Key Elements:**
  - Input matrix of pairs.
  - Sorting intervals if necessary.
  - Comparing and merging intervals.
- **Use Cases:** Merging overlapping intervals.

## Subsets/Backtracking

- **Definition:** Subsets/Backtracking is used to generate all unique paths in a matrix.
- **Steps:**
  1. Recursive traversal.
  2. Out-of-bounds, visited, and target conditions.
  3. Mark coordinates as visited.
- **Use Cases:** Generating unique paths in a matrix.

## Modified Binary Search

- **Definition:** Modified Binary Search involves searching for a target element in an array.
- **Steps:**
  1. Define low and high.
  2. Iterate while low < high.
  3. Update low or high as needed.
- **Use Cases:** Searching for elements in sorted arrays.

## Bitwise XOR (to be explored further)
- 

## Heaps (Data Structures)

- **Insertion:**
  1. Push the initial node.
  2. Rebalance the heap.
- **Removal:** Use object pointer reassignment (Node Pointers).

## Top K Elements pattern (work in progress)
- 



## In-Place Reversal of Linked List Nodes

**Steps:**
```javascript
Check head length or value or exist 

Create/Store linked list in CURRENT variable 

Create/Store  null in PREVIOUS variable 

Iterate while current not equal to  null 

Create/Store  current.next in NEXT variable 

Update current.next to previous 

Update previous to current 

Update current to next 

return previous 
```

Printing backward specifically recursively goes all the way to null  if you have print after recursive call when you hit last call you print then go back up the call stack and continue console. which are after recursive call

