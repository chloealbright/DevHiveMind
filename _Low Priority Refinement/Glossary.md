---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
- **API (Application Programming Interface)**: It's a software-to-software interface enabling data exchange between applications, forming the backbone of modern technology.

- **Back-End Development**: Concerns the server-side of a website, handling server, application, and database interactions.

- **Big-Endian**: A data representation where the most significant byte is stored at the lowest memory address. Various processors and communication protocols use this format.

- **BLOB (Binary Large OBject)**: In SQL, it's a term for data types like long varbinary, long varchar, or long wvarchar.

- **Catalog**: A repository for a database's data definition meta-data, also known as the system catalog or syscat.

- **Checksum**: A numerical value calculated from data, often used for data integrity during transmission over networks.

- **CMS**:  A content management system is computer software used to manage the creation and modification of digital content. A CMS is typically used for enterprise content management and web content management.

- **Compiler**: Translates high-level language programs into machine instructions, but additional steps like linking are needed for executable code.

- **Concurrent**: Concurrent refers to things happening or existing at the same time. In computing and programming, concurrency specifically relates to the concept of multiple tasks making progress at overlapping time intervals. It doesn't necessarily mean that these tasks are executed simultaneously, but rather they can be interleaved or partially overlapping in their execution.
 ^4f0064

- **Concurrency** is crucial in programming to handle multiple tasks efficiently, especially in situations where tasks can be performed independently or where waiting for one task to complete before starting another would be inefficient. It's commonly used in systems dealing with input/output operations, network requests, and handling multiple user interactions simultaneously.

- **Consecutive**: Sequential order, e.g., serving one sentence after another.

- **jQuery**: A JavaScript library for implementing website functionalities and effects.

- **Logical Call Stack**: A conceptual representation in asynchronous programming for tracking execution flow.

- **MetaData**: Metadata is the data about the data. Metadata describes data relationships and characteristics, and is often referred to as a data dictionary, though that seems to be a term more prevalent in the relational world (though not exclusive to it by any means).

- **Propagation** refers to the transmission, spread, or dissemination of something, such as information, signals, or effects, from one point or source to another. It involves the process of carrying or passing on these elements to reach a wider or different area, often involving a sequence of steps or changes as they move from their origin to their destination. Propagation can occur in various contexts, including in the fields of science, technology, communication, and biology. ^5487d3

- **Scope Creep**: Unauthorized addition of features or work beyond the agreed-upon scope.

- **Typed languages** - Languages where data types are defined, known by the machine at compile-time or runtime.   ^acb92b

- **Verbose**: Using more words than necessary to express something.


- **Convertor:** A utility class responsible for converting data between plain, often raw, format and structured business objects. It plays a role in transforming information from a general form to one that aligns with the needs of specific applications or systems.

- **Serializer:** A utility class focused on converting business objects into a format suitable for storage or transmission, commonly transforming them into a serialized form like JSON or XML. This process is crucial for data persistence or communication between different software components.

- **Deserializer:** A utility class that performs the reverse operation of a serializer. It converts serialized data, often in formats like JSON or XML, back into structured business objects. Deserialization is essential for reconstructing information after storage or transmission.

In summary, these terms collectively refer to tools used in software development to manage the conversion of data between raw formats and structured objects, facilitating tasks like storage, communication, and data manipulation. Abstraction is suggested to simplify discussions, especially when communicating with non-programmers, by using these terms without delving into technical details.




## Logical Call Stack
In the context of asynchronous programming, a logical call stack refers to a conceptual representation of the execution context of a program. Unlike a physical stack(which represents the actual function calls in memory) tied to a specific thread in synchronous programming, a logical stack in asynchronous programming is not bound to a single thread.

The logical stack is a way to visualize the flow of execution in asynchronous code. It helps keep track of the sequence of tasks and operations, especially when there are asynchronous calls that may not complete immediately. Asynchronous tasks can be paused, allowing other tasks to proceed, and then resumed when the asynchronous operation finishes.

This logical stack is essential for managing the state of the program during asynchronous operations, and it contributes to the efficiency of asynchronous programming by enabling concurrent execution of tasks without the need for multiple threads. It's a crucial concept in understanding how asynchronous code can be organized and executed in a non-blocking manner.



### Types of concurrency:
1. **Parallel Concurrency:**
    - Tasks truly execute simultaneously, often achieved through multiple processors or cores.
    - This type of concurrency is more about simultaneous execution.
2. **Sequential Concurrency (or Simulated Concurrency):**
    - Tasks appear to be executed simultaneously by interleaving their execution.
    - This is often achieved through techniques such as multitasking, where a system rapidly switches between different tasks.
