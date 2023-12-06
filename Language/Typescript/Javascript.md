![[java-script Inner Working.gif]]

Javascript is a programming language that was used to make websites more interactive but now is used for more things ever since the v8 engine from google chrome was created which allowed people to use javascript for mobile, desktop, and server development.

JavaScript is considered a weak type in language while Java is strong like when you're declaring something like a character you get to make it a character variable while in Java you can just make it let variable then you have to declare the function data type and whether it's private or public and so on for Java as for JavaScript you don't have to do that but if you're using typescript you can do strong typing in your code  

JavaScript files can referred as modules



It allocates memory 

Parses and executes 

Allocating memory is basically something as simple as declaring a variable and assigning a value 

When declaring these variables if you don't use them they take up memory and can lead to memory leak especially with global variables 

So because JavaScript is garbage collected that is memory is managed automatically.


# Execution Context

![[Global Exe Context.png]]![[Pasted image 20230418075540.png]]

The Execution Context contains 

Lexical environment {scope} general scope block, Global & function scope 

Variable Environment evaluates the values of created variables and separate from binding 

"this" Binding this refers to window and prototype 

Window have multiple ------------> this which refer to prototype 

                                           |_____this 

The Global Execution Context 

• Create a Memory Heap to keep all variables and functions at a global level 

• Create a Global Object and “this” keyword 

The location of “this” depends on where your code is running. In the browser, for example, it points to windows objects. Nodejs, for example, will point to a different global object.


![[GetImage (20).png]]

call(), apply() and bind() 

Up until now we have treated functions as objects that are composed of a name (optional, can also be an anonymous function) and the code it executes when it is invoked. But that isn’t the entire truth. As a truth loving person, I must let you know that a function actually looks closer to the following image: 

bind() 

The official docs say: The bind() method creates a new function that, when called, has its this keyword set to the provided value. (It actually talks about even more stuff, but we’ll leave that for another time :) ) 

This is extremely powerful. It let’s us explicitly define the value of this when calling a function. 

When we use the bind() method: 

the JS engine is creating a new pokemonName instance and binding pokemon as its this variable. It is important to understand that it copies the pokemonName function. 

After creating a copy of the pokemonName function it is able to call logPokemon(), although it wasn’t on the pokemon object initially. It will now recognizes its properties (Pika and Chu) and its methods. 

And the cool thing is, after we bind() a value we can use the function just like it was any other normal function.  

call(), apply() 

The official docs for call() say: The call() method calls a function with a given this value and arguments provided individually. 

What that means, is that we can call any function, and explicitly specify what this should reference within the calling function. Really similar to the bind() method! This can definitely save us from writing hacky code (even though we are all still hackerzzz). 

The main differences between bind() and call() is that the call() method: 

Accepts additional parameters as well 

Executes the function it was called upon right away. 

The call() method does not make a copy of the function it is being called on. 

call() and apply() serve the exact same purpose. The only difference between how they work is that call() expects all parameters to be passed in individually, whereas apply() expects an array of all of our parameters.  

var pokemon = { 

    firstname: 'Pika', 

    lastname: 'Chu ', 

    getPokeName: function() { 

        var fullname = this.firstname + ' ' + this.lastname; 

        return fullname; 

    } 

}; 

var pokemonName = function(snack, hobby) { 

    console.log(this.getPokeName() + ' loves ' + snack + ' and ' + hobby); 

}; 

pokemonName.call(pokemon,'sushi', 'algorithms'); // Pika Chu  loves sushi and algorithms 

pokemonName.apply(pokemon,['sushi', 'algorithms']); // Pika Chu  loves sushi and algorithms




Debugging Memory Leaks 

In JavaScript, memory leaks commonly occur within heap allocated memory, where short lived objects are attached to long lived ones and the Garbage Collector cannot safely de-allocate that memory as it is still referenced from the root set (the global object).




Strict Mode 

JavaScript's strict mode is a way to opt-in to a restricted variant of JavaScript, thereby implicitly opting out of "sloppy mode". Strict mode isn't just a subset: it intentionally has different semantics from regular code. Browsers not supporting strict mode will run strict mode code with different behavior from browsers that do, so don't rely on strict mode without feature-testing for support for the relevant aspects of strict mode. Strict mode code and non-strict mode code can coexist so that scripts can opt into strict mode incrementally. 

Strict mode makes several changes to normal JavaScript semantics: 

-   Eliminates some JavaScript silent errors by changing them to throw errors. 
    
-   Fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes run faster than identical code that's not strict mode. 
    
-   Prohibits some syntax likely to be defined in future versions of ECMAScript.





Production Build & Compiling 

There are some other useful topics as compiling and creating production build. After you successfully build your application it would be ready to use in production! Compiling your typescript code will convert it to regular vanilla JavaScript code. 

To be able to compile your code to JavaScript you can use the script below 

"build": "tsc --project ." 

That will build your code into the dist folder as we specified in the tsconfig.json file. You can check out that file and it will be similar to this app.js file. 

import express from 'express'; 

const app = express(); 

const port = 8000; 

app.get('/', (req, res) => { 

res.send('Hello world!'); 

}); 

app.listen(port, function () { 

console.log(`App is listening on port ${port} !`); 

}); 

You can start using this code in production now! 

To be able to make always clean build you can use the command below 

"build": "rm -rf ./dist && tsc --project ." 

That will remove the dist folder already created in another build and create a new build. 

Running the production build code on your localhost is very easy after these steps are completed. 

There is another script we should add to package.json file to be able to run the production build in localhost. 

"start:prod": "yarn build && node ./dist/app.js" 

That command will create a new production build and start running it from the dist folder. 

That is all that is required to set up Express application with TypeScript and using ES modules in the Node application!