---
tags:
  - linear
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (30).gif]]

A stacks is a higher-level data structures based on lower-level data structures like arrays and linked lists  

that is less efficient but more useful. It can be limited in terms of functionality which is good in some cases only having a few methods 

stack just use pop and push  and is LIFO(Last In First Out)  meaning if you insert something and delete something you're deleting the last insert.  

peek to see the top of stack and length to see size. 

```Java
Stack<Integer> stack = new Stack<Integer>(); 

Let stack = new Array<Integer>(); // focus is the removal and adding of elements 

```
## Stacks implementation 

Using stacks with arrays Vs stacks with the linked list 

It depends on what you prefer and what your priority is when using them so go back to the pros and cons of arrays and linked list & similar in the context of doing DFS pattern 

Like a link list which has everything scattered in memory and uses extra memory because you have to have access to the pointers but the memory is more dynamic  

An array can be static or dynamic depending on the language where you would have to add to resize the array 

## Use case 

stacks are used a lot in procedural programming in a memory stack  

Building  stacks with arrays allows cache locality which makes it technically faster when accessing items in memory  

each portion of the stack in this case has a return link 

stack logic can also be used in the front end for handling states  

good for browser history 

can be  used with both static structures  with a predetermined storage capacity 

## Stack & Heaps in computer RAM  

Stack is allocated by the OS when the process starts (assuming the existence of an OS), it is maintained inline by the program. This is another reason the stack is faster, as well - push and pop operations are typically one machine instruction, and modern machines can do at least 3 of them in one cycle, whereas allocating or freeing heap involves calling into OS code. 

[https://stackoverflow.com/questions/79923/what-and-where-are-the-stack-and-heap](https://stackoverflow.com/questions/79923/what-and-where-are-the-stack-and-heap)  

Variables created on the stack will go out of scope and are automatically deallocated. 

Much faster to allocate in comparison to variables on the heap. 

Implemented with an actual stack data structure. 

Stores local data, return addresses, used for parameter passing. 

Can have a stack overflow when too much of the stack is used (mostly from infinite or too deep recursion, very large allocations). 

Data created on the stack can be used without pointers. 

You would use the stack if you know exactly how much data you need to allocate before compile time and it is not too big. 

Usually has a maximum size already determined when your program starts. 

In C++, variables on the heap must be destroyed manually and never fall out of scope. The data is freed with delete, delete[], or free. 

Slower to allocate in comparison to variables on the stack. 

Used on demand to allocate a block of data for use by the program. 

Can have fragmentation when there are a lot of allocations and deallocations. 

In C++ or C, data created on the heap will be pointed to by pointers and allocated with new or malloc respectively. 

Can have allocation failures if too big of a buffer is requested to be allocated. 

You would use the heap if you don't know exactly how much data you will need at run time or if you need to allocate a lot of data. 

Responsible for memory leaks.