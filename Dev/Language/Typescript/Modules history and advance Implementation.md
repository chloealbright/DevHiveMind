![[unnamed (9) 1.gif]]
In HTML when you create a script tag to import your JavaScript file you don't want to do that a lot because it makes it that the JavaScript is available to the window object in the browser which is bad for security probably because you have it on the global namespace  
  
So you put your JavaScript code into a function, Name the function or create an anonymous function which is basically a nameless function then call it or just parentheses like you would have method there would be no name though so it should be parentheses by themselves as the call  
  
This is called an IIFE module pattern the benefit of this is you don't have methods names in the global scope of the HTML page  
  
  
  
  
But there is still a better way which is module export & import  
  
which solves these issues  
  
Issues  
-----------  
Don't have to wrap our functions in IIFE's.  
Don't have to worry about keeping scripts in order.  
Nothing is bind to global name-space even APP.  
  
  
revisit for Module bundlers  
[https://www.youtube.com/watch?v=qJWALEoGge4](https://www.youtube.com/watch?v=qJWALEoGge4)