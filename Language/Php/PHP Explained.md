---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
PHP uses its own engine called Zend Engine which is a compiler and runtime environment for the PHP scripting language and consists of the Zend Virtual Machine, which is composed of the Zend Compiler and the Zend Executor, that compiles and executes the PHP code. 

Node uses V8 engine 

PHP provides ready to install tools for server  

Node it is a JavaScript runtime in itself 

PHP is synchronous  

Node is asynchronous 

PHP is slower and node is faster and lighter 

PHP functions on Apache/ISS 

Node doesn't need a dedicated server but Express is generally used 

Package management is one of the gray areas in PHP and has been a topic for debate over the years. There has never been a standard package manager that PHP developers could use to install reusable PHP libraries and components. PEAR was a widely-used package manager for PHP, but can now be thought to be deprecated. However, with initiatives like PHP-FIG and Composer, the PHP community has finally got a reliable system. Composer can be considered the standard package manager for PHP. 

On the other hand, Node.js already provides NPM (Node Package Manager), a package management system. It is easy to use NPM to manage Node packages in your application. In fact, NPM has become the de facto standard for sharing reusable JavaScript components. 

[https://getcomposer.org](https://getcomposer.org/)  

Traditionally, PHP has been paired with relational database systems (RDBMS) like MySQL, PostgreSQL, MS SQL, and the like. Among them, MySQL is the most popular database for building PHP websites. As we discussed earlier, it’s a part of the popular open-source stack LAMP (Linux, Apache, MySQL, and PHP). Having said that, it’s also possible to use NoSQL databases like MongoDB with PHP. 

Node.js is best suited to work with NoSQL databases like MongoDB and CouchDB. It can also work with SQL databases, but most developers prefer NoSQL databases with Node.js. With built-in JSON support, Node.js works exceedingly well with NoSQL databases. MongoDB is the most common choice—that's the M in MEAN. 

As we discussed earlier, Node.js is asynchronous by nature, and thus, it has superior performance on tasks with a lot of connections or a lot of time-consuming I/O or network operations. However, it’s important to note that Node.js is single-threaded by default, so a CPU-intensive operation in one request will block all connections to the server until it is complete.





Over the years, we’ve seen that PHP is used to build a wide range of applications that may range from a personal blog website to full-fledged enterprise-level applications. Generally, we would use PHP to build applications that don't interact much with other servers and don't use a client-side JavaScript framework. One of the main things that might dictate the use of PHP is if you want to use a CMS or framework that is built with PHP: for example WordPress or Laravel. 

On the other hand, Node.js is really useful for building applications that deal with real-time data and must be faster and scalable. Use cases like chat applications, real-time statistics display applications, and logging applications are ideal candidates to implement with Node.js. Apart from that, if you are building SPAs (Single Page Applications) that are highly interactive with a server and fetch the majority of their data via APIs, Node.js should be your first choice. 

Also, if you’re going to use front-end technologies like React, AngularJS, or Vue.js, it’s preferred to use Node.js as your back-end. It’s really useful to be able to work with the same language on the front-end and back-end. The JavaScript and Node ecosystem is set up to support using the same language across the whole stack. 

So it’s really up to you to go through the requirements of your application and decide whether PHP or Node is the best fit for you!