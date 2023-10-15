<mark style="background: #FFF3A3A6;">JSON Web Token structure: xxxxx.yyyyy.zzzzz</mark>

- Header.Payload.Signature 
    

-   The header typically consists of two parts: the type of the token, which is JWT, and the signing algorithm being used, such as HMAC SHA256 or RSA. 
    

-   For example: {   "alg": "HS256",   "typ": "JWT"  } this JSON is Base64Url encoded to form the first part of the JWT.