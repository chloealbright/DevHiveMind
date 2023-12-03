---
tags:
  - CodebaseDecision
  - MacroCodebaseDecision
  - MicroCodebaseDecision
  - editMerge
author:
  - jacgit18
Status: refinement
Started: 
EditDate: 
Relates:
---
Clean code is clear, understandable, and maintainable. When you write clean code, you're thinking of the others who may read and interpret it later. Help others understand the purpose of your code so they can change it eventually.

Clean code principles lead to highly modular source code easier to read and test. If you think of these practices as part of a house, clean code is the foundation. Implementing clean code principles is a foundational skill that pays off especially well when refactoring code or testing code under test. 

## General rules
- Follow standard conventions.
- Keep it simple stupid. Simpler is always better. Reduce complexity as much as possible.
- Boy scout rule. Leave the campground cleaner than you found it.
- Always find root cause. Always look for the root cause of a problem.

## Design rules
- Keep configurable data at high levels.
- Prefer polymorphism to if/else or switch/case.
- Separate multi-threading code.
- Prevent over-configurability.
- Use dependency injection.
- Follow Law of Demeter. A class should know only its direct dependencies.

## Understandability tips
- Be consistent. If you do something a certain way, do all similar things in the same way.
- Use explanatory variables.
- Encapsulate boundary conditions. Boundary conditions are hard to keep track of. Put the processing for them in one place.
- Prefer dedicated value objects to primitive type.
- Avoid logical dependency. Don't write methods which works correctly depending on something else in the same class.
- Avoid negative conditionals.




## [[Naming Conventions]]
High level description


## [[Functions rules]]
High level description




Breaking down code into modular functions is a good practice for improving readability, maintainability, and reusability. Besides breaking out conditional logic, here are some other types of functionality that you might consider making modular with helper functions:  
  
1. **Input Validation:**  
- If your code involves user input or external data, create modular functions to validate and sanitize input. This helps ensure that the data your program receives is correct and safe to process.  
  
2. **Data Transformation:**  
- If your code manipulates or transforms data in a specific way, encapsulate that logic into a function. This promotes code reuse and makes it easier to understand and modify the transformation process.  
  
3. **Error Handling:**  
- Create separate functions to handle different types of errors or exceptions. This can make error-handling logic more readable and centralized.  
  
4. **File I/O Operations:**  
- If your code interacts with files, consider breaking out file I/O operations into separate functions. This could include reading from or writing to files, parsing file formats, or managing directories.  
  
5. **Algorithmic Operations:**  
- If your code involves complex algorithms, break them down into smaller, modular functions. This not only makes your code more readable but also allows for easier testing and optimization of specific parts.  
  
6. **Logging and Debugging:**  
- Create modular functions for logging messages or debugging information. This can be particularly useful for enabling or disabling debugging features easily.  
  
7. **Formatting and Display:**  
- If your code involves formatting data for display, consider creating functions responsible for formatting strings, numbers, or other types of output.  
  
8. **Utility Functions:**  
- Identify common operations or computations that are used in multiple places within your code and abstract them into utility functions. These functions can be reused across different parts of your program.  
  
9. **Network Operations:**  
- If your code interacts with network resources, encapsulate networking operations into separate functions. This includes tasks like making HTTP requests, handling sockets, or managing network connections.  
  
10. **Configuration Management:**  
- If your code relies on configuration settings, create modular functions to load and manage configurations. This makes it easier to adapt your code to different environments.  
  
By modularizing your code in this way, you not only improve the organization and readability of your code but also make it easier to maintain, test, and extend in the future. Each modular function should ideally encapsulate a specific piece of functionality, promoting the principles of separation of concerns and modularity.






## Comments rules
![[Eye in the Detail.gif]]
Comments are essentially a type of documentation that requires smart maintenance. Your code should speak for itself through well-chosen conventions. Utilize descriptive verbs in method and function names. Exclude commented-out code in production applications. Steer clear of todo's. Employ concise, one-line comments for crucial legal or explanatory information, such as regular expressions. Comment when there's an issue with a specific line of code.

- Always try to explain yourself in code.
- Don't be redundant.
- Don't add obvious noise.
- Don't use closing brace comments.
- Don't comment out code. Just remove.
- Use as explanation of intent.
- Use as clarification of code.
- Use as warning of consequences.


## Source code structure
- Separate concepts vertically.
- Related code should appear vertically dense.
- Declare variables close to their usage.
- Dependent functions should be close.
- Similar functions should be close.
- Place functions in the downward direction.
- Keep lines short.
- Don't use horizontal alignment.
- Use white space to associate related things and disassociate weakly related.
- Don't break indentation.




In TypeScript, it's generally considered best practice to initialize variables when declaring them, and to provide explicit types whenever possible. This contributes to better code readability, maintainability, and helps catch potential errors early in the development process.  
  
Here's why initializing variables is often preferred:  
  
1. **Type Inference:** When you initialize a variable with a value, TypeScript can infer its type based on that value. This allows TypeScript to catch type-related errors during development.  
  
```typescript  
let count = 5; // TypeScript infers that count is of type number  
```  
  
2. **Avoid `undefined`:** Initializing variables helps to avoid unintentional use of `undefined` values. If a variable is not assigned a value initially, its type becomes `any`, and it may lead to runtime errors if not handled properly.  
  
```typescript  
let name: string; // This variable is of type 'any' and can be undefined  
```  
  
3. **Readability:** Initializing variables at the point of declaration makes the code more readable by providing a clear starting point for the variable's value.  
  
```typescript  
let isEnabled = true; // Clear indication of the initial state  
```  
  
However, there are cases where declaring a variable without initializing it might be necessary or preferred. For example, when you want to declare a variable first and assign a value to it later based on some condition.  
  
```typescript  
let result: number;  
  
if (someCondition) {  
result = 42;  
} else {  
result = 0;  
}  
```  
  
In conclusion, prefer initializing variables at the point of declaration to leverage TypeScript's type inference and improve code clarity. Only declare variables without initialization when there's a specific reason to do so.


## Objects and data structures
- Hide internal structure.
- Prefer data structures.
- Avoid hybrids structures (half object and half data).
- Should be small.
- Do one thing.
- Small number of instance variables.
- Base class should know nothing about their derivatives.
- Better to have many functions than to pass some code into a function to select a behavior.
- Prefer non-static methods to static methods.

## Tests
- One assert per test.
- Readable.
- Fast.
- Independent.
- Repeatable.

## Code smells
- Rigidity. The software is difficult to change. A small change causes a cascade of subsequent changes.
- Fragility. The software breaks in many places due to a single change.
- Immobility. You cannot reuse parts of the code in other projects because of involved risks and high effort.
- Needless Complexity.
- Needless Repetition.
- Opacity. The code is hard to understand.









