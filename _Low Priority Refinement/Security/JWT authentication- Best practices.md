---
tags: 
author: 
Status: 
Started: 
EditDate: 
Relates:
---
How to expire a single JWT token 

How do you invalidate a single token? A no-effort solution is to change the server secret key, which invalidates all tokens. However, this is not ideal for users, who may have their tokens expired for no reason. 

One way to do it is to add a property to your user object in the server database to reference the date and time at which the token was created. 

A token automatically stores this value in the iat property. Every time you check the token, you can compare its iat value with the server-side user property. 

 iat (issued at) claim identifies the time at which the JWT was issued 

To invalidate the token, just update the server-side value. If iat is older than this, you can reject the token. 

Another way to achieve this is by establishing a blacklist in your database cached in memory (or, even better, a whitelist). 

How to securely store JWTs in a cookie 

A JWT needs to be stored in a safe place inside the user’s browser. If you store it inside localStorage, it’s accessible by any script inside your page. This is as bad as it sounds; an XSS attack could give an external attacker access to the token. 

To reiterate, whatever you do, don’t store a JWT in local storage (or session storage). If any of the third-party scripts you include in your page is compromised, it can access all your users’ tokens. 

To keep them secure, you should always store JWTs inside an httpOnly cookie. This is a special kind of cookie that’s only sent in HTTP requests to the server. It’s never accessible (both for reading or writing) from JavaScript running in the browser. 

Using JWT for SPA authentication 

JWTs can be used as an authentication mechanism that does not require a database. The server can avoid using a database because the data store in the JWT sent to the client is safe. 

Using JWT to authorize operations across servers 

Say you have one server where you are logged in, SERVER1, which redirects you to another server SERVER2 to perform some kind of operation. 

SERVER1 can issue you a JWT that authorizes you to SERVER2. Those two servers don’t need to share a session or anything to authenticate you. The token is perfect for this use case.