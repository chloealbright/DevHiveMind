---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
In the realm of RESTful web services, controllers play a pivotal role in enhancing the separation of concerns between servers and clients, fostering network efficiency, and facilitating the atomic implementation of complex operations.

To streamline this process, designate a controller resource for each distinct operation. Clients can then utilize the HTTP method POST to initiate a request and trigger the intended operation. If the outcome involves creating a new resource, respond with a 201 (Created) status code, accompanied by a Location header pointing to the URI of the newly created resource. In case of modifying existing resources, employ a 303 (See Other) status code with a Location URI for clients to fetch the modifications.

Error handling follows the guidelines outlined in "How to Return Errors." A controller, despite not always being evident in the domain model, serves as a resource capable of atomically effecting changes to other resources. This abstraction aids in reducing coupling between clients and servers, fostering flexibility.

Consider the scenario of merging two address books for a user. Instead of the inefficient approach of downloading and merging the entire address book on the client side, a more effective solution involves the creation of a controller resource. This resource enables clients to submit their address books to the server for a merge, avoiding network inefficiencies and promoting a more streamlined separation of concerns.






After merging the address books, the server redirects the client to the user’s updated address book. The client can fetch a copy of the merged address book, if necessary. 

Here is another example. Consider a bookstore where a store operator wants to reduce the pretax price of a book by 15 percent, and update the posttax price to reflect this discount. The server can offer the discount percentage as a resource, and clients can submit a PUT request to modify the current discount. The server can update the total price of the book as part of the same request. 

# Request to update the discount value 

PUT /book/1234/discount HTTP/1.1 

Host: [www.example.org](http://www.example.org/) 

Content-Type: application/x-www-urlencoded 

value=15 

# Response 

HTTP/1.1 204 No Content 

Now consider that the client wants to offer a 30-day free access to an online version of the same book along with this 15 percent discount. The server can maintain a collection of all books that are currently being offered in the 30-day free plan, and the client can submit a POST request to add this particular book to that collection. 

# Request to add the book to the list of offers 

POST /30dayebookoffers HTTP/1.1 

Host: [www.example.org](http://www.example.org/) 

Content-Type: application/x-www-urlencoded 

id=1234&from=2009-10-10&to=2000-11-10 

# Response 

HTTP/1.1 201 Created 

Location: [http://www.example.org/30dayebookoffer/1234](http://www.example.org/30dayebookoffer/1234) 

Content-Length: 0  

If your business case requires that these two changes be done atomically, you can employ a controller resource for this purpose. 

# Request to add a discount offer and 30-day free access 

POST /book/1234/discountebookoffer HTTP/1.1 

Host: [www.example.org](http://www.example.org/) 

Content-Type: application/x-www-urlencoded 

id=1234&discount=15&ebook_from=2009-10-10&ebook_to=2000-11-10 

# Response 

HTTP/1.1 303 See Other 

Location: [http://www.example.org/book/1234](http://www.example.org/book/1234) 

Content-Length: 0 

# Request to get the updated book 

GET /book/1234 HTTP/1.1 

Host: [www.example.org](http://www.example.org/) 

# Response 

HTTP/1.1 200 OK 

Content-Type: application/xml;charset=UTF-8 

<book xmlns:atom=" [http://www.w3.org/2005/Atom](http://www.w3.org/2005/Atom)"> 

 <id>urn:example:book:1234</id> 

 <atom:link rel="self" href=" [http://www.example.org/book/1234"/](http://www.example.org/book/1234%22/)> 

 ... 

 <discount>15</discount> 

 ... 

 <atom:link rel=" [http://www.example.org/rels/offer](http://www.example.org/rels/offer)" 

 href=" [http://www.example.org/30dayebookoffer/1234"/](http://www.example.org/30dayebookoffer/1234%22/)> 

 ... 

</book>  

In the response, the server includes a link to let clients discover the 30-day offer. If the client is presenting a user interface to end users, it can provide a link to this offer for users to navigate to. 

The key point to notice from these examples is the difficulty you might find in mapping operations in your application to the methods in the uniform interface. For example, in the discount example, the server identifies the current discount value as a resource so that clients can use PUT to update it. Similarly, the server identifies 30-day free electronic book offers as a collection and lets clients use POST to add a new book to this collection. But when it comes to combining these two tasks into a single request, a direct mapping to any HTTP method is not obvious. Controllers are most appropriate in such cases. 

For use cases like the previous one, do not use the method POST directly on the book resource because it could lead to tunneling. Tunneling occurs whenever the client is using the same method on a single URI for different actions. Here is an example of tunneling: 

# Request to add a discount offer 

POST /book/1234 HTTP/1.1 

Host: [www.example.org](http://www.example.org/) 

Content-Type: application/x-www-urlencoded 

op=updateDiscount&discount=15 

# Response 

HTTP/1.1 200 OK 

Content-Type: application/xml;charset=UTF-8 

<book xmlns:atom=" [http://www.w3.org/2005/Atom](http://www.w3.org/2005/Atom)"> 

 <id>urn:example:book:1234</id> 

 <atom:link rel="self" href=" [http://www.example.org/book/1234"/](http://www.example.org/book/1234%22/)> 

 ... 

 <discount>15</discount> 

 ... 

</book> 

# Request to add the book for 30-day offers 

POST /book/1234 HTTP/1.1 

Host: [www.example.org](http://www.example.org/) 

Content-Type: application/x-www-urlencoded 

op=30dayOffer&ebook_from=2009-10-10&ebook_to=2000-11-10 

# Response 

HTTP/1.1 200 OK 

Content-Type: application/xml;charset=UTF-8 

<book xmlns:atom=" [http://www.w3.org/2005/Atom](http://www.w3.org/2005/Atom)"> 

 <id>urn:example:book:1234</id> 

 <atom:link rel="self" href=" [http://www.example.org/book/1234"/](http://www.example.org/book/1234%22/)> 

 ... 

 <atom:link rel=" [http://www.example.org/rels/offer](http://www.example.org/rels/offer)" 

 href=" [http://www.example.org/30dayebookoffer/1234"/](http://www.example.org/30dayebookoffer/1234%22/)> 

</book>  

In the requests, the parameters op=updateDiscount and op=30dayOffer signify the operation. This leads to tunneling. 

Tunneling reduces protocol-level visibility (see How to Keep Interactions Visible) because the visible parts of requests such as the request URI, the HTTP method used, headers, and media types do not unambiguously describe the operation.