---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[bin.jpeg]]

A Binomial Heap is a collection of Binomial Tree where each Binomial Tree follows the Min-Heap property and there can be at most one Binomial Tree of any degree. 

The key difference between a Binary Heap and a Binomial Heap is how the heaps are structured. In a Binary Heap, the heap is a single tree, which is a complete binary tree. In a Binomial Heap, the heap is a collection of smaller trees (that is, a forest of trees), each of which is a binomial tree. A complete binary tree can be built to hold any number of elements, but the number of elements in a binomial tree of some order N is always 2*N. Consequently, one complete binary tree is needed to back a Binary Heap, but we may need multiple binomial trees to back a Binomial Heap.