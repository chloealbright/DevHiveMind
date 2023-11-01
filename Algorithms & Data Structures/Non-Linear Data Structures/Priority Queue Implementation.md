---
tags:
  - non-linear
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---


Priority queue can be implemented using an array, a linked list, a heap data structure, or a binary search tree. Among these data structures, heap data structure provides an efficient implementation of priority queues. 

So why is Binary Heap Preferred for Priority Queue? 

Since Binary Heap is implemented using arrays, there is always better locality of reference and operations are more cache friendly. 

Although operations are of same time complexity, constants in Binary Search Tree are higher. 

We can build a Binary Heap in O(n) time. Self-Balancing BSTs require O(nLogn) time to construct. 

Binary Heap doesn’t require extra space for pointers. 

Binary Heap is easier to implement. 

There are variations of Binary Heap like Fibonacci Heap that can support insert and decrease-key in Θ(1) time 

Is Binary Heap always better? 

Although Binary Heap is for Priority Queue, BSTs have their own advantages and the list of advantages is in-fact bigger compared to binary heap. 

Searching an element in self-balancing BST is O(Logn) which is O(n) in Binary Heap. 

We can print all elements of BST in sorted order in O(n) time, but Binary Heap requires O(nLogn) time. 

Floor and ceil can be found in O(Logn) time. 

K’th largest/smallest element be found in O(Logn) time by augmenting tree with an additional field.





The time complexity of operations in a priority queue depends on its implementation.

If the priority queue is implemented as a heap data structure, then the time complexity of inserting an element into the priority queue is O(log n), where n is the number of elements in the priority queue. The time complexity of removing the element with the highest priority is also O(log n).

Therefore, a priority queue implemented as a heap is not considered linear, since the time complexity of the operations grows logarithmically with the size of the queue.

However, there are other implementations of priority queues that can have linear time complexity. For example, a priority queue implemented as a sorted array or a sorted linked list would have a time complexity of O(n) for both insertion and removal of elements.

In summary, a priority queue implemented as a heap is not linear, but there are other implementations of priority queues that can be linear.