---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Certainly! Here's an example in Java that demonstrates multiple threads with independent execution streams working on shared state using preemptive scheduling and synchronization:

```java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class ConcurrentExample {
    private static int sharedCounter = 0;
    private static Lock lock = new ReentrantLock();

    public static void main(String[] args) {
        // Creating multiple threads
        Thread thread1 = new Thread(new CounterTask());
        Thread thread2 = new Thread(new CounterTask());

        // Starting the threads
        thread1.start();
        thread2.start();

        // Waiting for the threads to complete
        try {
            thread1.join();
            thread2.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        // Printing the final shared counter value
        System.out.println("Final Counter Value: " + sharedCounter);
    }

    static class CounterTask implements Runnable {
        @Override
        public void run() {
            for (int i = 0; i < 10000; i++) {
                // Acquiring the lock to access the shared counter
                lock.lock();
                try {
                    sharedCounter++;
                } finally {
                    // Releasing the lock after modifying the shared counter
                    lock.unlock();
                }
            }
        }
    }
}
```

In this example, we have a shared state represented by the `sharedCounter` variable. We create two threads (`thread1` and `thread2`) that execute the `CounterTask` concurrently.

The `CounterTask` class implements the `Runnable` interface and represents an independent execution stream. Each task increments the `sharedCounter` variable by acquiring a lock using the `ReentrantLock` class. This ensures that only one thread can modify the shared counter at a time. After modifying the counter, the lock is released.

The main method creates and starts the two threads. It then waits for both threads to complete using the `join()` method. Finally, it prints the final value of the shared counter.

By using preemptive scheduling, the operating system determines when each thread gets CPU time to execute. The synchronization mechanism provided by the lock ensures that only one thread can access and modify the shared state at any given time, avoiding data corruption or inconsistent results.

This example demonstrates the use of threads with independent execution streams working on shared state while ensuring synchronization and mutual exclusion using a lock.


