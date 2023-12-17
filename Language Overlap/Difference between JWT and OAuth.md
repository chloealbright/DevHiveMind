---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Firstly, we have to differentiate JWT and OAuth. 

Basically, JWT is a token format. 

OAuth is an standardised authorization protocol that can use JWT as a token. 

OAuth uses server-side and client-side storage. If you want to do real logout you must go with OAuth2. Authentication with JWT token can not logout actually. Because you don’t have an Authentication Server that keeps track of tokens. 

If you want to provide an API to 3rd party clients, you must use OAuth2 also. OAuth2 is very flexible. JWT implementation is very easy and does not take long to implement. If your application needs this sort of flexibility, you should go with OAuth2. But if you don’t need this use-case scenario, implementing OAuth2 is a waste of time. 

JWT (JSON Web Tokens)- It is just a token format. JWT tokens are JSON encoded data structures contains information about issuer, subject (claims), expiration time etc. It is signed for tamper proof and authenticity and it can be encrypted to protect the token information using symmetric or asymmetric approach. JWT is simpler than SAML 1.1/2.0 and supported by all devices and it is more powerful than SWT(Simple Web Token). 

OAuth2 — OAuth2 solve a problem that user wants to access the data using client software like browse based web apps, native mobile apps or desktop apps. OAuth2 is just for authorization, client software can be authorized to access the resources on-behalf of end user using access token. 

Security protocols like OAuth2 use JWT tokens to secure APIs. 

At this point, most, but not all, Identity Provider vendors are using JWT tokens as OAuth2 Access Tokens. 

OpenID Connect — 

“OpenID Connect is a simple identity layer on top of the OAuth 2.0 protocol. It allows Clients to verify the identity of the End-User based on the authentication performed by an Authorization Server, as well as to obtain basic profile information about the End-User in an interoperable and REST-like manner.” 

As mention in the definition, OpenID Connect builds on top of OAuth2 and add authentication. OpenID Connect add some constraint to OAuth2 like UserInfo Endpoint, ID Token, discovery and dynamic registration of OpenID Connect providers and session management. JWT is the mandatory format for the token. 

OpenID Connect uses JWT tokens to authenticate web applications, but stores the token in a cookie. But they are different from the session cookies which is sent to the user in the request automatically whenever a user logs in. 

CSRF protection — You don’t need implement the CSRF protection if you do not store token in the browser’s cookie.


## JSON Web Tokens vs Oauth

A JWT technically is a mechanism to verify the owner of some JSON data 

It’s an encoded string, which is URL safe, that can contain an unlimited amount of data (unlike a cookie), and it’s cryptographically signed. 

When a server receives a JWT, it can guarantee the data it contains can be trusted because it’s signed by the source. No middleman can modify a JWT once it’s sent. 

It’s important to note that a JWT guarantees data ownership but not encryption; the JSON data you store into a JWT can be seen by anyone that intercepts the token, as it’s just serialized, not encrypted. 

What is OAuth 

To begin at a high level, OAuth is not an API or a service: it’s an open standard for authorization and anyone can implement it. 

More specifically, OAuth is a standard that apps can use to provide client applications with “secure delegated access”. OAuth works over HTTPS and authorizes devices, APIs, servers, and applications with access tokens rather than credentials. 

Simply put: it’s a standard to securely access stuff with randomized tokens. 

OAuth Grant Types 

There are different flows written into the specification for how those randomized tokens are actually generated. This can lead to a lot of confusion because some flows are much simpler than others (also less secure). 

The specification describes five grants for acquiring an access token: 

Authorization code grant 

This flow redirects you to log in directly with a 3rd party, meaning the client never gets access to your username/password that you type in. That very important secret is not shared in another database somewhere, it remains between you and the credential provider you trust (such as Facebook, although not sure I would trust them too much). 

That 3rd party provider that you login with generates your JWT that the client actually uses to fetch data for you. Based upon the configuration, in most cases, it’s a short-lived Access Token (Access Token is a JWT) meaning the client only can act on your behalf for a certain time period. 

Implicit grant 

Resource owner credentials grant 

Client credentials grant 

Refresh token grant