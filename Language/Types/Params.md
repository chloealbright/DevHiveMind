---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
## Optional Parameters

When the code snippet above is compiled to JavaScript, the greet() function will correctly print 'Hello, Anonymous!'. That’s because when no arguments are passed in, name has the falsy value undefined, which means that name || 'Anonymous' evaluates to 'Anonymous'. Since the final code works as intended, we want to prevent TypeScript from throwing errors:

To indicate that a parameter is intentionally optional, we add a ? after its name. This tells TypeScript that the parameter is allowed to be undefined and doesn’t always have to be provided.

function greet(name?: string) {

  console.log(`Hello, ${name|| 'Anonymous'}!`);

}

greet(); // 

## Default Parameters

If a parameter is assigned a default value, TypeScript will infer the variable type to be the same as the default value’s type. (This is similar to how TypeScript infers the type of an initialized variable to be the same as the type of its initial value.)

The following code snippet logs a string to greet a user’s name, and defaults to the name 'Anonymous' if no name is provided.

function greet(name = 'Anonymous') {

  console.log(`Hello, ${name}!`);

}

The function greet() can receive a string or undefined as its name parameter—if any other type is provided as an argument, TypeScript will consider that a type error.

This is a cleaner way of getting the same functionality we had in the previous exercise. There, we used ? to mark the name parameter as optional. But parameters with default values don’t need a ? after their name, since assigning a default value already implies that they’re optional parameters.

function proclaim(status = 'not ready...', repeat = 1) {

  for (let i = 0; i < repeat; i += 1) {

    console.log(`I'm ${status}`);

  }

}

proclaim();

proclaim('ready?');

proclaim('ready!', 3);



JavaScript Optional Arguments also known as Default parameters  

The following code is allowed and executes without any problem: 

function square(x) { return x * x; } 

console.log(square(4, true, "hedgehog")); 

// → 16 

We defined squares with only one parameter. Yet when we call it with three, the language doesn’t complain. It ignores the extra arguments and computes the square of the first one. 

JavaScript is extremely broad-minded about the number of arguments you pass to a function. If you pass too many, the extra ones are ignored. If you pass too few, the missing parameters get assigned the value undefined. 

The downside of this is that it is possible—likely, even—that you’ll accidentally pass the wrong number of arguments to functions. And no one will tell you about it. 

The upside is that this behavior can be used to allow a function to be called with different numbers of arguments. For example, this minus function tries to imitate the - operator by acting on either one or two arguments: 

function minus(a, b) { 

  if (b === undefined) return -a; 

  else return a - b; 

} 

console.log(minus(10)); 

// → -10 

console.log(minus(10, 5)); 

// → 5 

If you write an = operator after a parameter, followed by an expression, the value of that expression will replace the argument when it is not given. 

For example, this version of power makes its second argument optional. If you don’t provide it or pass the value undefined, it will default to two, and the function will behave like a square. 

function power(base, exponent = 2) { 

  let result = 1; 

  for (let count = 0; count < exponent; count++) { 

    result *= base; 

  } 

  return result; 

} 

console.log(power(4)); 

// → 16 

console.log(power(2, 6)); 

// → 64