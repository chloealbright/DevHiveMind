---
tags: 
author:
  - jacgit18
Status: refinement
Started: 
EditDate: 
Relates:
---
Can you explain what the thread scheduler is and its relationship to thread priority?

This is another question that addresses how multi-threading works at the CPU level. As a programmer, you may have to know how to write thread scheduler algorithms that prioritize different threads. When answering this question, it's acceptable to give a simple, one-sentence explanation of what a thread scheduler does.

Example: "The thread scheduler is what allocates CPU time to threads and determines the order in which threads execute."

From <[https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions](https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions)>



Why might you describe thread behavior as unpredictable?

In some cases, a thread scheduler may produce different outcomes when running on different CPUs leading to unpredictable thread behavior. Interviewers may ask this question to see if you understand the inherent risks involved when different CPUs determine the thread schedule. When answering this question, briefly describe how different CPUs can cause unpredictable thread behavior.

Example: "Because thread scheduling is determined by the CPU, different CPUs may give priority to different threads. This means there's a chance two CPUs might not run your threads in the same order, creating unpredictability in your code execution."


What's time slicing?

Time slicing is another programming concept that relates to CPU usage. Your answer to this question can show the interviewer you understand how the thread scheduler works. When you answer this question, explain the role that time slicing plays in scheduling threads.

Example: "Time slicing is the process used by the thread scheduler to divide CPU time between the available active threads."


What's thread starvation?

Thread starvation is a phenomenon in which a given thread is unable to make progress due to a lack of resources. This is a common issue that can cause malfunctions, and your awareness of thread starvation can be useful for code debugging. When you answer this question, explain what thread starvation is and explain when it might occur.

Example: "Thread starvation is when there's insufficient CPU capacity to execute a thread. This can happen with low-priority threads or threads that programmers demote in favor of other threads."


Explain the busy spin technique and why you might use it.

Bust spinning is a wait strategy that programmers might use to prevent CPU release. This question allows interviewers to gauge your understanding of popular thread manipulation techniques. When you answer, explain what busy spinning does and describe the advantage that it offers.

Example: "Busy spin is when you pause a thread by making it run an empty loop for a certain period. Unlike other methods like wait() or sleep(), a busy spin doesn't give up CPU control and therefore preserves CPU cache."


Can you start a thread twice?

As mentioned above, threads move through several different states during their lifecycle. This question shows interviewers that you understand the basic concepts of thread states and lifecycles. When answering this question, briefly state that you can't start a thread twice and explain why.

Example: "Once you execute a thread, it's dead and you can't restart it"


Can you describe a deadlock situation?

Deadlock is a common problem that can cause code to stall. Your ability to explain the problem indicates you understand this challenge and may know how to resolve it. When you answer, explain what a deadlock situation is and describe some of the reasons a deadlock may occur.

Example: "A deadlock situation occurs when multiple threads are waiting on one another to release CPU resources so they can run. For example, this can happen when a single thread has exclusive priority but needs resources from a waiting thread, or all the threads are depending on one another to release needed resources."




What happens when a livelock occurs?

This question is often a follow-up to the previous question and deals with another challenge you might face while multithreading. Your answer can show interviewers that you have a good understanding of issues you might face as a programmer. When you answer, describe what a livelock is and explain how it relates to a deadlock. You can also explain some issues that could cause a livelock.

Example: "A livelock is similar to a deadlock situation, except in a livelock, the state of the threads change without ever making progress. For instance, if all the threads are in infinite loops."



In Java, what's the difference between the wait() and sleep() methods? 

These are two common Java methods that accomplish similar tasks. Although they appear to do the same thing, programmers use them in different contexts, and it's important to distinguish their functions. When you answer the question, explain what each method is and what it does. 

Example: "The wait() method pauses a thread and waits until there are no notify() or notifyAll() method calls from other threads. The sleep() method pauses for a given period, allowing other threads to run, after which it resumes execution." 

From <[https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions](https://www.indeed.com/career-advice/interviewing/multithreading-interview-questions)>