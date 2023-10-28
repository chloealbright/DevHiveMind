---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[fib.png]]

Like Binomial Heap, Fibonacci Heap is a collection of trees with Min-Heap or Max-Heap property. In Fibonacci Heap, trees can have any shape even all trees can be single nodes (This is unlike Binomial Heap where every tree has to be a Binomial Tree). Fibonacci Heap maintains a pointer to a minimum value (which is the root of a tree). All tree roots are connected using a circular doubly linked list, so all of them can be accessed using a single ‘min’ pointer.