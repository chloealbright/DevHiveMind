---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[GetImage (16).png]]


In authentication, when the user successfully logs in using their credentials, a JSON Web Token will be returned. Since tokens are credentials, great care must be taken to prevent security issues. In general, you should not keep tokens longer than required. 

-   Whenever the user wants to access a protected route or resource, the user agent should send the JWT, typically in the Authorization header using the Bearer schema. The content of the header should look like the following: 
    
    -   Authorization: Bearer <"token">
        
    
-   This can be, in certain cases, a stateless authorization mechanism. The server's protected routes will check for a valid JWT in the Authorization header, and if it's present, the user will be allowed to access protected resources. If the JWT contains the necessary data, the need to query the database for certain operations may be reduced, though this may not always be the case. 
    

-   Note that if you send JWT tokens through HTTP headers, you should try to prevent them from getting too big. Some servers don't accept more than 8 KB in headers. If you are trying to embed too much information in a JWT token, like by including all the user's permissions, you may need an alternative solution, like Auth0 Fine-Grained Authorization. 
    

-   If the token is sent in the Authorization header, Cross-Origin Resource Sharing (CORS) won't be an issue as it doesn't use cookies. 
    

-    Authorization Code Flow Steps 
    
    -   Client prepares an Authentication Request containing the desired request parameters. 
        
    -   Client sends the request to the Authorization Server. 
        
    -   Authorization Server Authenticates the End-User. 
        
    -   Authorization Server obtains End-User Consent/Authorization. 
        
    -   Authorization Server sends the End-User back to the Client with an Authorization Code. 
        
    -   Client requests a response using the Authorization Code at the Token Endpoint. 
        
    -   Client receives a response that contains an ID Token and Access Token in the response body. 
        
    -   Client validates the ID token and retrieves the End-User's Subject Identifier. 
        
[https://openid.net/specs/openid-connect-core-1_0.html#CodeFlowAuth](https://openid.net/specs/openid-connect-core-1_0.html#CodeFlowAuth)