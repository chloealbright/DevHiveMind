---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
"Single-threaded" means that we open a single connection and measure the speeds from that. "Multi-threaded" means that we're using multiple connections - usually anywhere from 3 to 8 - at the same time, and measure the total speed across them all. 

Registers are used by the CPU when it's currently running a particular thread. When the OS decides to switch from one thread to another, the OS saves the current values of all the register into a private memory area specific to the first thread.


## During a thread's lifetime, what states can it have?

Threads go through a range of states during their lifetime, and it's important for programmers to understand them. Knowing a thread's various states can show that you know how threads operate and that you could debug a nonfunctioning thread. The interviewer may ask you about debugging later on in the interview, so just list the five states that a thread can have when giving your answer.

Example: "There are five states a thread can have: New, Runnable, Running, Waited/Blocked and Dead/Terminated."

From <[https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions](https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions)>


## What's a thread pool?

A thread pool is a design pattern used to facilitate multithreading. Asking about thread pools might be one way for an interviewer to determine if you know how to write performance-efficient code. When answering the question, give a brief but precise definition and explain why thread pools are useful.

Example: "A thread pool is a collection of worker threads created at start-up that programmers can assign tasks to as needed, then put back in the pool when complete. The main advantage of using a thread pool is having a supply of ready-made threads when you need them, which improves application performance."


How do you create a thread in Java?

Creating a thread is one of the most basic tasks that you may have as a programmer. This question demonstrates your knowledge of Java and your competence in basic coding. When you answer, try to provide more than one method to demonstrate your expertise.

Example: "You can create a thread in Java either by implementing the Runnable interface on a class and creating a thread object, or you can create a class that extends the thread class."



How do you stop a thread in Java?

This could be a trick question since threads usually only stop once they finish executing. Your answer can show interviewers that you understand the nuances of working in Java. When you answer, explain how threads usually stop and provide a method you could use to stop a thread manually.

Example: "There isn't a direct way to stop a thread in Java. Often, you have to wait for a thread to die when it finishes executing. If you need to manually kill a thread, you can use a Volatile boolean variable within a thread that throws an exception when triggered from another thread."



What's a race condition?

Race conditions occur when a system is unable to execute multiple functions simultaneously. This question addresses one of the primary obstacles to multithreading, so it's important to show awareness of the issue. When you give your answer, briefly define what a race condition is and mention what strategy a programmer might use to fix the issue.

Example: "A race condition occurs when multiple concurrent threads compete to run first. If the thread that wins the race isn't the one that was supposed to run first, the code may exhibit unexpected behavior. You can resolve this problem with synchronization."

From <[https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions](https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions)>



What's synchronization?

Synchronization is a useful way to fix race conditions that arise during multithreading. If you mention synchronization in another answer, the interviewer may ask you to define it further. Understanding synchronization shows that you are able to mitigate some of the dangers of multithreading. When answering this question, you can give a simple explanation of what synchronization accomplishes.

Example: "Synchronization forces threads to run one at a time to prevent a race condition or multiple threads trying to perform the same task."

From <[https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions](https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions)>



Why might you use synchronized block?

Synchronized block allows programmers to synchronize a specific subset of a method. This question shows that you understand several ways to use synchronization when managing multiple threads. When answering this question, give a brief explanation of synchronized block and how it works in the context of multithreading.

Example: "Synchronized block allows you to designate a particular portion of a method as synchronized. That is, only a single thread is able to run until it completes, prioritizing that thread above others."

From <[https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions](https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions)>