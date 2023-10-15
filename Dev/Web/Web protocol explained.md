![[_Files/Web/unnamed (10).gif]]

Websites are stored and hosted on servers that clients like are personal computers connect to through ISP when sending and receiving data it is broken down into packets with headers which are guided by routers to avoid confusion also known as [[TCIP]](Transmission Control Protocol) which consist of layers like application which tend to consist of HTTP, [[HTTPS]], [[SMTP]], [[FTP]] and other things from internet browsers then next layer is transport which has TCP and UDP and things are transferred between ports between these two layers then TCP breaks things down into packets with headers then the packets are pushed to internet layer which attaches origin and destination IP address which would eventually reach a DNS server that checks the address and match it to a URL and domain name like ".com" then it is sent to the network layer that handles mac addressing.  
  
when it comes to IP address the DNS checks IP address with URL name and domains like .com  
  
your computer caches DNS storing website info on your machine if you visit a site that changed IP address you can get a 404 error


![[1696261520481.gif]]


Edit
link to https req and res

Req & Res

The headers and body are completely different 

You can create a request and response directly using the Request() and Response() constructors, but it's uncommon to do this directly. Instead, these are more likely to be created as results of other API actions using the Fetch Interfaces like fetch() 

Within CRUD  

we typically POST request on the front-end > and Get request on the back-end 

if data is already created you do a GET on front-end at the endpoint and on the back-end the query action is down at whatever endpoint you defined