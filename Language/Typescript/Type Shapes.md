Because TypeScript knows what types our objects are, it also knows what shapes our objects adhere to. An object’s shape describes, among other things, what properties and methods it does or doesn’t contain.

The built-in types in JavaScript each have known properties and methods that always exist. All strings, for example, are known to have a .length property and .toLowerCase() method.

"OH".length; // 2

"MY".toLowerCase(); // "my"

TypeScript’s tsc command will let you know if your code tries to access properties and methods that don’t exist:

"MY".toLowercase();

// Property 'toLowercase' does not exist on type '"MY"'.

// Did you mean 'toLowerCase'?

Through this knowledge of type shapes, TypeScript helps us quickly locate bugs in our code.