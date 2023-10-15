Node js is a runtime environment for running javascript on your system instead of browser to build apps on different platforms. node js is based on v8 engine that runs on google chrome 


the v8 engine is Google's open-source high-performance JavaScript and WebAssembly engine which is used by the browser to convert javascript into machine code for the computer to understand with the help of a compiler or interpreter. 

V8 engine are made up of two parts memory heap and call stack



and other internet browsers. also, learn and expand knowledge on NPM and learn Express js which is a framework for node js that is designed for building web applications and APIs. It has been called the de facto standard server framework for Node.js. basically use to manage the flow of data between server and route with other features.





Node.js is an open-source, cross-platform, back-end JavaScript runtime environment that is a single threaded non-blocking Asynchronous execution framework. 

It is primarily used for non-blocking, event-driven servers, due to its single-threaded nature. It's used for traditional web sites and back-end API services, but was designed with real-time, push-based architectures in mind. 

The way Node.js works is that there is a single thread handling requests. The idea that a single threaded server can perform better than a thread pool server is not new to Node.js. Nginx is built on this principle. Nginx is a single-threaded web server and can handle a tremendous amount of concurrent requests. A simple benchmark comparing Nginx to Apache, both serving a single static file from the file system, is shown in Figure 2-4. 

You require a thread to have a particular priority. You have tasks that cause the thread to block for long periods of time. The thread pool has a maximum number of threads, so a large number of blocked thread pool threads might prevent tasks from starting. You need to place threads into a single-threaded apartment. 

Node consists of global utilities, consoles, timers,  processes, buffer etc... 

Underscore Underscore (npm install underscore) is by far the most popular JavaScript library available on NPM. It is the library with the largest number of dependents (other packages that depend on this package). It is called underscore because it creates a global variable ‘_’ when used in the browser. In node, you are free to name the variable returned from require('underscore') whatever you want, but it is conventional to still do var _ = require('underscore'). Underscore provides a lot of functional programming support to JavaScript that you find in other languages such as Ruby and Python. Every good JavaScript developer should be familiar with it. Note that bits of functionality of underscore is being added to core JavaScript with new versions, but to work across all browsers and Node.js it is recommended that you use underscore if only for consistency and lesser cognitive load (so you have less stuff to keep in your head at a time). 

Streaming data is one of those areas that fit very naturally in Node.js. Streams are great for improving user experience plus decreasing server resource utilization. 

 event emitters and streams, we first need to understand JavaScript inheritance. 

We already have a way to execute some code based on some occurrence (event) using callbacks. A more general concept for handling occurrences of significance is events. An event is like a broadcast, while a callback is like a handshake. A component that raises events knows nothing about its clients, while a component that uses callbacks knows a great deal. This makes events ideal for scenarios where the significance of the occurrence is determined by the client. Maybe the client wants to know, maybe it doesn’t. Registering multiple clients is also simpler with this even as we will see in this section. 

Node.js comes with built-in support for events baked into the core events module. As always, use require('events') to load the module. The events module has one simple class "EventEmitter", which we present next. 

EventEmitter class 

EventEmitter is a class designed to make it easy to emit events (no surprise there) and subscribe to raised events.

## Event Loop 

The Event Loop is one of the most important aspects to understand about Node.js. Why is this so important? Because it explains how Node.js can be asynchronous and have non-blocking I/O, it explains the "killer feature" of Node.js, which made it this successful.


## Inside the engine of Javascript

![[h7509mqq3egedothd2g8.jpeg]]

When you write a program, a syntax parser reads your code and then the compiler translates it into computer instructions(a lower-level language). 

Where you write your code and what surrounds it is crucial! The area of the code you are looking at physically is the lexical environment. 

It sounds funny, but not every programming language is like that. In JS, however, the compiler that converts your code cares about where you put things. And based on it, decide where your code will sit in the memory and interact. 

So there are multiple lexical environments, but one that is being executed is handled by the execution context — a context in which javascript code is running.