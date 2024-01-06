---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---






talk about stateless architecture means stateless application service with microservices, servers, cache servers  
  
client side > server/services(Architecture) > DB  
  
Talk about database like the data being organized so you might need a SQL database  
  
or  
  
talk about the data being unstructured so you'll need a NoSQL


We also want a load balancer to handle traffic from the DNS server  
  
Besides that, you might want to have a local cache to improve response time and also a CDN Network  
  
Cache is used for reading data frequently that isn't modified you would also want several of them because you want to limit your point of failure and stay away from having one single point of failure  
  
To scale up you want to keep your web tier stateless build redundancies on each tier cache data as much as you can support multiple data centers host CDN networks scale your data to your by sharding to individual services and monitor your system and use automation tools




we need multiple load balancer(without his you,ll go outside the dns) for all the HTTP request traffic for the post/ likes/ comments/ and feeds 

load balancer acts as one ip for alot of servers which helps keep you in the domain 

app server needs to stateless meaning it doesn't store data 

access other services that use aoi to return info based on your input like a user id 

You can say you don't know about this but my idea is ..... 

-> this will distribute to different servers pools  

-> we also need a cache probably for Likes  

-> we also a couple of master DB and slaveDB  



TIME 

60 sec * 60 min = 3600 sec per hour 

3600 * 24 hours = 86,400 sec per day 

86,400 

86,400 * 30 days 2,500,000 sec per month 




1 kilobyte (KB) 1,024 bytes 

1024 kilobytes = 1 megabyte (MB) 1,048,576 bytes 

1024 megabytes = 1 gigabyte (GB) 1,073,741,824 bytes 

1024 gigabytes = 1 terabyte (TB) 1,099,511,627,776 bytes 

1024 terabytes = 1 petabyte (PB) 1,125,899,906,842,624 byte 



traffic estimate 

many request and writes per second 

10 mill daily active users * 30 post viewed = 300 mill request  

10 mill daily active users * 1 post uploaded = 10 mill writes  

300mill(active uswe) / 86,400 sec = 3,000 req a sec 

10mill / 86,400 sec = 115 write a sec 



this goes into memory  

cache popular people use for instagram highlights 

300 mill req * 500 bytes= 150 gb 

150gb * .2(20%) = 30gb for cache 

30gb * 3(replication) 



bandwith 

300 mill * 1.5mb = 450,000gb 

450,000gb / 86,400 sec = 5.2gb per sec 



storage 

10mill writes * 1.5mb = 15tb per day 

15tb * 365 days * 10 years = 55ptb 



Summary 

traffic = daily active user * avg read and writes per user 

memory = read req per  day * AVG Req Size * 20% 

bandwith =  req per  day *  req size 

storage = writes per day * size of write * time to store data



# Alt way of writing edit merge


  
memory = read req per day * AVG Req Size * .2(20%)  
  
bandwith = req per day * req size  
  
storage = writes per day * size of write * time to store data  
  
10 million active users * 20 GET(read) is 200 mill req  
10 million daily active users * 1 POST(write) is 10 mill req  
  
200 mil(read=GET) / 86,400 seconds in a day is 2,300 request a second  
  
10 million daily active users divided by 86,4 00 seconds in a day is 115 writes a second  
  
1kb > 1024byt>1024kb > 1mb > 1024mb > 1gb >1024gb > 1tb > 1024tb > 1peta  
  
200 million requests times 500 bytes equals 100gb * 2 or 20% is 20 GB of cache * 3 it's about 60 GB when replicating the data  
  
  
200 million * 1.5 MB is about 400,000 GB/ 86,400 seconds in a day is about 5gb per second