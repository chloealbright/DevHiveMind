---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
### When to Use JWT (JSON Web Tokens)

#### Authentication
After a successful login, an ID token (JWT) is returned, following OpenID Connect specifications.

#### Authorization
JWTs are commonly employed for secure authorization, with subsequent requests including the JWT to grant access to permitted routes, services, and resources. They are especially favored in Single Sign-On for their efficiency and cross-domain compatibility.

#### Information Exchange
Securely transmit information between parties using signed JWTs. Public/private key pairs ensure sender authenticity, and the signature verifies content integrity.

**JSON Web Token Structure: xxxxx.yyyyy.zzzzz**

- **Header.Payload.Signature**

    - The header typically includes the token type (JWT) and the signing algorithm (e.g., HMAC SHA256 or RSA). For example: `{ "alg": "HS256", "typ": "JWT" }`—this JSON is Base64Url encoded to form the first part of the JWT.

