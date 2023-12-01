The server responds to a client with a 401 (Unauthorized) response status and provides information on how to authorize with a WWW-Authenticate response header containing at least one challenge. 

A client that wants to authenticate itself with the server can then do so by including an Authorization request header with the credentials. 

Usually a client will present a password prompt to the user and will then issue the request including the correct Authorization header.