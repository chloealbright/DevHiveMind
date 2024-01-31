---
tags: 
author:
  - jacgit18
Comments: 
Status: Capture
Started: 
EditDate: 
Relates: "[[HTTP Request]]"
---
![[Request Structure.png]]

## fetch (defaults to GET) 

The fetch() method takes one mandatory argument, the path to the resource you want to fetch. It returns a Promise that Resolves to the Response to that request — as soon as the server responds with headers — even if the server response is an HTTP error status. 

Fetch defaults to a HTTP get request but if you pass in a second param with custom config with a post method the fetch becomes a post 

The promise resolves to the Response object representing the response to your request. The promise does not reject on HTTP errors — it only rejects on network errors. You must use then handlers to check for HTTP errors. 

A fetch() promise only rejects when a network error is encountered (which is usually when there’s a permissions issue or similar). A fetch() promise does not reject on HTTP errors (404, etc.). Instead, a then() handler must check the Response.ok and/or Response.status properties. 

The fetch() method is controlled by the connect-src directive of Content Security Policy rather than the directive of the resources it's retrieving. 

-   fetch takes in a url and an optional  object containing any custom settings that you want to apply to the request. The possible options are: 
    
    -   url/resource: required This defines the resource that you wish to fetch. 
        
-   init Optional: An object containing any custom settings that you want to apply to the request. The possible options are: 
    
    -   Method - The request method, e.g., GET, POST. Note that the Origin header is not set on Fetch requests with a method of HEAD or GET. (This behavior was corrected in Firefox 65 — see bug 1508661). 
        
    
    -   Headers - Any headers you want to add to your request, contained within a Headers object or an object literal with String values. Note that some names are forbidden. 

    - Blob - Binary large object
	    - The Blob object represents a blob, which is a file-like object of immutable, raw data; they can be read as text or binary data, or converted into a ReadableStream so its methods can be used for processing the data.
	
	    - Blobs can represent data that isn't necessarily in a JavaScript-native format. The File interface is based on Blob, inheriting blob functionality and expanding it to support files on the user's system.

like you can convert image to data
    
    -   Body - Any body that you want to add to your request: this can be a Blob, BufferSource, FormData, URLSearchParams, USVString, or ReadableStream object. Note that a request using the GET or HEAD method cannot have a body. 
        
    
    -   Mode - The mode you want to use for the request, e.g., cors, no-cors, or same-origin. 
        
    
    -   Credentials - Controls what browsers do with credentials (cookies, HTTP authentication entries, and TLS client certificates). Must be one of the following strings: 
        
        -   Omit - Tells browsers to exclude credentials from the request, and ignore any credentials sent back in the response (e.g., any Set-Cookie header). 
            
        -   Same-origin - Tells browsers to include credentials with requests to same-origin URLs, and use any credentials sent back in responses from same-origin URLs. 
            
        -   Include - Tells browsers to include credentials in both same- and cross-origin requests, and always use any credentials sent back in responses. 
            
        
    -   Cache - A string indicating how the request will interact with the browser’s HTTP cache. The possible values, default, no-store, reload, no-cache, force-cache, and only-if-cached, are documented in the article for the cache property of the Request object. 
        
    
    -   Redirect  - URL redirection, also known as URL forwarding, is a technique to give more than one URL address to a page, a form, or a whole Web site/application. HTTP has a special kind of response, called a HTTP redirect, for this operation. 
        
        -   Redirects accomplish numerous goals:  
            
            -   Temporary redirects during site maintenance or downtime 
                
            -   Permanent redirects to preserve existing links/bookmarks after changing the site's URLs, progress pages when uploading a file, etc. 
                
        -   Principle 
            
            -   In HTTP, redirection is triggered by a server sending a special redirect response to a request. Redirect responses have status codes that start with 3, and a Location header holding the URL to redirect to. 
                
            -   When browsers receive a redirect, they immediately load the new URL provided in the Location header. Besides the small performance hit of an additional round-trip, users rarely notice the redirection. 
                
            
        -   How to handle a redirect response: 
            
            -   follow: Automatically follow redirects. Unless otherwise stated the redirect mode is set to follow 
                
            -   error: Abort with an error if a redirect occurs. 
                
            -   manual: Caller intends to process the response in another context. See WHATWG fetch standard for more information. 
                
    -   [https://developer.mozilla.org/en-US/docs/Web/HTTP/Redirections](https://developer.mozilla.org/en-US/docs/Web/HTTP/Redirections) 
        
    -   Referrer - A USVString specifying the referrer of the request. This can be a same-origin URL, about:client, or an empty string. 
        
    
    -   Referrer-Policy - Specifies the referrer policy to use for the request. May be one of no-referrer, no-referrer-when-downgrade, same-origin, origin, strict-origin, origin-when-cross-origin, strict-origin-when-cross-origin, or unsafe-url. 
        
    
    -   Integrity - Contains the subresource integrity value of the request (e.g., sha256-BpfBw7ivV8q2jLiT13fxDYAe2tJllusRSZ273h2nFSE=). 
        
    
    -   Keepalive - The keepalive option can be used to allow the request to outlive the page. Fetch with the keepalive flag is a replacement for the Navigator.sendBeacon() API. 
        
    
    -   Signal - An AbortSignal object instance; allows you to communicate with a fetch request and abort it if desired via an AbortController.  
        
    
    -   Return value - A Promise that resolves to a Response object. 
        
    
    -   Exceptions - [https://developer.mozilla.org/en-US/docs/Web/API/fetch#exceptions](https://developer.mozilla.org/en-US/docs/Web/API/fetch#exceptions) 
        
    
-   [https://developer.mozilla.org/en-US/docs/Web/API/FormData](https://developer.mozilla.org/en-US/docs/Web/API/FormData)