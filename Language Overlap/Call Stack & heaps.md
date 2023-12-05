![[Call Stack.gif]]
A stack has elements like primitive values which are numbers strings boolean nulls undefined and symbols and tends to be fast but has limited space  
  
While a heap is much slower and consists of all types of objects like object literals arrays functions dates and all other objects also has a lot of space  
  
Stacks and heaps have to do with memory so when you create a primitive type like a string or one of the others mentioned the value of this string is stored in a stack  
  
So when we create an object that probably has primitive types we create a pointer behind the scenes that end up on the stack with the reference of the object variable name that is stored in  
  
If you have a variable with a number and another variable that stores the first variable in the stack they'll be two separate values in the stack instead of one since you're storing a primitive type even though it's the same primitive type because they're two different positions and memory in the stack if you update the value of the first variable then the number changes it doesn't create another element in the stack or affects the second variable that is storing the first variables original value  
  
  
Now if you do the same thing with objects instead of primitive types there won't be a new object created on the heap the variables that store the pointer on the heap when use the same pointer that's why so if you update the first variable the values will change for both the first and the second variable since they share the same pointer  
  
  
Call Stack  
=============  
the call stack is maintained in memory for each task and the thread 

Each function call is a frame on the stack.  

  
This call stack is a stack of function calls to be executed in order. ( You see why it’s called a stack? )  

The frame contains the function arguments and local variables. This is where the scope object, and hence closure is defined!  
  
The functions are popped from the stack when they return.  
  
Every script begins with a main() on the stack, as the function containing all other functions in the script.  
  
JavaScript is a single-threaded language while other languages are multi-threaded meaning that JavaScript has one call stack and the others with multi-thread are multiple call stacks be non-blocking single-threaded means that it has only one call stack and one call stack only it can only do one thing at a time and as you saw  
  
  
Being single-threaded meaning it could do one thing at a time and its call stack is first in last out  
  
  
-----------------------------------------------------  
Heap  
=========  
Every object you create needs a place in memory to live. This place is the heap: A large unstructured region of memory.  
  
If you’re coming from C++ land, heap is where things go when constructed using new in C++.  
------------------------------------------------------  
Web APIs and Events  
===================  
Web APIs are low-level functions present in the Javascript runtime to interact with the OS. They are implemented by the browser/host. For ex: setTimeout().  
  
They are called from the stack and begin processing. The function returns at this point (thus popping the stack frame). This is what gives Javascript the asynchronous characteristic. Almost all its basic APIs are non-blocking.  
  
Have a look at the GIF above - and this bit will become clearer.  
  
These APIs generate a message.  
This could be an API call to fetch data, in which case the message is the data.  
This could be setTimeout(), where the message is empty.  
This could be an event on a DOM button like onClick, where the message is information stored in the button.  
  
The APIs send these messages to the callback queue. They have a callback function that is attached to the message. This callback is received from the call stack. ( something we provide when calling the API)  
  
In web browsers, messages are added anytime an event occurs and there is an event listener attached to it. If there is no listener, the event is lost. So a click on an element with a click event handler will add a message - likewise with any other event.  
-------------------------------------------------------------------------  
Callback queue  
============  
This is a queue containing all tasks that have finished processing. It has a queue of messages with callback functions for each message.  
  
To process a message, the callback function is called with the message as input - but the queue can’t do this, it’s just a message queue. This processing is achieved via the Event Loop.  
  
Fun-fact: This queue is commonly known as the macrotask queue. There’s a little microtask queue lurking behind too.  
Not a lot of people know about this - but it comes into play when dealing with Promises. A story for Part 3, perhaps? ( Wow, JS is huge, isn’t it? )  
---------------------------------------------------------------------------------------------------  
Event Loop  
==========  
To call the callbacks in the callback queue, we need to bring them back on the call stack. That’s the only way a function is called.  
  
The Event Loop handles this bit. It’s a running loop that checks if the call stack is empty on every loop.  
  
Once the call stack is empty, the event loop takes the first element from the callback queue and transfers the callback to the call stack.  
  
Run-to-completion  
In the event loop, every message runs to completion. This means, no new message is added to the call stack while the current message is executing.