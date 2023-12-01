---
tags: 
author:
  - jacgit18
Status: init
Started: 
EditDate: 
Relates:
---
## REST and API: Foundations of Web Development

### REST - Representational State Transfer

REST, or Representational State Transfer, is not a specific technology but a set of software architecture design constraints ensuring efficient, reliable, and scalable systems. It revolves around standardized methods, known as verbs, producing predictable outcomes by handling structured data, typically in JSON or XML formats. Representational State Transfer describes the transition between states, symbolizing the exchange of representations between applications and servers.

#### Transition from Traditional Websites to Web Applications

In contrast to traditional websites, where each page entails a complete HTML document, web applications follow a more resource-efficient approach. They download an application framework, style sheets, and JavaScript during the initial load. Subsequent navigation involves sending Universal Resource Identifier (URI) requests for specific web resources, allowing the application to dynamically update views without downloading entire documents.

#### Single Page Applications and REST Resource

This approach enables the creation of single-page applications and unified experiences across different platforms. For instance, platforms like LinkedIn utilize the same REST resource to provide data for both web browsers and mobile applications.

### API - Application Programming Interface

An API, or Application Programming Interface, serves as a set of features and rules within a software program, facilitating interactions with other software or hardware. In the context of REST APIs, it encompasses tools for accessing and manipulating REST resources through verbs like GET, POST, PUT, and DELETE.

#### Choosing Between GET and POST

While GET is suitable for simple cases with one or two parameters, POST is often recommended for more complex scenarios. This includes situations where input payloads are intricate, as seen in enterprise-grade applications, ensuring pragmatic adherence to RESTful principles without unnecessary complications.

#### API Design Considerations

API design reveals insights into the underlying program, encompassing elements like business models, product features, and occasional bugs. Despite being designed for program-to-program interactions, APIs are crafted to be understood and utilized by humans writing the code for those interactions.

In essence, the synergy of REST and API forms the backbone of modern web development, offering scalable, efficient, and user-friendly solutions for building dynamic applications and interfaces.