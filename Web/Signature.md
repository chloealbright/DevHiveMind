---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
-   To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that. 
    

-   For example if you want to use the HMAC SHA256 algorithm, the signature will be created in the following way: 
    
    -   HMACSHA256(base64UrlEncode(header) + "." +          base64UrlEncode(payload),                   secret) 
        
    
-   The signature is used to verify the message wasn't changed along the way, and, in the case of tokens signed with a private key, it can also verify that the sender of the JWT is who it says it is.