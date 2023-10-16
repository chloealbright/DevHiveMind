Define user stories 

Ask questions to clarify 

Ask about the scope and define the scope 

Come up with an entity relationship diagram 

talk about stateless architecture means stateless application service with microservices, servers, cache servers 

client side > server/services(Architecture) > DB 

Talk about database like the data being organized so you might need a SQL database  

or  

talk about the data being unstructured so you'll need a NoSQL  

The main difference between unstructured data and structured data is that structured data is typically used for general stuff and it's very organized like user accounts and the information associated with that as for unstructured is typically did I like media audio, geo-location, and weather 

Besides that, you want the other servers for database application you would want a master that handles the crud(Create Read Update Delete) processes and the copies would handle the reading operation you'll probably have more slaves databases and proportion to master the reason we want this because it allows queries to be processed in parallel Which is good for performance 

We also want a load balancer to handle traffic from the DNS server 

Besides that, you might want to have a local cache to improve response time and also a CDN Network 

Cache is used for reading data frequently that isn't modified you would also want several of them because you want to limit your point of failure and stay away from having one single point of failure 

To scale up you want to keep your web tier stateless build redundancies on each tier cache data as much as you can support multiple data centers host CDN networks scale your data to your by sharding to individual services and monitor your system and use automation tools 

Summary 

hund(3) > thous(6)>mill(9)>bill(12)>trill(15) 

86,400 seconds in a day  

read traffic = daily active user * avg read a day/GET(come up with a num)  

write traffic = daily active user * avg writes per/POST user a day(come up with a num)  

memory = read req per  day * AVG Req Size * .2(20%) 

bandwith =  req per  day *  req size 

storage = writes per day * size of write * time to store data 

10 million active users * 20 GET(read) is 200 mill req      

10 million daily active users * 1 POST(write) is 10 mill req 

200 mil(read=GET) / 86,400 seconds in a day is 2,300 request a second 

10 million daily active users divided by 86,4 00 seconds in a day is 115 writes a second 

1kb > 1024byt>1024kb > 1mb > 1024mb > 1gb >1024gb > 1tb > 1024tb > 1peta 

200 million requests times 500 bytes equals 100gb * 2 or 20% is 20 GB of cache * 3 it's about 60 GB when replicating the data 

200 million * 1.5 MB is about 400,000 GB/ 86,400 seconds in a day is about 5gb per second