Apache Tomcat server: Apache Tomcat is a web container. It allows the users to run Servlet and JAVA Server Pages that are based on the web-applications. It can be used as the HTTP server. The performance of the Tomcat server is not as good as the designated web server. 

Key difference between Tomcat and the Apache HTTP Server 

the Apache HTTP Server, but the fundamental difference is that Tomcat provides dynamic content by employing Java-based logic, while the Apache web server's primary purpose is to simply serve up static content such as HTML, images, audio and text. 

# Tomcat 9 & 10 are equivalent products 

[Apache Tomcat](https://en.wikipedia.org/wiki/Apache_Tomcat) 9 and 10 are equivalent products. The only difference is support for changes for the package names in the Jakarta Servlet and related technologies from javax.* to jakarta.*. 

This package name change is for legal reasons involved in the transfer of responsibility for [Jakarta EE](https://en.wikipedia.org/wiki/Jakarta_EE) (formerly Java EE) technologies from [Oracle Corp](https://en.wikipedia.org/wiki/Oracle_Corporation) to the [Eclipse Foundation](https://en.wikipedia.org/wiki/Eclipse_Foundation). 

For more info, read [Understanding Jakarta EE 9](https://www.eclipse.org/community/eclipse_newsletter/2020/november/1.php). 

To quote [the documentation](https://tomcat.apache.org/download-10.cgi): 

Users of Tomcat 10 onwards should be aware that, as a result of the move from Java EE to Jakarta EE as part of the transfer of Java EE to the Eclipse Foundation, the primary package for all implemented APIs has changed from javax.* to jakarta.*. This will almost certainly require code changes to enable applications to migrate from Tomcat 9 and earlier to Tomcat 10 and later. A migration tool is under development to aid this process. 

# Move to the latest 9 rather than 10 

Tomcat 9 and 10 track the same development changes. If your goal is simply to gain some security fixes, as far as I know you'll get the same fixes in both 9 and 10. Do not take my word for this, just study the Tomcat Release Notes. 

So for the fastest easiest migration path, just upgrade to the latest 9 instead of 10. The current latest version of 9 is 9.0.44. 

# Stick with Tomcat 10 

Alternatively, if you want to proceed with using Tomcat 10, change the import statements across your code base to use jakarta.* in place of javax.*. 

IDEs such as IntelliJ have added features to assist in this migration chore.