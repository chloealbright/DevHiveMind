![[1653752837328.849599076.jpg]]
## Prompt


## Threads
**Hyper-threading** is a process by which a CPU **divides up its physical cores into virtual cores** that are treated as if they are actually physical cores by the operating system. These virtual cores are also called *threads* which is a unit of execution used to manage concurrency in programming. Most CPU's with 2 cores use this process to create 4 threads/virtual cores. Cores increase the amount of work accomplished at a time by doing things like [[Content switching]]. Whereas threads improve throughput, and computational speed up using multiple CPU's for operating numerous processes or sequences of processes. Threads can have multiple independent execution streams along with shared state. Besides that it can use preemptive scheduling and synchronization(lock condition).
![[1653752299890.1954961617.png]]

## Multi-Threading
***Multi-threading*** is a technique that takes a process and breaks it down into multiple task and executing those sub task of that initial process at the same time and also having the ability to execute individually while sharing their resources. it is also considered a type of [[Synchronous  vs Asynchronous vs  Multiprocessing | asynchronous programming ]] .

Multithreading is used a lot in game development but not as much in business app development

>Process = Multiple applications running simultaneously in the server, PC or Mac
>Thread =Multiple tasks running within a process

## Daemon thread
A daemon is a type of useful support thread that performs unique tasks like running continuously as a background process and wakes up to handle periodic service requests, which often come from remote processes. 

## Multiprocessing 
[[Multiprocessing example | Multiprocessing]] - the idea of, instead of spinning up threads in a single process that shares the same resources of the process. we create individual unique processes with there on memory structure and you just communicate between these process using inter process communication or centralized Redis database, there are many ways to communicate between processes. 

Multiprocessing is good for scaling up to be used on multiple machines and can used to brute force through a password with a hash 



### Parallel processing vs Concurrent processing
![[1653753275490.1327774142.jpg]]
- Concurrency(Multi-threading) is the task of running and managing multiple computations at the same time. core to thread operates by switching.  
- In Java, concurrency is the ability to run several programs or parts of a program in parallel. A time-consuming task can be performed asynchronously or in parallel improving the program's throughput and interactivity. A modern computer has several CPU's or several cores within one CPU.
- [[Parallelism]] is the task of running multiple computations simultaneously. core to core all operate at the same time. ^2862c2

[[Concurrent programming]]



## CPU FlashCard
#processor
Why use multithreading in your applications?

What is a daemon thread? A daemon thread is a low-priority thread used for unique task.

what is an example of those task? one example is providing background services or support to the other threads. 

Multithreading is important because it facilitates a wide range of benefits not provided by other programming techniques. This question allows you to demonstrate to the interviewer how well you appreciate the advantages of multithreading. When you answer this question, explain one or two of the main advantages of multithreading, including more efficient CPU usage, faster task execution and simplification of application structures.

Example: "Since each thread runs concurrently, multithreading makes efficient use of the CPU. You can have background processes running while the application receives user input. Also, tasks can execute faster since each thread runs independently."

***FIX
[[CPU Thread Flash]]





