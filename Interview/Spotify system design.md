![[_Files/Interview/unnamed (7).gif]]

Don't make assumptions when you have one tell the interviewer can I assume this.. to convey an assumption and get an idea of things 

Don't focus on other Scopes outside of your scope 

Before asking about stuff like databases clear out these questions first. 

Ask about different use cases which will let you derive The entity-relationship diagram for type of data that you would need 

When you ask about use cases first focus on the action like pressing the button ask what it does and expand on that in terms of what you think should happen like collecting certain data and where would that go or be connected to and the different processes that need to happen 

Then you ask about things like user base and the size of it estimation of it and determine things like constraints and bottlenecks which will then lead to database questions which may require specialized databases that are NoSQL or SQL base 

Estimation just come up with a little math problem like there are about this amount of playing music in a day and there are listening to about this amount of songs since listening to this amount of songs just multiply this amount of songs by the amounts of music being played to get a daily usage in total which is estimation then multiply that by the number of days in a month to get that usage for a month and convert that monthly usage to seconds to determine an estimation of what will be used to process all that information which is a lot and go from there 

We care about all this information because we want to know about the throughput to property design and infrastructure to handle it  

Now when it comes to processing this data would have a api request send a post request that sends the data to an endpoint with information like user ID and all the information associated with that 

ask about data cap size for components user range like a particular state, country or continent ask about certain things that we would need along a data table which would help draw out a lot of info 

define certain things like what it means to be a user and the different user type  

After that, we're going to scaling 

talk endpoints for api calls 

like GET /profile Query statement for SQL and so on 

think about computation as you scale up and optimizations 

think about traffic type 

you can have servers for specific things like reading or writing post GET/POST 

servers can cache locally 

a cache hit is local and cache miss isn't local 

a load balancer is basically another server at a high level 



### TIME 

60 sec * 60 min = 3600 sec per hour 

3600 * 24 hours = 86,400 sec per day 

86,400 * 30 days 2,500,000 sec per month 



### num place 

300 hundred 

600,000 thousand 

900,000,000 million 

120,000,000,000 billion 

150,000,000,000,000 trillion 





1 kilobyte (KB) 1,024 bytes 

1024 kilobytes = 1 megabyte (MB) 1,048,576 bytes 

1024 megabytes = 1 gigabyte (GB) 1,073,741,824 bytes 

1024 gigabytes = 1 terabyte (TB) 1,099,511,627,776 bytes 

1024 terabytes = 1 petabyte (PB) 1,125,899,906,842,624 byte 



### traffic estimate 

many requests and writes per second 

10 mill daily active users * 30 GET(read) is = 300 mill req 

10 mill daily active users * 1 POST(write)  = 10 mill req  

300mill / 86,400 sec = 3,000 req a sec 

10mill / 86,400 sec = 115 write a sec 



### this goes into memory  

cache popular people use for highlights 

300 mill req * 500 bytes= 150 gb 

150gb * .2(20%) = 30gb for cache 

30gb * 3(replication) 



### bandwith 

300 mill * 1.5mb = 450,000gb 

 450,000gb / 86,400 sec = 5.2gb per sec 

storage 

10mill writes * 1.5mb = 15tb per day 

15tb * 365 days * 10 years = 55ptb 



### Summary 

traffic = daily active user * avg read and writes per user 

memory = read req per  day * AVG Req Size * 20% 

bandwith =  req per  day *  req size 

storage = writes per day * size of write * time to store data