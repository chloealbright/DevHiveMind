
Only return if of declared return type 

function createGreeting(name?: string): string { 

  if (name) { 

    return `Hello, ${name}!`; 

  } 

  return undefined; 

  //Typescript Error: Type 'undefined' is not assignable to type 'string'. 

}; 

We can also explicitly state return types for arrow functions (which were defined in the ES6/ES2015 version of JavaScript). We’ll see the same kinds of error messages for both function types. 

const createArrowGreeting = (name?: string): string => { 

    if (name) { 

        return `Hello, ${name}!`; 

    } 

    return undefined; 

    // Typescript Error: Type 'undefined' is not assignable to type 'string'. 

}; 

import {getUserChoice,f1,f2,f3,f4,f5,f6,f7,f8,f9,f10,f11,f12} from './resources' 

function returnFruit():string{ 

  let num = getUserChoice(); 

  switch(num){ 

case 1 : return f1(); 

case 2 : return f2(); 

case 3 : return f3(); 

case 4 : return f4(); 

case 5 : return f5(); 

case 6 : return f6(); 

case 7 : return f7(); 

case 8 : return f8(); 

case 9 : return f9(); 

case 10 : return f10(); 

case 11 : return f11(); 

case 12 : return f12(); 

  } 

  return 'durian.jpg' 

} 

console.log(returnFruit()) 

//The problematic function is f9()





## Void Return Type 

By now, we’ve made a pretty convincing case that type annotations are very useful and should always be used unless there’s a very good reason not to. They make everything neat and aid in understanding our code. 

For these reasons, it is often preferred to use type annotations for functions, even when those functions don’t return anything. Example: 

function logGreeting(name: string){ 

  console.log(`Hello, ${name}!`) 

} 

The function logGreeting() simply logs a greeting to the console. There is no returned value, so we must treat the return type as void. A proper type annotation for this function would look like this: 

function logGreeting(name:string): void{ 

  console.log(`Hello, ${name}!`) 

} 

function makeFruitSalad(fruit1:string, fruit2:string):void{ 

  let salad=fruit1+fruit2+fruit2+fruit1+fruit2+fruit1+fruit1; 

  console.log(salad); 

} 

makeFruitSalad('banana','pineapple'); 

The void operator evaluates the given expression and then returns undefined. 

This operator allows evaluating expressions that produce a value into places where an expression that evaluates to undefined is desired. 

The void operator is often used merely to obtain the undefined primitive value, usually using "void(0)" (which is equivalent to "void 0"). In these cases, the global variable undefined can be used. 

It should be noted that the precedence of the void operator should be taken into account and that parentheses can help clarify the resolution of the expression following the void operator: 

void 2 == '2';   // (void 2) == '2', returns false 

void (2 == '2'); // void (2 == '2'), returns undefined 

Copy to Clipboard 

Examples 

Immediately Invoked Function Expressions 

When using an immediately-invoked function expression, void can be used to force the function keyword to be treated as an expression instead of a declaration. 

void function iife() { 

  console.log("Executed!"); 

}(); 

// Output: "Executed!" 

Copy to Clipboard 

Executing the above function without the void keyword will result in an Uncaught SyntaxError. 

JavaScript URIs 

When a browser follows a javascript: URI, it evaluates the code in the URI and then replaces the contents of the page with the returned value, unless the returned value is undefined. The void operator can be used to return undefined. For example: 

<a href="javascript:void(0);"> 

  Click here to do nothing 

</a> 

<a href="javascript:void(document.body.style.backgroundColor='green');"> 

  Click here for green background 

</a> 

Non-leaking Arrow Functions 

Arrow functions introduce a short-hand braceless syntax that returns an expression. This can cause unintended side effects by returning the result of a function call that previously returned nothing. To be safe, when the return value of a function is not intended to be used, it can be passed to the void operator to ensure that (for example) changing APIs do not cause arrow functions' behaviors to change. 

button.onclick = () => void doSomething(); 

Copy to Clipboard 

This ensures the return value of doSomething changing from undefined to true will not change the behavior of this code.