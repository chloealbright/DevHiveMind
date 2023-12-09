![[URL Anatomy.jpeg]]


<mark style="background: #FFF3A3A6;">URL 1 to 7 </mark>A Uniform Resource Locator is a unique identifier used to locate a resource on the Internet. 

<mark style="background: #ABF7F7A6;">URN 3 to 8</mark> A Uniform Resource Name is an Internet resource with a name that, unlike a URL, has persistent significance - that is, the owner of the URN can expect that someone else (or a program) will always be able to find the resource 

<mark style="background: #BBFABBA6;">URI 1 to 8</mark> A Uniform Resource Identifier is a unique sequence of characters that identifies a logical or physical resource used by web technologies. URIs may be used to identify anything, including real-world objects, such as people and places, concepts, or information resources such as web pages and books 

 # 1. Scheme/Protocol common ones are HTTP or[[ HTTPS]].   

 ### 2. Sub-domain common one is `www` or other like `www1`, `blog`, or mail for Gmail not used a lot. 

 ### 3. Domain is a string that acts as a Identifier  

 4. Top Level Domain is the most generic domain in the Internet's hierarchical DNS domain name system `com`, `org`, and many  more

 5. Port numbers are sometimes seen URLs. By default, HTTP uses port 80 and HTTPS uses port 443, but a URL like [http://www.example.com:8080/path/](http://www.example.com:8080/path/) specifies that the web browser connects instead to port 8080 of the HTTP server. Also web browsers tend to hide the port number from users. 
    
<mark style="background: #ADCCFFA6;">6.</mark>  Path or endpoints are defined when making different CRUD request.  
    
<mark style="background: #D2B3FFA6;">7.</mark>  [[Query String]] which takes in parameters
    
<mark style="background: #FFB8EBA6;">8.</mark>  Fragment identifier is a string after URI, after the hashtag, which identifies something specific as a function of the document.  

The URI fragment is the optional part at the end of a URL which starts with a hash ( # ) character. It lets you refer to a specific part of the document you've accessed. For example, if you visit the following link, you'll automatically scroll to the top of the section you're reading right now!


Hostname would be the combination of the  Sub-Domain, Domain, and Top Level Domain so example would be [www.youtube.com](http://www.youtube.com/) or mail.gmail.com



edit

Resources are part of URLs, like /users.  

For each resource, two URLs are generally implemented: one for the collection, like /users, and one for a specific element, like /users/U123. 

Nouns are used instead of verbs for resources. For example, instead of /getUserInfo/U123, use /users/U123. 

two types of APIs: private and public. 

most APIs are private and imperceptible, internal to companies, used by staff and by partners with contractual agreements. This use of APIs is what is really driving the API revolution. Do not limit your thinking about the ways APIs can be used to public examples like the App Store. Partner and internal use of APIs is often more valuable.