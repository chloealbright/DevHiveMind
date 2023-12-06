## Background

Have you ever accessed one of your applications and seen weird errors like IOException or IllegalNullPointer?  In Java, an [Exception](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Exception.html) aka “exceptional event” is an event that occurs during the execution of a program and can disrupt its normal flow. Don’t confuse errors with exceptions.  Exceptions are events from which we can recover, errors are serious problems that cannot be recovered from but require code changes. The JDK covers most general cases, but Java does allow developers to create their exceptions. This is frowned upon but sometimes necessary, depending on the scenario.

## The Call Stack

Let’s understand how this works.  When an error occurs within a method, the method creates an exception object and hands it off to the runtime system. The exception object contains information about the error, such as its type and the program's state when the error occurred.  Next, the runtime system searches the call stack for an exception handler which is a method that contains a block of code that can handle the exception. Once an exception handler is found that meets the criteria of the error, the runtime system passes the exception object to the handler.  This is known as catching the exception.  If the runtime system cannot find an appropriate exception handler, then the runtime system terminates, which also terminates your application.

## Benefits of Exception handling

-   Separation from regular code. This keeps the main logic of the program separate from the code that handles exceptional events.
-   Propagating the error to the appropriate method.
-   Grouping and differentiating error types. The developer has the choice to handle specific exceptions (FileNotFoundException), combine exceptions (IOException), or a catch-all by catching the Exception class.

## Type of Exceptions

There are two types of exceptions:  Checked and Unchecked.

-   Checked exceptions that can be handled at compile time. The catch or specify requirement applies. This means the exception can be handled or propagated up the class stack. To be propagated, the keyword throw is used. All exceptions are checked exceptions except subclasses of Runtime Exception or Error. FileNotFoundException is an example of a checked exception.  
    For example:

![[Exception.png]]

-   Results in
![[Exception Result.png]]

-   Unchecked exceptions are not anticipated. They do not follow the catch or specify requirements. They have automatically propagated up the call stack until an appropriate exception handler is found; otherwise, the runtime terminates. RuntimeException or Error are unchecked exceptions. NullPointerException is an example of an unchecked exception.

## Catching and Handling Exceptions

Catching and handling exceptions consist of three blocks: [try](https://docs.oracle.com/javase/tutorial/essential/exceptions/try.html), [catch](https://docs.oracle.com/javase/tutorial/essential/exceptions/catch.html), and [finally](https://docs.oracle.com/javase/tutorial/essential/exceptions/finally.html) blocks.  Try and catch are paired together, and finally.

-   try contains statements where errors occurred. It is ALWAYS followed by a catch block, a finally block, or both.
-   catch contains statements about where to handle the exceptions. A single try block can have multiple catch blocks. If consolidating exceptions into one catch block, be sure to separate exceptions with a pipe (|).
-   finally is optional, and any statements in here are executed after completing the try-catch blocks. It gets called no matter what. It is good to use if you have resources that need to be closed.
-   Instead of using finally(), an option to use [the try-with-resources](https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html) statement can be used. the try-with-resources statement is a try statement that declares one or more resources. the try-with-resources statement will close each declared resource at the end of the statement.

## Throwing Exceptions

The keyword throw is used to propagate an exception to the appropriate handler.  The keyword throws can specifically throw any checked exception in the method signature or user-defined exception.

For example, rather than this method handling any exceptions, it throws the catchall Exception. If the developer wanted to throw specifically FileNotFoundException, it would change Exception to FileNotFoundException.

![[Exceptions throwing.png]]

### Types of Errors:
Besides error constructors, JavaScript also has other core Error constructors.

-   [AggregateError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError)
-   [EvalError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/EvalError)
-   [InternalError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/InternalError)
-   [RangeError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError)
-   [ReferenceError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError)
-   [SyntaxError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError)


### Utilizing error objects
When a runtime error occurs, a new Error object is created and thrown. With this Error object, we can determine the type of the Error and handle it according to its type.


```typescript
class CustomError extends Error {
    constructor(message: string) {
        super(message);
        this.name = "CustomError";
    }
}

function exampleFunction(value: number): string {
    try {
        if (value < 0) {
            throw new CustomError("Value must be non-negative");
        }

        // Your regular logic here

        return "Operation successful";
    } catch (error) {
        if (error instanceof CustomError) {
            console.error(`Custom Error: ${error.message}`);
            // Handle CustomError specifically
        } else if (error instanceof Error) {
            console.error(`Generic Error: ${error.message}`);
            // Handle other types of errors
        } else {
            console.error("Unknown error occurred");
        }

        return "Operation failed";
    }
}

// Example usage:
console.log(exampleFunction(42)); // Operation successful
console.log(exampleFunction(-5)); // Custom Error: Value must be non-negative, Operation failed
```

