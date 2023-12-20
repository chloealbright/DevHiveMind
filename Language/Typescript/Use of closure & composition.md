---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Decorators or wrappers, often implemented using closure and composition, are a mechanism for encapsulating and enhancing functions in a software context. Essentially, decorators "decorate" or wrap one piece of code with another, a concept synonymous with functional composition or higher-order functions.

In software, a "wrapper" refers to programs or code components that enclose or envelop other program elements. Various wrapper functions serve to ensure compatibility or interoperability between different software structures.

Here's an example using a basic function for calculating the area of a rectangle, employing decorators implemented with closures:

```javascript
// Our basic function, always using 'let' for Decorators
let rectangleArea = (length, width) => {
    return length * width;
}

// A decorator that counts the parameters
const countParams = (fn) => {
    return (...params) => {
        console.log('countParams');
        if (params.length !== fn.length) {
            throw new Error(`Incorrect number of parameters for ${fn.name}`);
        }
        return fn(...params);
    }
}

// A decorator that requires integers
const requireIntegers = (fn) => {
    return (...params) => {
        console.log('requireIntegers');
        params.forEach(param => {
            if (!Number.isInteger(param)) {
                throw new TypeError(`Params must be integers`);
            }
        });
        return fn(...params);
    }
}

// Applied first, making it run last
rectangleArea = countParams(rectangleArea);

// Applied last, making it run first
rectangleArea = requireIntegers(rectangleArea);

// Example usages
// console.log(rectangleArea(20, 30, "Dave")) // Caught first by integers error
// console.log(rectangleArea(20, 30, 40)) // Number of parameters error
console.log(rectangleArea(20, 30)); // No error
```

In this example, the decorators enhance the `rectangleArea` function by checking the number and type of parameters, showcasing the power of closure and composition in modifying and extending functionality.