![[HTTP Streaming.png]]

With the HTTP request–response APIs, clients send an HTTP request and the server returns an HTTP response of a finite length (Figure 2-6). Now, it’s possible to make the length of this response indefinite. With HTTP Streaming, the server can continue to push new data in a single long-lived connection opened by a client. 

To transmit data over a persistent connection from server to client, there are two options. The first option is for the server to set the Transfer-Encoding header to chunked. This indicates to clients that data will be arriving in chunks of newline-delimited strings. For typical application developers, this is easy to parse. 

Another option is to stream data via server-sent events (SSE). This option is great for clients consuming these events in a browser because they can use the standardized Event Source API. 

Twitter utilizes the HTTP Streaming protocol to deliver data through a single connection opened between an app and Twitter’s streaming API. The big benefit for developers is that they don’t need to poll the Twitter API continuously for new tweets. Twitter’s Streaming API can push new tweets over a single HTTP connection instead of a custom protocol. This saves resources for both Twitter and the developer. 

HTTP Streaming is easy to consume. However, one of the issues with it is related to buffering. Clients and proxies often have buffer limits. They might not start rendering data to the application until a threshold is met. Also, if clients want to frequently change what kind of events they listen to, HTTP Streaming might not be ideal because it requires reconnections.


Data Streaming

Streaming data is data that is generated continuously by thousands of data sources, which typically send in the data records simultaneously, and in small sizes (order of Kilobytes).