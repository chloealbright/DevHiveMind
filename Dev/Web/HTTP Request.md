-   Process of going to website  Request is made from application layer and might hit transport and session layer and sent to DNS 
    
-   When a request happens we connect to a DNS (domain name server)  recursive resolver. The resolver then queries a DNS root nameserver. 
    
    -   The root server is the first step in translating (resolving) human readable host names into IP addresses. it responds to the resolver with a query of the address of a Top-Level Domain (.COM), which stores the information for its domains. When searching for example.com, our request is pointed toward the .com TLD. The resolver then makes a request to the .com TLD. 
        
    
    -   The TLD server then search for  the IP address of the domain’s nameserver, example.com. 
        
    -   This final nameserver can be thought of as a dictionary on a rack of books, in which a specific name can be translated into its definition. The authoritative nameserver is the last stop in the nameserver query. If the authoritative name server has access to the requested record, it will return the IP address for the requested hostname back to the DNS Recursor (the librarian) that made the initial request. 
        
    -   [https://www.cloudflare.com/learning/dns/what-is-dns/](https://www.cloudflare.com/learning/dns/what-is-dns/) 
        
    
    -   The request has the first line with the CRUD method being used then the path component of the URL for the request. The path identifies the resource on the server. Then the HTTP version number, showing the HTTP specification to which the client has tried to make the message comply. 
        

-   Then we have the headers 
    

-   Finally we the message body. Message bodies are appropriate for some request methods and inappropriate for others. For example, a request with the POST method, which sends input data to the server, has a message body containing the data. A request with the GET method, which asks the server to send a resource, does not have a message body. 
    

-   Bodies can be broadly divided into two categories: 
    
    -   Single-resource bodies, consisting of one single file, defined by the two headers: Content-Type and Content-Length. 
        
    -   Multiple-resource bodies, consisting of a multipart body, each containing a different bit of information. This is typically associated with HTML Forms. 
        
    
-   Request.redirect 
    
    -   The redirect read-only property of the Request interface contains the mode for how redirects are handled. 
        
    -   A RequestRedirect enum value, which can be one the following strings: the default value of follow, error, or manual 
        

Debug with [res.text](https://developer.mozilla.org/en-US/docs/Web/API/Response/text) 

Client Request(sends CRUD)-> exchange of data <-(returns body)Response 

CRUD represents the four basic functions of working with data in code we make and store a request(CRUD) in a response variable and handle response you get back  

Request can be resolved(accepted) or rejected and you may create test case to handle and control flow of your data/code 

-   Create(Add) –> POST - method sends data to the server. The type of the body of the request is indicated by the Content-Type header. requests are never cached the request will not remain in the browser history No restriction on data length. 
    
    -   Create means create-unless-exists: If the resource already exists, fail this operation. If two valid but different create operations arrive at once, at least one must fail. 
        
    
-   When to Use POST 
    
    -   To create a new resource, using the resource as a factory as described in How to Create Resources Using POST 
        
    -   To modify one or more resources via a controller resource as described in When and How to Use Controllers to Operate on Resources 
        
    -   To run queries with large inputs as described in How to Support Query Requests with Large Inputs 
        
    -   To perform any unsafe or nonidempotent operation when no other HTTP method seems appropriate 
        
    
-   POST in general is unsafe and not Idempotent by nature 
    
    -   Read(Retrieve) –> GET - method requests a representation of the specified resource. Requests using GET should only retrieve data. / 
        
    -    Read is just read: Get the most recent value or null if it doesn’t exist. 
        
    
-   When to Use GET 
    

-   The infrastructure of the Web strongly relies on the idempotent and safe nature of GET. Clients count on being able to repeat GET requests without causing side effects i.e altering data & safe being Read-Only. Caches depend on the ability to serve cached representations without contacting the origin server. 
    
-   No body but has params 
    

-   Most abuse of GET happens in the form of using this method for unsafe operations. Here are some examples: 
    
    -   # Bookmark a page GET /bookmarks/add_bookmark?href=http%3A%2F%2F [www.example.org%2F2009%2F10%2F10%2Fnotes.html](http://www.example.org%2F2009%2F10%2F10%2Fnotes.html/) HTTP/1.1 
        
    -   # Add an item to a shopping cart GET /add_cart?pid=1234 HTTP/1.1 
        
    -   # Send a message GET /messages/send?message=I%20am%20reading HTTP/1.1 
        
    -   # Delete a note GET /notes/delete?id=1234 HTTP/1.1 
        
    
-   The consequences of this difference can be severe depending on the application. For example, a tool routinely performing health checks on a server by periodically submitting a GET request using the fourth URI shown previously will delete a note. 
    

-   If you must use GET for such operations, take the following precautions: 
    
    -   Make the response noncacheable by adding a Cache-Control: no-cache header. 
        
    -   Ensure that any side effects are benign and do not alter business-critical data. 
        
    -   Implement the server such that those operations are repeatable (i.e., idempotent). 
        
    

These steps may help reduce the impact of errors for certain but not all operations. The best course of action is to avoid abusing GET. 

-   HEAD -> - method is identical to GET except that the server MUST NOT return a message-body in the response. The metainformation contained in the HTTP headers in response to a HEAD request SHOULD be identical to the information sent in response to a GET request. This method can be used for obtaining metainformation about the entity implied by the request without transferring the entity-body itself. This method is often used for testing hypertext links for validity, accessibility, and recent modification. 
    

-   The response to a HEAD request MAY be cacheable in the sense that the information contained in the response MAY be used to update a previously cached entity from that resource. If the new field values indicate that the cached entity differs from the current entity (as would be indicated by a change in Content-Length, Content-MD5, ETag or Last-Modified), then the cache MUST treat the cache entry as stale. 
    

-   Update(Replace) –> PUT - request method creates a new resource or replaces a representation of the target resource with the request payload.  
    
    -   Update means update-if-exists: Overwrite the current value with the provided new value wholesale. If the resource doesn’t exist, fail this operation. If two valid but different update operations arrive at once, accept both, but pick a “latest” one to serve all future reads. 
        
    
-   The difference between PUT and POST is that PUT is idempotent: calling it once or several times successively has the same effect (that is no side effect), where successive identical POST may have additional effects, like passing an order several times. 
    

-   When to Use PUT to Create New Resources 
    
    -   You can use either HTTP POST or HTTP PUT to create new resources. This recipe discusses when to use PUT to create new resources. 
        
    -   Use PUT to create new resources only when the client can control part of the URI. For instance, a storage server may allocate a root URI for each client and let clients create new resources using that root URI as a root directory on a filesystem. Otherwise, use POST. 
        
    -   When using POST to create new resources, the server decides the URI for the newly created resource. It can control its URI naming policies along with any network security-level configurations. You can still let servers use information in the representation (such as the Slug header) while generating URIs for new resources. 
        
    -   When you support PUT to create new resources, clients must be able to assign URIs for resources. When using this method to create new resources, take the following into consideration: 
        
    -   To let clients assign URIs, the server needs to explain to clients how URIs on the server are organized, what kind of URIs are valid, and what kind are not. 
        
    

You also need to consider any security and filtering rules set up on servers based on URI patterns and may want to restrict clients to use a narrow range of URIs while creating new URIs. 

PATCH -> request method applies partial modifications to a resource. 

PATCH is somewhat analogous to the "update" concept found in CRUD (in general, HTTP is different than CRUD, and the two should not be confused). 

-   A PATCH request is considered a set of instructions on how to modify a resource. Contrast this with PUT; which is a complete representation of a resource. 
    
    -   A PATCH is not necessarily idempotent, although it can be. Contrast this with PUT; which is always idempotent. The word "idempotent" means that any number of repeated, identical requests will leave the resource in the same state. For example if an auto-incrementing counter field is an integral part of the resource, then a PUT will naturally overwrite it (since it overwrites everything), but not necessarily so for PATCH. 
        
    

[[Delete]]

[[Other Methods]]

Clients use the POST method to invoke the function-oriented controller resources. A POST request message may include both headers and a body as inputs to a controller resource’s function. 

HTTP designates POST as semantically open-ended. It allows the method to take any action, regardless of its repeatability or side effects. This makes POST the clear choice to be paired with the equally unrestricted controller resources. 

Our REST API designs use POST, along with a targeted controller resource, to trigger all operations that cannot be intuitively mapped to one of the other core HTTP methods. In other words, the POST method should not be used to get, store, or delete resources—HTTP already provides specific methods for each of those functions. 

HTTP calls the POST request method unsafe and non-idempotent, which means that its outcome is unpredictable and not guaranteed to be repeatable without potentially undesirable side effects. For example, a resubmitted web form that uses POST might run the risk of double billing a user’s credit card. Controller resources trade a degree of transparency and robustness for the sake of flexibility. 

The example below demonstrates how a controller can be executed using the POST request method: 

-   POST /alerts/245743/resend 
    
-   This is the second use of POST in the design of REST APIs. This use case resembles the fairly common concept of a runtime system’s “PostMessage” mechanism, which allows functions to be invoked across some sort of boundary.