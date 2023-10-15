HTTP Headers 

Various forms of metadata may be conveyed through the entity headers contained within HTTP’s request and response messages. HTTP defines a set of standard headers, some of which provide information about a requested resource. Other headers indicate something about the representation carried by the message. Finally, a few headers serve as directives to control intermediary caches. 

Rule: Content-Type must be used 

Rule: Content-Length should be used 

The Content-Length header gives the size of the entity-body in bytes. In responses, this header is important for two reasons. First, a client can know whether it has read the correct number of bytes from the connection. Second, a client can make a HEAD request to find out how large the entity-body is, without downloading it. 

Rule: Last-Modified should be used in responses 

The Last-Modified header applies to response messages only. The value of this response header is a timestamp that indicates the last time that something happened to alter the representational state of the resource. Clients and cache intermediaries may rely on this header to determine the freshness of their local copies of a resource’s state representation. This header should always be supplied in response to GET requests. 

Rule: ETag should be used in responses 

The value of ETag is an opaque string that identifies a specific “version” of the representational state contained in the response’s entity. The entity is the HTTP message’s payload, which is composed of a message’s headers and body. The entity tag may be any string value, so long as it changes along with the resource’s representation. This header should always be sent in response to GET requests. 

Clients may choose to save an ETag header’s value for use in future GET requests, as the value of the conditional If-None-Match request header. If the REST API concludes that the entity tag hasn’t changed, then it can save time and bandwidth by not sending the representation again. 

Rule: Stores must support conditional PUT requests 

A store resource uses the PUT method for both insert and update, which means it is difficult for a REST API to know the true intent of a client’s PUT request. Through headers, HTTP provides the necessary support to help an API resolve any potential ambiguity. A REST API must rely on the client to include the If-Unmodified-Since and/or If-Match request headers to express their intent. The If-Unmodified-Since request header asks the API to proceed with the operation if, and only if, the resource’s state representation hasn’t changed since the time indicated by the header’s supplied timestamp value. The If-Match header’s value is an entity tag, which the client remembers from an earlier response’s ETag header value. The If-Match header makes the request conditional, based upon an exact match of the header’s supplied entity tag value and the representational state’s current entity tag value, as stored or computed by the REST API. 

Rule: Location must be used to specify the URI of a newly created resource 

Rule: Cache-Control, Expires, and Date response headers should be used to encourage caching 

Rule: Cache-Control, Expires, and Pragma response headers may be used to discourage caching 

Rule: Caching should be encouraged 

Rule: Expiration caching headers should be used with 200 (“OK”) responses 

Rule: Expiration caching headers may optionally be used with 3xx and 4xx responses 

Rule: Custom HTTP headers must not be used to change the behavior of HTTP methods 

You can optionally use custom headers for informational purposes only. Implement clients and servers such that they do not fail when they do not find expected custom headers. 

If the information you are conveying through a custom HTTP header is important for the correct interpretation of the request or response, include that information in the body of the request or response or the URI used for the request. Avoid custom headers for such usages.