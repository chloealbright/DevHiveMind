---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[Status Codes.jpg]]

## Status code are stored in the body of responses  

-   200: OK One of the silent Status Codes/Server Response Codes, this means that the request was received and processed successfully. 
    
-   201:  Indicates that as a result of HTTP POST request, one or more new resources have been successfully created on the server. 
    
-   301: Moved Permanently The resource that was requested has been assigned a new permanent URI, and the server should be redirecting you there. 
    
-   302: Found The resource that was requested has been assigned a new temporary URI, and the server should be redirecting you there (but for future requests, it will try and use the original location again). 
    
-   401: Unauthorized For the request to be successfully processed, user authentication is required. If you’re seeing the 401 status code, this means the header in your request didn’t contain the authorization codes necessary to view the page content. 
    
-   404: Not Found The server was unable to find anything that matched the requested URI, and it is impossible to tell whether this is temporary or permanent. This is often used either when a server does not want to reveal specifically why a request was refused, or if no other response is applicable. 
    
-   500: Internal Server Error An error has occurred in the server itself which prevented it from completing the request. This is a generic, default message that is used when no other codes are applicable. When it comes to WordPress this is similar to the 'error establishing a database connection' message which you can see when the WordPress MySQL database gets tied up. 
    
-   503: Service Unavailable The server was unable to handle your HTTP request at the time. This could be due to server crash, server maintenance, server overload, or other reasons. It is generally temporary, and is a code that is normally put up until the whatever the problem was has been fixed.





## What status code to use when a parameter is missing in the query string? 

TLDR It's an HTTP 400 - Bad Request. 

It's a 400 because the user did not send the Required input field. 

why not 422 - because this case fits to 400. Keeping your consumers in mind, you shouldn't go to non-popular response codes if you don't really need to. 

Cases for HTTP 404: 

1) Url which the client requested is not existing in your server (usually this will be handled by your server. Application developer usually doesn't have to do anything unless you want a nice looking 404 page and SEO reasons). 

2) If it was a path parameter and client was looking for an entity with an id (for Example (/students/{id} and your application couldn't find such entity, you may respond with an HTTP 404. 

Let's say, user send the query parameter and you did not find any items matching the query param, make no mistake, it's still an HTTP 200 with body as an empty array or so (not a 404 unlike mentioned in the previous case)