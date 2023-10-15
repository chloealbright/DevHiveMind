By now, you’ve covered a lot of TypeScript. You understand all of the types that TypeScript defines for you: primitive types and arrays. That’s a real accomplishment! But don’t rest on your laurels just yet though, because TypeScript can also be used to create custom types, rather than being limited to pre-defined types. Custom types are what make TypeScript really fun and useful, because they enable type checking that’s tailored to your exact purposes. 

Actually, you have already studied an example of a custom type: tuples. For example, the tuple type [string, string, number, boolean] is a custom type that can be used with data about a website’s users: first name (string), last name (string), age (number), and whether they have a paid account (boolean). 

Pre-defined types are like ingredients: they can be used on their own. Sometimes you just need a simple string and sometimes you just want to eat a pickle! However, pre-defined types can also be combined into custom types. Custom types are like fully assembled meals (pickles, as well as cheese, bread, and burger patties). 

The complex types covered here will be usable in the same ways as the simpler types covered earlier. They can be used as type annotations during variable declaration: 

let myVar: compType;  

And they can be used as type annotations for functions: 

function testFn(param: compType): returnedCompType { 

  /*Function body*/ 

} 

And you can even do type inference with complex types: 

let inferredTypeVariable = testFn(myVar); 

// The variable inferredTypeVariable will have the type returnedCompType.


## Enums 

Our first example of a complex type is also one of the most useful: enums. We use enums when we’d like to enumerate all the possible values that a variable could have. This is in contrast to most of the other types we have studied. A variable of the string type can have any string as a value; there are infinitely many possible strings, and it would be impossible to list them all. Similarly, a variable of the boolean[] type can have any array of booleans as its value; again, the possibilities are infinite. 

enum Direction { 

  North, 

  South, 

  East, 

  West 

} 

There are many situations when we might want to limit the possible values of a variable. For example, the code above defines the enum Direction, representing four compass directions: Direction.North, Direction.South, Direction.East, and Direction.West. Any other values, like Direction.Southeast, are not allowed. Check out the example below: 

let whichWayToArcticOcean: Direction; 

whichWayToArcticOcean = Direction.North; // No type error. 

whichWayToArcticOcean = Direction.Southeast; // Type error: Southeast is not a valid value for the Direction enum. 

whichWayToArcticOcean = West; // Wrong syntax, we must use Direction.West instead.  

As shown above, an enum type can be used in a type annotation like any other type. 

Under the hood, TypeScript processes these kinds of enum types using numbers. Enum values are assigned a numerical value according to their listed order. The first value is assigned a number of 0, the second a number of 1, and onwards 

For example, if we set whichWayToArticOcean = Direction.North, then whichWayToArticOcean == 0 evaluates to true. Furthermore, we can reassign whichWayToArticOcean to a number value, like whichWayToArticOcean = 2, and it does not raise a type error. This is because Direction.North, Direction.South, Direction.East, and Direction.West are equal to 0, 1, 2, and 3, respectively. 

We can change the starting number, writing something like 

enum Direction { 

  North = 7, 

  South, 

  East, 

  West 

} 

Here, Direction.North, Direction.South, Direction.East, and Direction.West are equal to 7, 8, 9, and 10, respectively. 

We can also specify all numbers separately, if needed: 

enum Direction { 

  North = 8, 

  South = 2, 

  East = 6, 

  West = 4 

} 

(These numbers match up with the keys on the numpad portion of many keyboards.) 

Let’s get some practice with TypeScript’s enums. 

let petOnSale = 'chinchilla'; 

let ordersArray = [ 

  ['rat', 2],  

  ['chinchilla', 1],  

  ['hamster', 2],  

  ['chinchilla', 50] 

]; 

// Write your code below: 

enum Pet { 

  Hamster, 

  Rat, 

  Chinchilla, 

  Tarantula 

} 

const petOnSaleTS : Pet = Pet.Chinchilla; 

const ordersArrayTS : [Pet, number][] = [ 

  [Pet.Rat, 2], 

  [Pet.Chinchilla, 1], 

  [Pet.Hamster, 2], 

  [Pet.Chinchilla, 50] 

] 

ordersArrayTS.push([Pet.Jerboa, 3]) 

## String Enums vs. Numeric Enums 

The enums we have studied so far are referred to as numeric enums, since they are based on numbers. TypeScript also allows us to use enums based on strings, referred to as string enums. They are defined very similarly: 

enum DirectionNumber { North, South, East, West } 

enum DirectionString { North = 'NORTH', South = 'SOUTH', East = 'EAST', West = 'WEST' } 

With numeric enums, the numbers could be assigned automatically, but with string enums we must write the string explicitly, as shown above. Technically, any string will do: North = 'JabberWocky' is a valid value definition. However, it is much better to use the convention shown here (North = 'NORTH'), where the string value of the enum variable is just the capitalized form of the variable name. This way, error messages and logs will be much more informative. 

We recommend to always use string enums because numeric enums allow for some behaviors that can let bugs sneak into our code. For example, numbers can be assigned directly to numeric enum variables: 

let whichWayToAntarctica: DirectionNumber; 

whichWayToAntarctica = 1; // Valid TypeScript code. 

whichWayToAntarctica = DirectionNumber.South; // Valid, equivalent to the above line. 

Strangely, even assigning arbitrary numbers, as in whichWayToAntarctica = 943205, will not lead to type errors. 

String enums are much more strict. With string enums, variables cannot be assigned to strings at all! 

let whichWayToAntarctica: DirectionString; 

whichWayToAntarctica = '\ (•◡•) / Arbitrary String \ (•◡•) /'; // Type error! 

whichWayToAntarctica = 'SOUTH'; // STILL a type error! 

whichWayToAntarctica = DirectionString.South; // The only allowable way to do this. 

let petOnSale = 'chinchilla'; 

let ordersArray = [ 

  ['rat', 2],  

  ['chinchilla', 1],  

  ['hamster', 2],  

  ['chinchilla', 50] 

]; 

// Write your code below: 

enum Pet { 

  Hamster = 'HAMSTER', 

  Rat = 'RAT', 

  Chinchilla = 'CHINCHILLA', 

  Tarantula = 'TARANTULA' 

} 

const petOnSaleTS : Pet = Pet.Chinchilla; 

let ordersArrayTS : [Pet, number][] = [ 

  [Pet.Rat, 2],  

  [Pet.Chinchilla, 1],  

  [Pet.Hamster, 2],  

  [Pet.Chinchilla, 50] 

]; 

ordersArrayTS.push(['HAMSTER', 1]);



## Object Types 

It’s time, we can finally discuss object-oriented programming and how it relates to TypeScript! TypeScript’s object types are extremely useful, as they allow us extremely fine-level control over variable types in our programs. They’re also the most common custom types, so we’ll have to understand them if we want to read other people’s programs. 

Here’s a type annotation for an object meant to represent a person: 

let aPerson: {name: string, age: number}; 

The type annotation looks like an object literal, but instead of values appearing after properties, we have types. Notice that the variable aPerson has yet to be assigned a value. Trying to assign a value to aPerson that doesn’t have name and age properties of the specified types will lead to a type error: 

aPerson = {name: 'Aisle Nevertell', age: "wouldn't you like to know"}; // Type error: age property has the wrong type. 

aPerson = {name: 'Kushim', yearsOld: 5000}; // Type error: no age property.  

aPerson = {name: 'User McCodecad', age: 22}; // Valid code.  

Above, in the case of Kushim, the object had properties of the correct types. Still, a type error was thrown because the properties didn’t have the correct names. 

TypeScript places no restrictions on the types of an object’s properties. They can be enums, arrays, and even other object types! 

let aCompany: { 

  companyName: string,  

  boss: {name: string, age: number},  

  employees: {name: string, age: number}[],  

  employeeOfTheMonth: {name: string, age: number},   

  moneyEarned: number 

}; 

This is only an introduction to TypeScript’s object types. A thorough description would deserve a lesson of its own (which we will soon arrive at if we keep learning). For now, let’s practice the basics some more. 

function sayHappyBirthdayWithObject(personObject: {name: string, age: number, giftWish: string, success: boolean}){ 

  let output =''; 

  output += 'Happy Birthday ' 

         + personObject.name + '! '; 

  output += 'You are now '  

         + personObject.age + ' years old! '; 

  output += 'Your birthday wish was to receive '  

         + personObject.giftWish  

         + '. And guess what? You will '; 

  if (!personObject.success){ 

    output += 'not '; 

  } 

  output += 'receive it! \n'; 

  console.log(output); 

} 

let birthdayBabies: {name: string, age: number, giftWish: string, success: boolean}[] = [ 

  {name: 'Liam', age: 0, giftWish: 'karate skills', success: false},  

  {name: 'Olivia', age: 0, giftWish: 'a bright future', success:true},  

  {name: 'Ava', age: 0, giftWish: '$0.25', success:true} 

];  

birthdayBabies.forEach(s 

Type Aliases 

One great way to customize the types in our programs is to use type aliases. These are alternative type names that we choose for convenience. We use the format type <alias name> = <type>: 

type MyString = string; 

let myVar: MyString = 'Hi'; // Valid code. 

Coming up with alternate names for string may not be very useful, but this can be done with any type whatsoever. Type aliases are truly useful for referring to complicated types that need to be repeated, especially object types and tuple types. Recall our earlier company example: 

let aCompany: {  

  companyName: string,  

  boss: { name: string, age: number },  

  employees: { name: string, age: number }[],  

  employeeOfTheMonth: { name: string, age: number },   

  moneyEarned: number 

}; 

There’s so much needless repetition here! (And the more times we repeat something, the more opportunity there is for typos.) This can be cleaned up with type aliases: 

type Person = { name: string, age: number }; 

let aCompany: { 

  companyName: string,  

  boss: Person,  

  employees: Person[],  

  employeeOfTheMonth: Person,   

  moneyEarned: number 

}; 

Everyone knows the famous Shakespeare quotation “What’s in a name? That which we call a string by any other name would smell as sweet”. TypeScript aliases are nothing more than names. They have absolutely no influence over how types work. For example, the following code does not lead to type errors: 

type MyString = string;  

type MyOtherString = string; 

let firstString: MyString = 'test'; 

let secondString: MyOtherString = firstString; // Valid code. 

The reason this works is that MyString and MyOtherString are not distinct types. They are just alternative names for the same thing. 

// Add your type alias below: 

type Coord = [number, number, string, number, number, string]; 

let codecademyCoordinates: Coord = [40, 43.2, 'N', 73, 59.8, 'W']; 

let bermudaTCoordinates: Coord = [25, 0, 'N', 71, 0, 'W']; 

ayHappyBirthdayWithObject);