-   CRUD not a part of response 
    
-   HTTP Status line consist of 
    
    -   HTTP version number showing the HTTP specification to which the server has tried to make the message comply. 
        
    -   HTTP  Status code 1xx to 5xx 
        
    -   A reason phrase, also known as status text, which is human-readable text that summarizes the meaning of the status code. 
        
    
-   HTTP Headers there are three one general, one for response, and the entity header that contains CRLF(Carriage Return - Line Feed) 
    
    -   The HTTP headers for a server's response contain information that a client can use to find out more about the response, and about the server that sent it. This information can assist the client with displaying the response to a user, with storing (or caching) the response for future use, and with making further requests to the server now or in the future. For example, the following series of headers tell the client when the response was sent, that it was sent by Apache, and that it is a text/html 
        
    -   In the case of an unsuccessful request, headers can be used to tell the client what it must do to complete its request successfully. 
        
    -   An empty line (that is, a CRLF alone) is placed in the response message after the series of HTTP headers, to divide the headers from the message body. 
        
    -   The web server uses the CRLF combination to understand when new HTTP header begins and another one ends. The CRLF can also tell a web application or user that a new line begins in a file or in a text block. The CRLF characters are a standard HTTP/1.1 message, so they are used by all web servers, including Apache, Microsoft IIS, and others. 
        
    
-   Message body 
    
    -   The message body of a response may be referred to for convenience as a response body. 
        
    -   Message bodies are used for most responses. The exceptions are where a server is responding to a client request that used the HEAD method (which asks for the headers but not the body of the response), and where a server is using certain status codes. 
        
    -   For a response to a successful request, the message body contains either the resource requested by the client, or some information about the status of the action requested by the client. For a response to an unsuccessful request, the message body might provide further information about the reasons for the error, or about some action the client needs to take to complete the request successfully. 
        
    
-   Bodies can be broadly divided into three categories: 
    
    -   Single-resource bodies, consisting of a single file of known length, defined by the two headers: Content-Type and Content-Length. 
        
    -   Single-resource bodies, consisting of a single file of unknown length, encoded by chunks with Transfer-Encoding set to chunked. 
        
    -   Multiple-resource bodies, consisting of a multipart body, each containing a different section of information. These are relatively rare.