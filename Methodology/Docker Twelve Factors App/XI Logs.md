Logs: The app should generate logs as event streams for monitoring and troubleshooting, providing insight into its behavior. The app should only log to STDOUT or STDERR streams so standard container tools can forward them into a centralized logging system, which is required to monitor and troubleshoot your app.

### Relationship between Disposability and Logging:
The relationship between the disposability factor and the logging factor lies in their combined effect on managing and understanding application behavior:

- **Graceful Shutdown and Recovery:** When an application is designed to be disposable (i.e., it can be stopped and started quickly without adverse effects), proper logging becomes crucial. During shutdown and startup processes, detailed logging helps track the state of the application, identify potential issues, and ensure that it recovers properly after restarting.
    
- **Diagnosing Disposability Issues:** In a disposable architecture, the ability to quickly diagnose issues during startup or shutdown is important. Detailed and structured logs provide insights into why a component might be failing to start or shut down gracefully. This can include information about dependencies, resource availability, and configuration issues.
    
- **Monitoring and Scalability:** Both disposability and logging are important for managing scalability. A stateless, disposable architecture is better suited for horizontal scaling, where new instances can be quickly spun up. Proper logging helps monitor the behavior of these instances, enabling operators to assess performance, identify bottlenecks, and make informed decisions about scaling.
    
- **Debugging and Troubleshooting:** In a disposable environment, applications can be brought up, tested, and taken down frequently. This increases the importance of effective logging for debugging and troubleshooting. Detailed logs provide insights into application behavior, allowing developers to understand issues and identify potential improvements.

## Official Description
### Treat logs as event streams

_Logs_ provide visibility into the behavior of a running app. In server-based environments they are commonly written to a file on disk (a “logfile”); but this is only an output format.

Logs are the [stream](https://adam.herokuapp.com/past/2011/4/1/logs_are_streams_not_files/) of aggregated, time-ordered events collected from the output streams of all running processes and backing services. Logs in their raw form are typically a text format with one event per line (though backtraces from exceptions may span multiple lines). Logs have no fixed beginning or end, but flow continuously as long as the app is operating.

**A twelve-factor app never concerns itself with routing or storage of its output stream.** It should not attempt to write to or manage logfiles. Instead, each running process writes its event stream, unbuffered, to `stdout`. During local development, the developer will view this stream in the foreground of their terminal to observe the app’s behavior.

In staging or production deploys, each process’ stream will be captured by the execution environment, collated together with all other streams from the app, and routed to one or more final destinations for viewing and long-term archival. These archival destinations are not visible to or configurable by the app, and instead are completely managed by the execution environment. Open-source log routers (such as [Logplex](https://github.com/heroku/logplex) and [Fluentd](https://github.com/fluent/fluentd)) are available for this purpose.

The event stream for an app can be routed to a file, or watched via realtime tail in a terminal. Most significantly, the stream can be sent to a log indexing and analysis system such as [Splunk](http://www.splunk.com/), or a general-purpose data warehousing system such as [Hadoop/Hive](http://hive.apache.org/). These systems allow for great power and flexibility for introspecting an app’s behavior over time, including:

- Finding specific events in the past.
- Large-scale graphing of trends (such as requests per minute).
- Active alerting according to user-defined heuristics (such as an alert when the quantity of errors per minute exceeds a certain threshold).