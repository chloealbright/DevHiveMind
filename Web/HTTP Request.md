---
tags: 
author:
  - jacgit18
Comments: 
Status: Refinement
Started: 
EditDate: 
Relates:
---
![[Http Request Method.gif]]


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
        

Debug with *[res.text](https://developer.mozilla.org/en-US/docs/Web/API/Response/text)*

Client Request(sends CRUD)-> exchange of data <-(returns body)Response 

CRUD represents the four basic functions of working with data in code we make and store a request(CRUD) in a response variable and handle response you get back  

Request can be resolved(accepted) or rejected and you may create test case to handle and control flow of your data/code 


- HEAD -> - method is identical to GET except that the server MUST NOT return a message-body in the response. The metainformation contained in the HTTP headers in response to a HEAD request SHOULD be identical to the information sent in response to a GET request. This method can be used for obtaining metainformation about the entity implied by the request without transferring the entity-body itself. This method is often used for testing hypertext links for validity, accessibility, and recent modification. 


- The response to a HEAD request MAY be cacheable in the sense that the information contained in the response MAY be used to update a previously cached entity from that resource. If the new field values indicate that the cached entity differs from the current entity (as would be indicated by a change in Content-Length, Content-MD5, ETag or Last-Modified), then the cache MUST treat the cache entry as stale. 


[[GET]]


[[POST]]

[[PATCH]]

[[PUT]]

[[DELETE]]

[[Other Methods]]



