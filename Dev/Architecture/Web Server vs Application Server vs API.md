Web Server vs Application Server vs API 

web vs application server  

web server host a program doesn't necessary execute it because that isnt it,s primary function it is there to provide request to a end user in terms of accessing what you are hosting almost like a basic api but it isn't processing things in terms of running a program 

an example of this is going to a linux site that have different iso files for there distro versions  

web server process http request 

web app execute a program being hosted by web server 

so lets say you have tacflo api they just files until it is configured and added to something like Heroku thus it is a backend web app  because it is executing things 

web app server > API > web app server 

web app collect network packets combines packets to form input data 

api process data > executes > then create result set 

api is a contract or language between a source system and target system both system understand the data coming in and out in terms of format 

web app server formats data from network transfers sending data 

![[Web+Services+vs.+Web+Apps.jpg]]


A web server accepts and fulfills requests from clients for static content (i.e., HTML pages, files, images, and videos) from a website. Web servers handle HTTP requests and responses only. 

An application server exposes business logic to the clients, which generates dynamic content. It is a software framework that transforms data to provide the specialized functionality offered by a business, service, or application. Application servers enhance the interactive parts of a website that can appear differently depending on the context of the request. 

Web Server 

Deliver static content. 

Content is delivered using the HTTP protocol only. 

Serves only web-based applications. 

No support for multi-threading. 

Facilitates web traffic that is not very resource intensive. 

Application Server 

Delivers dynamic content. 

Provides business logic to application programs using several protocols (including HTTP). 

Can serve web and enterprise-based applications. 

Uses multi-threading to support multiple requests in parallel. 

Facilitates longer running processes that are very resource-intensive .








APIs, web servers, and application servers are all technologies that are commonly used in web development, but they serve different purposes.

An API, or application programming interface, is a set of rules and protocols that developers use to build software applications. APIs allow different applications to communicate with each other, enabling developers to integrate functionality from different systems into their own applications. APIs can be accessed over the internet, and are typically used to enable integrations between different systems or to expose data to external developers.

A web server, on the other hand, is a piece of software that runs on a server and serves web pages to clients, such as web browsers. When a client makes a request for a web page, the web server retrieves the appropriate content and sends it back to the client. Web servers are used to host websites and web applications, and can handle a variety of tasks such as serving static content, handling requests for dynamic content, and managing user sessions.

An application server is a software platform that provides a framework for developing and deploying applications. It typically includes components for managing database connections, security, and transaction processing, and provides a runtime environment for executing application code. Application servers are often used for building and deploying enterprise-level applications, such as customer relationship management (CRM) systems or supply chain management applications.

In summary, APIs are used to enable communication between different applications, web servers are used to serve web pages to clients, and application servers provide a framework for developing and deploying applications.