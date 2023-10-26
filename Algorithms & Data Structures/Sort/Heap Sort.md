![[_Images/Algo/unnamed (2).gif]]

The heap data structure is an array object that we can view as a nearly complete binary tree. Each node of the tree corresponds to an element of the array. The tree is completely filled on all levels except possibly the lowest level, which is filled from the left up to a point.  
  
The heapsort algorithm uses the heap data structure, and it starts by using "BUILD-MAX-HEAP" to build a max-heap on the input array A[1..n], where n = A.length; Since the maximum element of the array is stored at the root A[1], we can put it into its correct final position by exchanging it with A[n]. If we now discard node n from the heap- and we can do so by simply decrementing A.heap-size-we observer that the children of the root remain max-heaps, but the new root element might violate the max-heap property. All we need to do to restore the max-heap property, however, is call a function MAX-HEAPIFY-FUNCTION(A,1), which leaves a max-heap in A[1..n-1]. The heapsort repeats this process for the max-heap of size n-1 down to a heap of size 2.  
  
[https://stackabuse.com/heap-sort-in-javascript/](https://stackabuse.com/heap-sort-in-javascript/)  
  
[https://levelup.gitconnected.com/heapsort-for-javascript-newbies-598d25477d55](https://levelup.gitconnected.com/heapsort-for-javascript-newbies-598d25477d55)  
  
[https://vhudyma-blog.eu/2020-09-22-algorithms-heap-sort-in-javascript/](https://vhudyma-blog.eu/2020-09-22-algorithms-heap-sort-in-javascript/)