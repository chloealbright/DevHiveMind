---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (51).gif]]

Binary Heap is either Min Heap or Max Heap
Heaps are a type of binary tree that are great for priority queues.

heap and binary heap are not the same thing.

A heap is a tree-based data structure that satisfies the heap property, which means that for any node in the heap, its key (or value) is either greater than or equal to (in a max-heap) or less than or equal to (in a min-heap) the keys of its children.  
  
A binary heap, on the other hand, is a specific type of heap that is implemented as a binary tree (a tree in which each node has at most two children) and satisfies the heap property. In a binary heap, the key of each node is greater than or equal to (in a max-heap) or less than or equal to (in a min-heap) the keys of its children. Binary heaps are commonly used to implement priority queues, which are abstract data types that allow elements to be inserted with a priority and removed in priority order.  
  
So, while all binary heaps are heaps, not all heaps are binary heaps. There are other types of heaps as well, such as Fibonacci heap, binomial heap, and pairing heap.



**You can use Java Priority Queue as a Heap. 

PriorityQueue<Integer> minHeap = new PriorityQueue<Integer>(); 

Max Heap: --> to keep the max element always on top, the same order as above. 

PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Comparator.reverseOrder()); 

Which is the same as (Integer o1, Integer o2) -> Integer.compare(o2, o1) or - Integer.compare(o1, o2) as suggested from other answers. 



## When are Heaps useful? 

Heaps are used when the highest or lowest order/priority element needs to be removed. They allow quick access to this item in O(1) time. One use of a heap is to implement a priority queue. 

## Binary heaps are usually implemented using arrays, which save the overhead cost of storing pointers to child nodes. 

	Can be used for priority queues which is a different data structure from queues 

	Binary heaps are good for comparative operations used a lot in data storage priority queues sorting algorithms. 

## Applications of Heaps: 

1) Heap Sort: Heap Sort uses Binary Heap to sort an array in O(nLogn) time. 

2) Priority Queue: Priority queues can be efficiently implemented using Binary Heap because it supports insert(), delete() and extractmax(), decreaseKey() operations in O(logn) time. Binomoial Heap and Fibonacci Heap are variations of Binary Heap. These variations perform union also efficiently. 

3) Graph Algorithms: The priority queues are especially used in Graph Algorithms like Dijkstra’s Shortest Path and Prim’s Minimum Spanning Tree. 

4) Many problems can be efficiently solved using Heaps. See the following for example. 

	a) K’th Largest Element in an array. 

	b) Sort an almost sorted array. 

	c) Merge K Sorted Arrays. 

## Operations on Min Heap: 

	1) getMini(): It returns the root element of Min Heap. Time Complexity of this operation is O(1). 

	2) extractMin(): Removes the minimum element from MinHeap. Time Complexity of this Operation is O(Logn) as this operation needs to maintain the heap property (by calling heapify()) after removing root. 

	3) decreaseKey(): Decreases value of key. The time complexity of this operation is O(Logn). If the decreases key value of a node is greater than the parent of the node, then we don’t need to do anything. Otherwise, we need to traverse up to fix the violated heap property. 

	4) insert(): Inserting a new key takes O(Logn) time. We add a new key at the end of the tree. IF new key is greater than its parent, then we don’t need to do anything. Otherwise, we need to traverse up to fix the violated heap property. 

	5) delete(): Deleting a key also takes O(Logn) time. We replace the key to be deleted with minum infinite by calling decreaseKey(). After decreaseKey(), the minus infinite value must reach root, so we call extractMin() to remove the key.








Binary Heaps 

Binary heaps are data structures that are similar to trees but have different rules. 

Each node in a binary heap has at most two children, but sibling order does not matter. 

Heaps are as compact as possible, meaning new elements are added first from top to bottom then from left to right. 

Binary heaps can have one of two formats: a Max Binary Heap or a Min Binary Heap. 

All of the child nodes in a Max Binary Heap are smaller than their parent 

All of the child nodes in a Min Binary Heap are greater than their parent 

Implementation 

We can use a class to implement adding and removing from the heap, but we need a way to store the values in order. What kind of data structures do we know in JavaScript that have a specific order? Arrays do! Let’s take a look at the model below: 

There’s a pattern that children and parent nodes follow in our heap array. Where any index of an array is n, 

The index of the left child is 2n + 1 

The index of the right child is 2n + 2 

In order to derive the index of the parent of a child we use (n-1)/2 rounded down. Using this information, we can develop our insertion and removal methods. We’ll start with a Max Binary Heap. 

When inserting and removing in a binary heap, we use a method called bubbling to sort the heap. The insertion method uses two helper functions: swap and bubbleUp. The swap function swaps the elements in our values array at the two indices passed in. Once we push the new value into the array, our bubbleUp function compares the parent of the newly added element, and swaps it if the child is greater than the parent. We reassign our current index to the element’s new index if swapped, and keeps testing parents in a loop until the element fits, or we reach the root of the heap. 

Our method for removal ( called removeMax above) also uses bubbling, but it’s a bit more complicated. We’ll first swap the the first and last element in our values array so that we can pop the max element off of the array and return it. Before we return it, we need to make sure our heap is properly sorted. 

Our bubbleDown method then loops over the heap, checking the children nodes against our new root (the former last element in our array that we swapped). In order to bubble down properly, we first check the left child, and then the right child. If the parent is lesser than only one of the two children, we swap it with that child. However, if the parent is lesser than both of the children, we swap it with the greater value. We also need to ensure that both children exist. This is why we don’t swap until we’ve checked both the left and right child. 

Priority Queues 

Our priority queue isn’t that different from our Max Binary Heap, we’ll just need to change a few things. The biggest change is that our values are no longer numbers but Nodes. Each node has a value and a priority, and we need to change our implementation to consider a node’s priority instead of it’s value. I changed the method names to enqueue and dequeue instead of insert and removeMax . Finally, lower priority numbers usually signify higher priority, so we’ll need to change our Max Binary Heap to a Min Binary Heap. We’ll convert all the > signs to < where we are comparing priorities. 

https://stackoverflow.com/questions/48795979/what-is-the-difference-between-a-priority-queue-and-a-min-max-heap 

https://www.educba.com/priority-queue-vs-heap/



MIN HEAP 
this.heap.push(node) 

 if (this.heap.length > 1) { 

   let current = this.heap.length - 1; 

while (current > 1 && this.heap[Math.floor(current/2)] > this.heap[current]) { 

[this.heap[Math.floor(current/2)], this.heap[current]] 

              = 

 [this.heap[current],this.heap[Math.floor(current/2)]] 

 current = Math.floor(current/2) 

            } 

        } 

MAX HEAP 

 this.heap.push(node) 

  if (this.heap.length > 1) { 

   let current = this.heap.length - 1 

while (current > 1 && this.heap[Math.ceil(current/2)] < this.heap[current]) { 

      [this.heap[Math.ceil(current/2)], this.heap[current]] 

         = 

      [this.heap[current], this.heap[Math.ceil(current/2)]] 

current = Math.ceil(current/2) 

            } 

        } 

The remove min & max logic is the same since we are removing base off how we created the Heap in the first place