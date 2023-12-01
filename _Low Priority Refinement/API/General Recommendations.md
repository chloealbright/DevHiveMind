-   API Data Protection Recommendations 
    
    -   Use SSL when the API includes sensitive data, or if the authentication mechanism does not include an encryption component. HTTP Basic authentication and OAuth with bearer tokens, for instance, allow an eavesdropper to intercept the security credentials unless SSL is used. 
        
    
    -   Always defend against injection attacks, in the backend server, at the edge of the network, or both. 
        
    
    -   If your API accepts incoming parameters via HTTP POST or some other method, you must defend against many types of data attacks. These include large inputs, payloads or attachments, header bombs, replay attacks, message tampering and more. 
        
    
    -   Consider using data masking in a common transformation layer if your backend servers return some data that should not be given out to all users of the API. 
        
    
    -   For writable APIs, don’t simply rely on IP addresses to secure your APIs. IP addresses can be spoofed, are not always unique, and can’t be trusted as a single authentication scheme. A combination of approaches works best. 
        
    

-   API Security Recommendations 
    
    -   Use API keys only for nonsensitive, read-only data. If you have a public API—which exposes data you’d make public on the Internet anyway—consider issuing nonsensitive API keys. These are easy to implement and still give you a way to identify applications and developers. Armed with an API key, you have the option of establishing a quota for your API, or at least monitoring usage by application. Without one, the only way to track usage is through IP addresses, which are not reliable. For example, the Yahoo Maps Geocoding API issues API keys so it can track its users and establish a quota, but the data that it returns is not sensitive, so it’s not critical to keep the key secret. 
        
    
    -   Public APIs should use OAuth 2.0 for APIs that are intended for use by native and mobile apps. The advantage of using an OAuth token rather than a password is also important for mobile apps, to ensure that a user’s password is not propagated to every app and device that they use. Typically, authenticating to OAuth requires that the user enter her password into a web browser screen, rather than the application itself. That means that the application never actually sees the user’s password. This adds a layer of security when an API is used by mobile apps built by untrusted developers for a public API. OAuth also has the ability to allow the API provider to revoke tokens for an individual user, or for an entire application, without requiring the user to change his or her original password. This is critical if a mobile device is compromised or if a rogue application is discovered. 
        
    
    -   Private APIs should consider OAuth 2.0 for native and mobile apps. Private API providers have control over the clients that are built for the API, so it is safer to allow the application to collect the user’s password directly. However, OAuth still makes it possible for the application to acquire a token, store it on the device, and immediately discard the password, which reduces the risk that the password will be compromised. 
        
    
    -   Support other types of authentication for server-to-server APIs. Two-way SSL, SAML, and even usernames combined with long, random passwords are fine security schemes that have the advantage of being well supported by client and server platforms. For an API that is only used by a small number of internal or partner systems, and which is used by servers and not by end users who have passwords, OAuth works but it is overkill. 
        
    
    -   Use SSL for everything sensitive (or maybe even for everything). Unless your API exclusively has open and nonsensitive data, support SSL and consider enforcing it by redirecting any API traffic on the non-SSL port to the SSL port. It makes other authentication schemes more secure, and keeps your user’s private API data from prying eyes—and it’s not all that hard to do. 
        
    
    -   Sanitize incoming and outgoing data. This will prevent malicious code or content from entering your system or being executed by clients that read your data. This practice should be employed for all APIs, but may be especially important for writable ones. For example, for a writable API, you do not want to allow insertion of JavaScript that could be used for cross-site scripting attacks when users visit your website. For example, if a parameter value is known to be numeric, it should be validated as numeric before being passed. Again, this practice should be applied for all APIs, but may be more needed for writable APIs.