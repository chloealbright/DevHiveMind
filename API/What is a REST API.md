---
tags:
  - API
  - REST
  - web
author:
  - jacgit18
  - chatgpt
Comments: This documentation discusses REST API.
Status: Done
Started: 
EditDate: 2024-03-02
Relates:
---
An API, or Application Programming Interface, acts as a set of features and rules within a software program, facilitating interactions with other software or hardware. In the context of REST APIs, it provides public and private tools for accessing and manipulating REST resources through verbs such as GET, POST, PUT, and DELETE.

### API vs Servers
APIs are deployed on servers, but it's important to understand that a server's capabilities extend far beyond hosting APIs. For instance, a server might be configured to perform regular tasks such as backing up your database every 24 hours, showcasing its versatile role in both maintenance and functionality.

APIs, fundamentally, are designed to implement protocols that enable data transfer between two or more applications. This communication is essential for integrating and extending the capabilities of different software systems.

Traditionally, a server refers to the physical hardware that hosts applications, often tasked with critical back-end functions like database access, and facilitating interactions (via APIs) with other server-hosted applications. This highlights a server's pivotal role in the underlying infrastructure that supports application functionalities.

It's crucial to note that the scope of APIs is not confined to server-side applications. APIs serve as a communication protocol between any two applications, regardless of where they are hosted. This broad applicability of APIs underscores their importance in building interconnected, efficient, and scalable digital ecosystems.

#### Understanding Declarative vs Imperative APIs
Declarative("what) APIs are the key pillar of what many vendors call “policy” or “intent-based” networking. 

A declarative API is a desired state system. You provide a certain state you want the system to create. You don't care about all the steps needed to achieve that state. You just tell the system: "Please make sure that the state I provide will be there." 

I haven’t seen a single API call that would tell the server how to do stuff. They always tell the server what we want to get done. Admittedly, some API calls are more abstracted than others, but that’s a different story. 

##### Conclusion: All API calls are declarative

In much the same way that the imperative mood in natural languages expresses commands, an imperative program consists of commands for the computer to perform. All Create, Update, or Delete (three quarters of CRUD) API calls are executed to change the state of the system. 

In computer science, imperative programming is a programming paradigm that uses statements that change a program’s state. In much the same way that the imperative mood in natural languages expresses commands, an imperative program consists of commands for the computer to perform. 

All Create, Update, or Delete (three quarters of CRUD) API calls are executed to change the state of the system. Admittedly, some API calls tell the system what to do in vague manner, while others are more precise. 

##### Conclusion: Many API calls are imperative 

Using declarative and imperative to describe API calls makes as little sense as intent-based networking (TL&DR: every configuration is an expression of our intent). 

What really matters is the level of abstraction an API call provides, and the atomicity of the requested operation. 



### Representational State Transfer (REST)

REST, or Representational State Transfer, is not a specific technology but a set of software architecture design constraints aimed at ensuring efficient, reliable, and scalable systems. It centers around standardized methods, known as verbs, to produce predictable outcomes by handling structured data, typically in JSON or XML formats. Representational State Transfer describes the transition between states, symbolizing the exchange of representations between applications and servers.

#### Transition from Traditional Websites to Web Applications

Unlike traditional websites, where each page involves a complete HTML document, web applications follow a more resource-efficient approach. They download an application framework, style sheets, and JavaScript during the initial load. Subsequent navigation involves sending Universal Resource Identifier (URI) requests for specific web resources, enabling the application to dynamically update views without downloading entire documents.

#### Single Page Applications and REST Resources

This approach facilitates the creation of single-page applications and unified experiences across different platforms. For example, platforms like LinkedIn utilize the same REST resource to provide data for both web browsers and mobile applications.

#### API Design Considerations

While designed for program-to-program interactions, APIs are crafted to be understood and utilized by humans writing the code for those interactions. API design reveals insights into the underlying program, encompassing elements like business models, product features, and occasional bugs.

In essence, the synergy of REST and API forms the backbone of modern web development, offering scalable, efficient, and user-friendly solutions for building dynamic applications and interfaces.

## RESTful Routing
### RESTful Essence
- The addition of "ful" not only emphasizes completeness but also promotes the adoption of this technology/pattern by framing it within a word with positive connotations.

### Resource-Centric Approach
- At its core, RESTful routing revolves around the concept of resources representing entities in the system, such as articles, users, or any data that can undergo CRUD operations.

### CRUD Operations via HTTP
- The fundamental objective is to enable CRUD operations (Create, Read, Update, Delete) on these resources using the HTTP protocol, with each operation corresponding to a specific HTTP verb:
  - **GET:** Retrieve data.
  - **POST:** Create new data.
  - **PUT:** Update existing data.
  - **DELETE:** Remove data.

### Utilization of HTTP Verbs
- The strength of RESTful routing lies in its alignment with HTTP verbs, allowing developers to express actions succinctly and intuitively.

### Consistent and Elegant URLs
- RESTful routing involves creating URLs that are not only consistent but also aesthetically pleasing, promoting readability and maintainability for an overall elegant design.

In essence, RESTful routing provides a structured and intuitive approach to designing APIs and web applications. By aligning with REST principles, developers can create powerful systems adhering to standardized and efficient patterns, fostering best practices in the ever-evolving landscape of web development. Embrace the RESTful philosophy, and let the elegance of your APIs mirror the simplicity and power of the underlying principles.