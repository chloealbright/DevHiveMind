[[Event Driven Architecture]] 
Event-Driven APIs & WebHooks


With request–response APIs, for services with constantly changing data, the response can quickly become stale. Developers who want to stay up to date with the changes in data often end up polling the API. With polling, developers constantly query API endpoints at a predetermined frequency and look for new data. 

If developers poll at a low frequency, their apps will not have data about all the events (like a resource being created, updated, or deleted) that occurred since the last poll. However, polling at a high frequency would lead to a huge waste of resources, as most API calls will not return any new data. In one case, Zapier did a study and found that only about 1.5% of their polling API calls returned new data. 

To share data about events in real time, there are three common mechanisms: WebHooks, WebSockets, and HTTP Streaming. We dive deeper into each of them in the subsections that follow. 

WebHooks 

A webhook is a lightweight API that powers one-way data sharing triggered by events. Together, they enable applications to share data and functionality, and turn the web into something greater than the sum of its parts. APIs and webhooks both allow different software systems to sync up and share information. 

A WebHook is just a URL that accepts an HTTP POST (or GET, PUT, or DELETE). An API provider implementing WebHooks will simply POST a message to the configured URL when something happens. Unlike with request–response APIs, with WebHooks, you can receive updates in real time. Several API providers, like Slack, Stripe, GitHub, and Zapier, support WebHooks. For instance, if you want to keep track of “channels” in a Slack team with Slack’s Web API, you might need to continuously poll the API for new channels. However, as illustrated in Figure 2-3, by configuring a WebHook, you can simply receive a notification whenever a new channel is created. 

WebHooks are great for easily sharing real-time data from one server to another server. From an app developer’s point of view, it’s typically easy to implement WebHooks because it simply requires creating a new HTTP endpoint to receive events (see Figure 2-4). This means that they can generally reuse existing infrastructure. At the same time, supporting WebHooks adds new complexities, including the following: 

Failures and retries 

To ensure WebHooks are delivered successfully, it’s important to build a system that will retry WebHook delivery on errors. Slack built a system that retries failed deliveries up to three times: once immediately, and then one minute later, and finally five minutes later. Further, if the endpoint continues to return errors for 95% of requests, Slack stops sending events to that WebHook endpoint and notifies the developer. 

Security 

Although there are standard ways of making REST API calls secure, security for WebHooks is still evolving. With WebHooks, the onus is on app developers to ensure that they’ve received a legitimate WebHook. That often leads to developers using unverified WebHooks. There are some common patterns that most API providers follow to secure WebHooks, which we discuss in Chapter 3. 

Firewalls 

Applications running behind firewalls can access APIs over HTTP, but they are unable to receive inbound traffic. For such applications, utilizing WebHooks is difficult and often not possible. 

Noise 

Typically, each WebHook call represents one single event. When there are thousands of events happening in a short time that need to be sent via a single WebHook, it can be noisy.