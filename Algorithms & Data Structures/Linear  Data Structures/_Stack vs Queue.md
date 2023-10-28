---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[Pasted image 20230411081206.png]]

Dequeue vs Pop  

main diff is Dequeue remove stuff at beginning which can just be a queue.Shift() and pop at the end or top of the stack  

you can use unshift(adds to beginning of an array)  

Enqueue is basically push() which Stacks and Queues both use, and as for pop() it is used with Stacks to remove element  at the same point were we push elements and Dequeue is basically a shift() which ends up removing the value we pushed then the next one behind it 

Use a stack when you want to get things out in the reverse order than you put them in. 

Fundamentally whenever you need to put a reverse gear & get the elements in constant time, use a Stack.  

Stack follows LIFO it’s just a way of arranging data. 

Appln: 

Achieving the undo operation in notepads. 

Browser back button uses a Stack. 

Queue: 

Use a queue when you want to get things out in the order that you put them in. 

Queues are implemented using a First-In-Fist-Out (FIFO) principle 

Appln: 

In real life, Call Center phone systems will use Queues, to hold people calling them in an order, until a service representative is free. CPU scheduling, Disk Scheduling. When multiple processes require CPU at the same time, various CPU scheduling algorithms are used which are implemented using Queue data structure. 

In print spooling 

Breadth First search in a Graph 

Handling of interrupts in real-time systems. The interrupts are handled in the same order as they arrive, First come first served.