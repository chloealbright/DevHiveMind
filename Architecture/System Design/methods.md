---
tags: 
author:
  - jacgit18
Comments: This documentation discusses
Status: Capture
Started: 
EditDate: 
Relates:
---
It's hard to design a software system that can work on a large scale.  
  
You need to think about a lot of different options, each with its pros and cons.  
  
But every solution comes down to using three main methods:  
  
1. Adding server clones  
  
This is the quickest and least expensive way to scale a system from scratch.  
  
Just add more exact copies of a server or component so that they all share the load.  
  
This method works best for services that don't keep any state, so there is nothing to sync.  
  
Whenever the load balancer receives a request, it should be able to send it to any server without knowing where the previous request went.  
  
2. Partitioning servers  
  
A more complex approach is dividing the system into groups of servers with different roles.  
  
Ideally, each group of servers is a self-contained application that can make decisions independently.  
  
This separation allows each part to be scaled on its own, depending on its needs.  
  
It promotes efficient management, as teams can work on different parts of the system simultaneously without interfering with each other.  
  
However, it requires more initial effort, and there's a limit to how much you can partition a system before it becomes too complex.  
  
3, Partitioning data  
  
A third approach is dividing and distributing the entire dataset across multiple machines, each having a subset of the data.  
  
This setup speeds up data processing and storage as each server only has to deal with a smaller amount of it at a time.  
  
It also makes the system scalable, so as the amount of data grows, you can add more computers and change how the data is distributed between them.  
  
The partitioning strategy, however, makes things more complicated.  
  
You need a system to track where each piece of data is stored to direct queries to the correct server.  
  
Also, it can be hard to make queries that cover more than one data partition work well.


![[ScalingMethods.jpeg]]