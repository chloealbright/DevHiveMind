-   The second part of the token is the payload, which contains the claims. Claims are statements about an entity (typically, the user) and additional data. There are three types of claims: registered, public, and private claims. 
    

-   Registered claims: These are a set of predefined claims which are not mandatory but recommended, to provide a set of useful, interoperable claims. Some of them are: iss (issuer), exp (expiration time), sub (subject), aud (audience), and others. 
    

-   Public claims: These can be defined at will by those using JWTs. But to avoid collisions they should be defined in the IANA JSON Web Token Registry or be defined as a URI that contains a collision resistant namespace. 
    

-   Private claims: These are the custom claims created to share information between parties that agree on using them and are neither registered or public claims. 
    

-   An example payload could be: { "sub": "1234567890", "name": "John Doe", "admin": true } The payload is then Base64Url encoded to form the second part of the JSON Web Token.