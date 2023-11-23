---
tags: 
author:
  - jacgit18
Status: init
Started: 2023-11-23
EditDate: 
Relates:
---
You can use the `Worker` API to run functions in parallel in pure JavaScript without the need for HTML. Here's an example:  
  
```javascript  
// Function 1  
function function1() {  
return new Promise((resolve) => {  
setTimeout(() => {  
console.log('Function 1 completed');  
resolve();  
}, 1000); // Simulating a time-consuming task  
});  
}  
  
// Function 2  
function function2() {  
return new Promise((resolve) => {  
setTimeout(() => {  
console.log('Function 2 completed');  
resolve();  
}, 2000); // Simulating a longer time-consuming task  
});  
}  
  
// Create a Worker for function1  
const worker1 = new Worker(URL.createObjectURL(new Blob([`(${function1.toString()})()`]));  
  
// Create a Worker for function2  
const worker2 = new Worker(URL.createObjectURL(new Blob([`(${function2.toString()})()`]));  
  
const start = performance.now();  
  
// Listen for messages from worker1  
worker1.onmessage = () => {  
console.log('Worker 1 completed');  
worker1.terminate();  
  
// Listen for messages from worker2  
worker2.onmessage = () => {  
console.log('Worker 2 completed');  
worker2.terminate();  
  
const end = performance.now();  
const elapsedTime = end - start;  
console.log(`Both workers completed in ${elapsedTime} milliseconds`);  
};  
  
worker2.postMessage('start');  
};  
  
worker1.postMessage('start');  
```  
  
In this example, we define `function1` and `function2`, and then create two separate workers to run them in parallel. The workers communicate with the main script using `postMessage`. When both workers complete their tasks, the main script measures the elapsed time to test their speed.