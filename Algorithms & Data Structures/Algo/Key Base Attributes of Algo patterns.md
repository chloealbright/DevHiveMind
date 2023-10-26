---
tags:
  - MicroCodebaseDecision
author: jacgit18
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

## Two Pointer

- **Definition:** The Two Pointer pattern involves using two pointers to traverse arrays or strings.
- **Key Elements:**
  - Input array or string.
  - Left and right pointers.
- **Use Cases:**
  - Comparing values at two pointers.
  - Fast-slow pointer variations.
- **Use Sorting:** Sort the input arrays/lists if necessary before applying the Two Pointer technique.

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

## Heaps (Data Structures)

- **Insertion:**
  1. Push the initial node.
  2. Rebalance the heap.
- **Removal:** Use object pointer reassignment (Node Pointers).

## Top K Elements pattern (work in progress)

## Fast & Slow Pointers

- **Definition:** Fast & Slow Pointers help detect cycles in linked lists.
- **Steps:**
  1. Check for existence of the head.
  2. Initialize slow and fast pointers.
  3. Iterate through the list.
- **Use Cases:** Detecting cycles in linked lists.

## In-Place Reversal of Linked List Nodes

- **Steps:**
  1. Check if the head exists.
  2. Initialize current and previous pointers.
  3. Iterate through the list to reverse the nodes.
  4. Return the new head.


