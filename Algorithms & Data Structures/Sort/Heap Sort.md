---
tags:
  - sortAlgo
author:
  - jacgit18
Status: init
Started: 
EditDate: 
Relates:
---
![[_Images/Algo/unnamed (2).gif]]


The heapsort algorithm utilizes the heap data structure. Here's a refined summary of the process:

1. **Building the Max-Heap**: Start with an input array A[1..n], where n = A.length. Create a max-heap by using the "BUILD-MAX-HEAP" operation.

2. **Exchanging Maximum Element**: The maximum element is at the root (A[1]). Move it to its final position by exchanging it with A[n].

3. **Restoring Max-Heap Property**: Discard node n from the heap (decrement A.heap-size). The children of the root remain max-heaps, but the new root might not. To restore the max-heap property, use the "MAX-HEAPIFY" function on A[1..n-1].

4. **Repeat**: Repeat the process for max-heaps of decreasing size from n-1 down to a heap of size 2.

For more details and implementation, you can refer to the resources you provided:

- [Stack Abuse](https://stackabuse.com/heap-sort-in-javascript/)
- [GitConnected](https://levelup.gitconnected.com/heapsort-for-javascript-newbies-598d25477d55)
- [Vhudyma's Blog](https://vhudyma-blog.eu/2020-09-22-algorithms-heap-sort-in-javascript/)