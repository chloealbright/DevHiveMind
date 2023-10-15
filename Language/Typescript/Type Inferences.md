JavaScript allows us to assign any value to any variable. That makes it very flexible to use, which can be good for getting started quickly in coding. In practice, variables that are assigned values of multiple types throughout a program can be very confusing or lead to bugs.

One of the first things we’ll discover with TypeScript is that when we declare a variable with an initial value, the variable can never be reassigned a value of a different data type. This is an example of type inference: everywhere in our program, TypeScript expects the data type of the variable to match the type of the value initially assigned to it at declaration.

TypeScript recognizes JavaScript’s built-in “primitive” data types:

boolean

number

null

string

undefined

If we try to reassign a variable to a value of a different type, TypeScript will surface an error.

let order = 'first';

order = 1;

Running the TypeScript code above will result in the following error being surfaced in the terminal: Type '1' is not assignable to type 'string'.

TypeScript’s type system is telling us that order is expected to be the primitive type string, but we’re trying to assign it a value of type number. That’s not allowed: variables can only be assigned the types expected by the type system.

We can fix this complaint by changing the new value to be the expected string type:

let order = 'first';

order = '1';

Use the tsc command to run the index.ts file and surface any type errors.