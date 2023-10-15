Decorators/Wrapper use closure & composition


In its simplest form, a decorator is simply a way of wrapping one piece of code with another — literally “decorating” it. This is a concept you might well have heard of previously as functional composition, or higher-order functions. 

In a software context, the term “wrapper” refers to programs or codes that literally wrap around other program components. Several different wrapper functions can be distinguished. They are often used for ensuring compatibility or interoperability between different software structures. 

// Our basic function always use let for Decorators 

let rectangleArea = (length, width) => { 

    return length * width; 

} 

// A decorator that counts the parameters 

const countParams = (fn) => { 

    return (...params) => { 

        console.log('countParams') 

        if (params.length !== fn.length) { 

            throw new Error(`Incorrect number of parameters for ${fn.name}`); 

        } 

        return fn(...params); 

    } 

} 

// A decorator that requires integers 

const requireIntegers = (fn) => { 

    return (...params) => { 

        console.log('requireIntegers') 

        params.forEach(param => { 

            if (!Number.isInteger(param)) { 

                throw new TypeError(`Params must be integers`); 

            } 

        }); 

        return fn(...params); 

    } 

} 

// applied first makes it runs last 

rectangleArea = countParams(rectangleArea); 

// applied last makes it runs first 

rectangleArea = requireIntegers(rectangleArea); 

//console.log(rectangleArea(20, 30, "Dave")) //caught 1st by integers error 

//console.log(rectangleArea(20, 30, 40)); //number of parameters error 

console.log(rectangleArea(20, 30)); //no error