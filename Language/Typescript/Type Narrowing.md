---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
 TypeScript can understand how our code will execute at runtime so that it can infer more specific types while we write code. This is called type narrowing.

When compiling TypeScript code to JavaScript, the compiler will throw any errors related to variable types. This process of compilation involves giving the TypeScript compiler the information it needs to perform type checks. Therefore, when we give our variables specific types, these types are reinforced by the compiler/TypeScript.

If TypeScript could only check types at compile-time, that would still be useful, but it turns out that TypeScript can do so much more. TypeScript has the ability to evaluate how our runtime code will perform, and then infer variable types for us. When the compiler notices an error, it will complain when running tsc and also by showing a red squiggly line below the code in the editor.

Evaluating runtime code can be really useful when our programs have variables of multiple types. In the case of unions, TypeScript can hone in on a more narrow type by evaluating our runtime code. For example:

function formatDate(date: string | number) {

  // date can be a number or string here

  if (typeof date === 'string') {

    // date must be a string here

  }

}

In the example above, the date parameter has a union type of string | number. Inside the body of formatDate(), there’s a conditional that checks if date is a 'string'. If the condition is met, then TypeScript can infer that date must be a string type within the conditional. It will allow us to call methods and properties that are allowed on string types. This is called type narrowing. Type narrowing is when TypeScript can infer more specific types based on the variable’s surrounding code.

Type guards

One way that TypeScript can narrow a type is with a conditional statement that checks if a variable is a specific type. This pattern is called a type guard. Type guards can use a variety of operators that check for a variable’s type. One operator we can use is typeof. For example:

function formatDate(date: string | number) {

  // date can be a number or string here

  if (typeof date === 'string') {

    // date must be a string type

  }

}

In this example, TypeScript is able to infer that date must be a 'string' inside the conditional because typeof checked that date is a 'string'. TypeScript evaluated what our code would do at runtime and then inferred a more specific type for date.

TypeScript can recognize typeof type guards that check for these specific values: 'string', 'number', 'boolean', and 'symbol'.

function formatStatistic(stat: string | number) {

  if (typeof stat === 'number') {

    return stat.toFixed(2);

  }

  if (typeof stat === 'string') {

    return stat.toUpperCase();

  }

}

console.log(formatStatistic('Win'));

console.log(formatStatistic(0.364));

Using in with Type Guards

As we write more types, we’re bound to create custom types to better describe our data’s properties and methods. While using typeof can get us pretty far, sometimes we want to see if a specific method exists on a type instead of a type like 'string'. That’s where the in operator comes into play. The in operator checks if a property exists on an object itself or anywhere within its prototype chain. Take a look at this example:

type Tennis = {

  serve: () => void;

}

type Soccer = {

  kick: () => void;

}

function play(sport: Tennis | Soccer) {

  if ('serve' in sport) {

    return sport.serve();

  }

  if ('kick' in sport) {

    return sport.kick();

  }

}

In the example above, we check if the 'serve' property exists on sport with the in operator. The 'serve' property must exist inside the conditional, so TypeScript can narrow sport‘s type inside the conditional to be of type Tennis. This type narrowing is possible because TypeScript recognizes in as a type guard.

type Cat = {

  name: string;

  run: () => string;

}

type Fish = {

  name: string;

  swim: () => string;

}

const siameseCat = {

  name: 'Proxie',

  run: () => 'pitter pat'

}

const bettaFish = {

  name: 'Neptune',

  swim: () => 'bubble blub'

}

function move(pet: Cat | Fish) {

  if ('run' in pet) {

    return pet.run();

  }

  if ('swim' in pet) {

    return pet.swim();

  }

}

console.log(move(siameseCat))

Narrowing with else

In our previous examples, we’ve used two separate if statements as type guards to handle each possible type. It turns out that TypeScript can recognize the else block of an if/else statement as being the opposite type guard check of the if statement’s type guard check. For example:

function formatPadding(padding: string | number) {

  if (typeof padding === 'string') {

    return padding.toLowerCase();

  } else {

    return `${padding}px`;

  }

}

In the example above, the formatPadding() function can take in a value for CSS padding like the number 32 or the string '0 32px'. Then a type guard is used to figure out how to format the padding argument.

The type guard typeof padding === 'string' tells TypeScript that padding within the if statement’s block must be a string. Going further, TypeScript is also able to infer that, since the padding argument is typed as the union string | number, that padding must be a number type within the else block.

Since TypeScript can understand how our code will work at runtime, it’s able to infer specific types for us, like with the else of an if/else statement.

type Pasta = {

  menuName: string;

  boil: () => string;

}

type Meat = {

  menuName: string;

  panFry: () => string;

}

const fettuccine = {

  menuName: 'Fettuccine',

  boil: () => "Heat water to 212 degrees",

}

const steak = {

  menuName: 'New York Strip Steak',

  panFry: () => "Heat oil to 350 degrees",

}

function prepareEntree(entree: Pasta | Meat) {

  if ('boil' in entree) {

    return entree.boil();

  } else {

    return entree.panFry();

  }

}

console.log(prepareEntree(fettuccine));

Narrowing After a Type Guard

TypeScript’s ability to infer types after a type guard stretches even further than inferring the type within an else statement. TypeScript can also type narrow without an else statement, provided that there’s a return statement within the type guard. Take a look at this example:

type Tea = {

  steep: () => string;

}

type Coffee = {

  pourOver: () => string;

}

function brew(beverage: Coffee | Tea) {

  if ('steep' in beverage) {

    return beverage.steep();

  }

  return beverage.pourOver();

}

In the conditional, we immediately return beverage.steep(). Once we encounter a return statement, the function execution stops. Any code that was meant to work with a beverage of type Tea will be executed and returned within the conditional. TypeScript then infers that the code following the conditional must be of type Coffee.

type Metal = {

  magnetize: () => string;

}

type Glass = {

  melt: () => string;

}

const iron = {

  magnetize: () => 'Electromagnet activated'

}

const bottle = {

  melt: () => 'Furnace set to 2,700 degrees'

}

function recycle(trash: Metal | Glass) {

  // Add your code below:

  if ('magnetize' in trash) {

  return trash.magnetize();

  }

  return trash.melt();

}

console.log(recycle(iron));