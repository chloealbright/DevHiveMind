![[unnamed (27).gif]]

Queues are similar to stacks but we are going first in first out like a checkout line there are dynamic queues that grow in size they are good for background process and task scheduling they are used a lot in cron jobs, memory management, and a lot of background activity. 

sometimes we have a central queue and have multiple points of access. 

Queue<Integer> queue = new Queue<Integer>();  

Let queue = new Array<Integer>(); // focus is the removal and adding of elements 

Adding an item to the end is called enqueuing and removing it from the front is called dequeuing   

queues are used in Breadth-first search (BFS) which is an algorithm for traversing or searching tree or graph  

is a linear data structures data that can be accessed sequentially  

Application 

Stacks & Queues 

Advantage: Both structures are very efficient in adding and removing items. 

Disadvantage: They both have quite a limited number of use cases compared to other data structures. 

Queues are used in things like printers 

Traversal is big O of n, enqueue , dequeue, and peek is big O of 1 

Enqueue is basically like push 

Dequeue like pop but it pops off the first person instead of the last person








Queues are similar to stacks but we are going first in first out like a checkout line there are dynamic queues that grow in size they are good for background process and task scheduling they are used a lot in cron jobs, memory management, and a lot of background activity.  
  
some times we have a central queue and have multiple points of access.  
  
Adding an item to the end is called enqueuing and removing it from the front is called dequeuing  
  
queues are used in Breadth-first search (BFS) which is an algorithm for traversing or searching tree or graph  
  
is a linear data structures data that can be accessed sequentially  
Application  
  
Stacks & Queues  
  
Advantage: Both structures are very efficient in adding and removing items.  
  
Disadvantage: They both have quite a limited number of use cases compared to other data structures.  
  
Queues are used in things like printers  
  
Traversal is big O of n, enqueue , dequeue, and peek is big O of 1  
  
Enqueue is basically like push  
  
Dequeue like pop but it pops off the first person instead of the last person




QUEUE ->  Built with LinkedList or Arrays which you should avoid when you do bfs question  

Dequeue use queue.shift(which is basically dequeue) meaning  FIFO(First In First Out)  

and enqueue  method adds an element at the end of the queue. which basically the same as push








When we want to process data efficiently in computer programming, we sometimes use data structures called stacks and queues to form an order for our data. A priority queue functions somewhat like a queue in that it processes data from the front of the list (or queue), but it differs when data is added to the queue. While a traditional queue simply adds the data to the back of the line, priority queues need to ensure that the new data gets a proper place in the line according to its priority. We’ll need to use something called a binary heap to implement our priority queue. 

It doesn't make any sense at all to implement a heap as a linked list. (The most common kinds of) heaps are inherently binary trees. You can store a heap in an array because it's easy to compute the array index of a node's children: the children of the node at index K live at indices 2K+1 and 2K+2 if indices start at 0 (or at indices 2K and 2K+1 if indices start at 1). It's massively more efficient to find the Kth element of an array than the Kth element of a linked list. 

Advantages of storing a heap as an array rather than a pointer-based binary tree include the following. 

Lower memory usage (no need to store three pointers for every element of the heap). 

Easier memory management (just one object allocated, rather than N). 

Better locality of reference (the items in the heap are relatively close together in memory rather than scattered wherever the allocator put them). 

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


