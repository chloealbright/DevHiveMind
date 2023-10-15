```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class MultiprocessingExample {

    public static void main(String[] args) {
        System.out.println("Start");

        // Create an ExecutorService with a fixed number of threads
        ExecutorService executorService = Executors.newFixedThreadPool(2);

        // Submit tasks to the ExecutorService
        executorService.submit(MultiprocessingExample::task1);
        executorService.submit(MultiprocessingExample::task2);

        // Shutdown the ExecutorService
        executorService.shutdown();

        System.out.println("End");
    }

    private static void task1() {
        System.out.println("Executing Task 1");
        // Perform some time-consuming operation
        System.out.println("Task 1 completed");
    }

    private static void task2() {
        System.out.println("Executing Task 2");
        // Perform some time-consuming operation
        System.out.println("Task 2 completed");
    }
}

```


```javascript
const { Worker } = require('worker_threads');

console.log("Start");

// Create a new worker for Task 1
const worker1 = new Worker('./task1.js');

// Create a new worker for Task 2
const worker2 = new Worker('./task2.js');

// Listen for messages from the workers
worker1.on('message', message => {
    console.log(`Task 1 completed: ${message}`);
});
worker2.on('message', message => {
    console.log(`Task 2 completed: ${message}`);
});

// Terminate the workers when they are done
worker1.on('exit', () => {
    console.log("Worker 1 terminated");
});
worker2.on('exit', () => {
    console.log("Worker 2 terminated");
});

console.log("End");

```