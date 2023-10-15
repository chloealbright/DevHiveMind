TypeScript is a superset of JavaScript that adds types.  


TypeScript is a transpiler or code that translates one language to the other   

Like TypeScript renders down to JavaScript and JavaScript renders down to the browser to be executed  

Can also be referred to as preprocessing   

ecmascript





The type system refers to TypeScript’s understanding of how your code is meant to function: mainly what data types should be stored under your variables.  

TypeScript expects the data type of the variable to match the type of the value initially assigned to it at its declaration—this is known as type inference.  

An object’s shape describes, among other things, what properties and methods it does or doesn’t contain. TypeScript knows not only what type something is but also what shape that type has.  

When it isn’t able to infer a type, TypeScript will consider a variable to be of type any.  

Type annotations are little pieces of code that indicate what type a variable is meant to be.  

The tsconfig.json file is always placed in the root of your project and you can customize what rules you want the TypeScript compiler to enforce. Here’s the tsconfig.json file we provide in every single exercise and project in our Learn TypeScript course:  

{   

  "compilerOptions": {   

    "target": "es2017",   

    "module": "commonjs",     

    "strictNullChecks": true   

  },   

  "include": ["**/*.ts"]   

}   

In the JSON, there are several properties:  

"compilerOptions", which is a nested object that contains the rules for the TypeScript compiler to enforce.   

"target", the value "es2017" means the project will be using the 2017 version of EcmaScript standards for JavaScript.   

"module", this project will be using "commonjs" syntax to import and export modules.   

"strictNullChecks", variables can only have null or undefined values if they are explicitly assigned those values.   

"include" that determines what files the compiler applies the rules to. 

	In this case ["**/*.ts"] means the compiler should check every single file that has a .ts extension.   

We chose these rules because we wanted to give you an idea of what rules to enforce and still allow your creativity to shine. For your own projects, you can set these rules to your own preferences! The tsconfig.json file is great for both individual work and team projects because it allows everyone to be on the same page about how to write their code.   

 Another neat addition is that by including a tsconfig.json file, you can now use the command tsc without any arguments in your terminal! The compiler will automatically recognize from your tsconfig.json file, what specific files to run on. You can still provide specific files like tsc fileName.ts if that’s the only file you want the compiler to check. 

@ basically adds types to lib 

After adding all required packages, now we can initialize our TypeScript configuration file 

yarn tsc --init 

Typescript setup - add tsconfig.json file  

install in project folder 

    npm install  ts-node typescript @types/express 

Run the below commands and install the required packages globally: 

         npm install -g ts-node typescript '@types/node' 

Now run the following command to execute a typescript file: 

          ts-node typescript-file.ts



## Functions in typescript


```typescript
// Documenting  

/** 

* @param fruit1- The first input number 

  * @param fruit2 - The second input number 

  @returns void 

*/ 

function makeFruitSalad(fruit1: string, fruit2: string): void { 

  let salad = fruit1 + fruit2 + fruit2 + fruit1 + fruit2+ fruit1 + fruit1; 

  console.log(salad); 

}


NormaljsObj :  { [key: string]: UnvalidatedField } ={ 

"a": 1 

"b": true 

}


const NormaljsObj : { [key: string]: UnvalidatedField } = { 

"a": 1,  

"b": true  

}




```


Function Types 

One of the neat things about JavaScript is that functions can be assigned to variables. 

let myFavoriteFunction = console.log; // Note the lack of parentheses. 

myFavoriteFunction('Hello World'); // Prints: Hello World 

One of the neat things about TypeScript is that we can precisely control the kinds of functions assignable to a variable. We do this using function types, which specify the argument types and return type of a function. Here’s an example of a function type that is only compatible with functions that take in two string arguments and return a number. 

type StringsToNumberFunction = (arg0: string, arg1: string) => number; 

This syntax is just like arrow notation for functions, except instead of the return value we put the return type. In this case, the return type is number. Because this is just a type, we did not write the function body at all. A variable of type StringsToNumberFunction can be assigned any compatible function: 

let myFunc: StringsToNumberFunction; 

myFunc = function(firstName: string, lastName: string) { 

  return firstName.length + lastName.length; 

}; 

myFunc = function(whatever: string, blah: string) { 

  return whatever.length - blah.length; 

}; 

// Neither of these assignments results in a type error. 

As we can see above, it doesn’t matter what we name the function parameters, so long as they have the correct types (string and string). Therefore, it doesn’t matter what we name the parameters in the type annotation (above, we chose arg0 and arg1). 

There’s something important to remember here. We must never be tempted to omit the parameter names or the parentheses around the parameters in a function type annotation, even if there is only one parameter. This code will not run! 

type StringToNumberFunction = (string)=>number; // NO 

type StringToNumberFunction = arg: string=>number; // NO NO NO NO 

Function types are most useful when applied to callback functions. With how common callback functions are, it’s useful to know how to type them appropriately. 

// Math Operations 

function add(a, b){ return a+b } 

function subtract(a, b){ return a-b } 

function multiply(a, b){ return a*b} 

function divide(a, b){ return a/b} 

function wrongAdd(a, b){return (a+b)+''} 

// Add your function type below: 

type OperatorFunction = (a: number, b: number)=>number; 

// Math Tutor Function That Accepts a Callback 

function mathTutor(operationCallback: OperatorFunction) { 

  console.log("Let's learn how to", operationCallback.name,'!'); 

  let value25 = operationCallback(2,5); 

  console.log('When we', operationCallback.name, '2 and 5, we get', value25, '.'); 

  console.log('When we', operationCallback.name, value25, 'and 7, we get', operationCallback(value25, 7), '.'); 

  console.log('Now fill out this worksheet.') 

} 

// Call your functions below: 

mathTutor(multiply); 

mathTutor(wrongAdd);