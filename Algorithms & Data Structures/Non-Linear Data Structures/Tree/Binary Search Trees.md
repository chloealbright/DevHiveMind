---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (50).gif]]

## Pros

Inserting and deleting

Speed of Access

Maintains sorted order; retrieval of elements is in order.

Flexible size

## Cons
Some overhead because of their creation and management.

Like I could become unbalanced and basically be a long live list which can cause things to become O(n) and there is no O(1) operations




In Binary search tree all nodes to the right starting from the root must be greater than the last node and all nodes to the left must be lesser than the node before it

Don't focus too much on remove function for binary search trees probably not on interview very complex

In production we probably won't be using a binary search tree will be using AVL or red-black tree since they self balance


## Binary Search on Arrays

Binary search is often presented as a search method for sorted arrays. This does not contradict the description above. In fact, it highlights the fact that we don't actually care how a binary search tree is implemented; we just care that we can take an object and do three things with it: get a element, get a left sub-object, and get a right sub-object (subject, of course, to the constraints about the elements in the left being less than the element, and the elements in the right being greater, etc.).

We can do all three things with a sorted array. With a sorted array, the "element" is the middle element of the array, the left sub-object is the subarray to the left of it, and the right sub-object is the subarray to the right of it. E.g., the array

As often presented, binary search refers to the array-based algorithm presented here, and binary search tree refers to a tree-based data structure with certain properties. However, the properties that binary search requires and the properties that binary search trees have to make these two sides of the same coin. Being a binary search tree often implies a particular implementation, but really it's a matter of providing certain operations and satisfying certain constraints. Binary search is an algorithm that functions on data structures that have these operations and meet these constraints.