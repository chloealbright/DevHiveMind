API stands for Application Programming Interface. It is a software-to-software interface that enables two applications to exchange data with each other. Each time we use an app like Facebook or Instagram, send an instant message or check the weather on our phone, we use nothing but an API. It is like the hidden backbone of our modern world.

Big-Endian – A data representation for a multibyte value that has the most significant byte stored at the lowest memory address. Note that only the bytes are reordered, never the nibbles or bits that comprise them. Every processor stores its data in either big-endian or little-endian format. Sun’s SPARC, Motorola’s 68k, and the PowerPC families are all big-endian. The Java virtual machine is big-endian as well. Similarly, every communications protocol must define the byte order of its multibyte values. TCP/IP uses big-endian representation. 

BLOB – An abbreviation for Binary Large OBject. In SQL, BLOB can be a general term for any data of type long varbinary, long varchar, or long wvarchar. It is also a specific term (and synonym) for data of type long varbinary.

Catalog – A repository for the computer-readable form of a database’s data definition meta-data. Sometimes called the system catalog or just syscat. 

Checksum – A numerical check value calculated from a larger set of data. A checksum is most often used when sending a packet of data over a network or other communications channel. One checksum formula is a simple addition, with overflow ignored, wherein the bytes of the packet are added together into a variable of a fixed size/width (say, 16 bits) as they are sent. The checksum is typically sent at the end of the packet and used at the receiving end to confirm the integrity of the preceding data.


Compiler – A software-development tool that translates high-level language programs into the machine-language instructions that a particular processor can understand and execute. However, the object code that results is not yet ready to be run; at least a linker or link-step must follow.



## consecutive vs concurrent

Consecutive refers to things that are arranged or happen in a sequential order. A criminal who serves a consecutive sentence does time for one conviction after another.Jan 6, 2022 



Concurrent refers to things happening or existing at the same time. In computing and programming, concurrency specifically relates to the concept of multiple tasks making progress at overlapping time intervals. It doesn't necessarily mean that these tasks are executed simultaneously, but rather they can be interleaved or partially overlapping in their execution.

There are two main types of concurrency:

1. **Parallel Concurrency:**
    
    - Tasks truly execute simultaneously, often achieved through multiple processors or cores.
    - This type of concurrency is more about simultaneous execution.
2. **Sequential Concurrency (or Simulated Concurrency):**
    
    - Tasks appear to be executed simultaneously by interleaving their execution.
    - This is often achieved through techniques such as multitasking, where a system rapidly switches between different tasks.

Concurrency is crucial in programming to handle multiple tasks efficiently, especially in situations where tasks can be performed independently or where waiting for one task to complete before starting another would be inefficient. It's commonly used in systems dealing with input/output operations, network requests, and handling multiple user interactions simultaneously.

In summary, concurrency in computing refers to the ability of a system to execute multiple tasks in overlapping time intervals, either truly simultaneously (parallel) or by cleverly interleaving their execution (sequential).








Scope creep: Adding additional features or functions of a new product, requirements, or work that is not authorized (i.e., beyond the agreed-upon scope).



By definition, back-end development refers to the server-side of the development where the primary focus is on how the site works. 

They are liable to make updates and changes in addition to monitoring the functionality of the site. 

Back-end web development also predominantly consists of three parts: a server, an application, and a database. The code written by back-end developers is what communicates the database information to the browser. Anything that we cannot see easily with the eye - databases and the servers is the work of a back-end developer.





tech talk  

Convertor/Serializer/Deserializer: 

These terms are generically used to describe utility classes that are responsible for converting from/to plain data to/from business objects. They are mostly part of some open source conversion libraries. 

Abstraction reduces the tech-jargon density of the discussion, thus making it bearable to the rest of the team 

In such a case, you can refer to them by their real names, too. However, doing so could add more complexity to team communication when a non-programmer audience is involved.



JQuery is a javascript library which is full of tools  that allow you to implement functionalities or effects without the need for certain code



## Logical Call Stack
In the context of asynchronous programming, a logical call stack refers to a conceptual representation of the execution context of a program. Unlike a physical stack(which represents the actual function calls in memory) tied to a specific thread in synchronous programming, a logical stack in asynchronous programming is not bound to a single thread.

The logical stack is a way to visualize the flow of execution in asynchronous code. It helps keep track of the sequence of tasks and operations, especially when there are asynchronous calls that may not complete immediately. Asynchronous tasks can be paused, allowing other tasks to proceed, and then resumed when the asynchronous operation finishes.

This logical stack is essential for managing the state of the program during asynchronous operations, and it contributes to the efficiency of asynchronous programming by enabling concurrent execution of tasks without the need for multiple threads. It's a crucial concept in understanding how asynchronous code can be organized and executed in a non-blocking manner.



**Propagation** refers to the transmission, spread, or dissemination of something, such as information, signals, or effects, from one point or source to another. It involves the process of carrying or passing on these elements to reach a wider or different area, often involving a sequence of steps or changes as they move from their origin to their destination. Propagation can occur in various contexts, including in the fields of science, technology, communication, and biology. ^5487d3