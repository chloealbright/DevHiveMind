In the case of RESTful web services, controllers can help increase the separation of concerns between servers and clients, improve network efficiency, and let servers implement complex operations atomically. 

Designate a controller resource for each distinct operation. Let clients use the HTTP method POST to submit a request to trigger the operation. If the outcome of the operation is the creation of a new resource, return response code 201 (Created) with a Location header referring to the URI of the newly created resource. If the outcome is the modification of one or more existing resources, return response code 303 (See Other) with a Location with a URI that clients can use to fetch a representation of those modifications. If the server cannot provide a single URI to all the modified resources, return response code 200 (OK) with a representation in the body that clients can use to learn about the outcome. Handle errors as described in How to Return Errors. 

A controller is a resource that can atomically make changes to resources. The need for such a resource may not be apparent from your domain model, but it can help the server abstract complex business operations and provide a way for clients to trigger those operations. This in turn reduces coupling between clients and servers. 

Consider merging two address books for a user. A client on the mobile phone needs a way to synchronize all the contacts with the current address book on the server. One option is to use PUT as follows: 

Submit a GET request to the address book resource to download the complete address book from the server. 

Load the local list of contacts, and merge them with the address book downloaded from the server. 

Submit a PUT request to the address book resource to replace the entire address book with the merged one. 

This will do the job but with some limitations. For the client’s environment, downloading the entire address book and then merging it with the local list of contacts makes the client’s use of the network inefficient. Moreover, some users may have very large address books on the server, and not all fields in the address book may be relevant for the client. The client may not have enough computing power for handling the merge operation. More importantly, the application logic to merge entries in the address book belongs to the server, not the client. Expecting clients to deal with this task results in the duplication of code and poor separation of concerns. 

Here is another option: 

Get each address in the address book from the server. 

If that address matches with an entry in the local storage, merge it, and update it by submitting a PUT request. 

If there is a new contact in the local storage that does not exist on the server, submit a POST request to the address book to add it. 

This approach has the additional drawback of network chattiness, which again is not suitable for the client’s constrained environment such as a mobile phone. 

A more effective solution is to employ a controller resource to solve this problem. For this example, design a controller resource, and allow the client to submit the address book to the server for a merge. 

# Request to merge an address book 

POST /user/smith/address_merge HTTP/1.1 

Host: [www.example.org](http://www.example.org/) 

Content-Type: text/csv;charset=UTF-8 

John Doe, 1 Main Street, Seattle, WA 

Jane Doe, 100 North Street, Los Angeles, CA 

... 

# Response 

HTTP/1.1 303 See Other 

Location: [http://www.example.org/user/smith/address_book](http://www.example.org/user/smith/address_book) 

Content-Type: text/html;charset=UTF-8 

<html> 

 <body> 

 <p>See <a href=" [http://www.example.org/user/smith/address_book">address](http://www.example.org/user/smith/address_book%22%3Eaddress) 

 book</a> for the merged address book.</p> 

 </body> 

</html>  

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