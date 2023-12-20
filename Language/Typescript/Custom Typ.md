---
tags: 
author:
  - jacgit18
Status: Capture
Started: 
EditDate: 
Relates:
---
By now, you’ve delved deep into TypeScript, mastering its pre-defined types like primitive types and arrays. Yet, the real power lies in custom types, letting you tailor type checking precisely for your needs.

Remember the example of a custom type you've already encountered: tuples. For instance, the tuple type `[string, string, number, boolean]` captures data about website users: first name (string), last name (string), age (number), and whether they have a paid account (boolean).

While pre-defined types are like standalone ingredients, custom types combine them into fully assembled meals—complex types. These complex types can be used in various ways, such as type annotations in variable declarations:

```typescript
let myVar: compType;
```

And in function type annotations:

```typescript
function testFn(param: compType): returnedCompType {
  /*Function body*/
}
```

You can even perform type inference with complex types:

```typescript
let inferredTypeVariable = testFn(myVar);
// The variable inferredTypeVariable will have the type returnedCompType.
```

## Enums

An essential complex type is Enums, which enumerate all possible values for a variable. Unlike most types, Enums restrict the potential values. For example:

```typescript
enum Direction {
  North,
  South,
  East,
  West
}

let whichWayToArcticOcean: Direction;
whichWayToArcticOcean = Direction.North; // No type error.
whichWayToArcticOcean = Direction.Southeast; // Type error: Southeast is not a valid value for Direction.
whichWayToArcticOcean = Direction.West; // Correct syntax: use Direction.West instead.
```

Under the hood, Enums use numbers. Enum values get numerical assignments based on their order. Starting from 0, subsequent values increment by 1.

You can customize the starting number:

```typescript
enum Direction {
  North = 7,
  South,
  East,
  West
}
```

Or set each number explicitly:

```typescript
enum Direction {
  North = 8,
  South = 2,
  East = 6,
  West = 4
}
```

Let's practice with Enums:

```typescript
enum Pet {
  Hamster,
  Rat,
  Chinchilla,
  Tarantula
}

const petOnSaleTS: Pet = Pet.Chinchilla;

let ordersArrayTS: [Pet, number][] = [
  [Pet.Rat, 2],
  [Pet.Chinchilla, 1],
  [Pet.Hamster, 2],
  [Pet.Chinchilla, 50]
];

ordersArrayTS.push([Pet.Jerboa, 3]);
```

### String Enums vs. Numeric Enums

Enums can be numeric or string-based. While numeric Enums use numbers, string Enums use strings, providing stricter type checks:

```typescript
enum DirectionNumber { North, South, East, West }
enum DirectionString { North = 'NORTH', South = 'SOUTH', East = 'EAST', West = 'WEST' }
```

String Enums are preferred due to their strictness, preventing assignments to arbitrary strings:

```typescript
let whichWayToAntarctica: DirectionNumber;
whichWayToAntarctica = 1; // Valid TypeScript code.
whichWayToAntarctica = DirectionNumber.South; // Valid, equivalent to the above line.

// Numeric Enums allow direct assignment of arbitrary numbers.
let whichWayToAntarctica: DirectionNumber;
whichWayToAntarctica = 943205; // No type error.

let whichWayToAntarctica: DirectionString;
whichWayToAntarctica = '(•◡•) / Arbitrary String \ (•◡•) /'; // Type error!
whichWayToAntarctica = 'SOUTH'; // STILL a type error!
whichWayToAntarctica = DirectionString.South; // The only allowable way to do this.

enum Pet {
  Hamster = 'HAMSTER',
  Rat = 'RAT',
  Chinchilla = 'CHINCHILLA',
  Tarantula = 'TARANTULA'
}

const petOnSaleTS: Pet = Pet.Chinchilla;
let ordersArrayTS: [Pet, number][] = [
  [Pet.Rat, 2],
  [Pet.Chinchilla, 1],
  [Pet.Hamster, 2],
  [Pet.Chinchilla, 50]
];
ordersArrayTS.push(['HAMSTER', 1]);
```

## Object Types

Finally, let's delve into TypeScript's object types, a crucial aspect of object-oriented programming. These types grant fine-level control over variable types. Consider this type annotation for a person object:

```typescript
let aPerson: { name: string, age: number };
```

This annotation ensures that any assigned value to `aPerson` adheres to the specified structure. Properties can be of any type, including Enums, arrays, or even other object types:

```typescript
let aCompany: {
  companyName: string,
  boss: { name: string, age: number },
  employees: { name: string, age: number }[],
  employeeOfTheMonth: { name: string, age: number },
  moneyEarned: number
};
```

For a cleaner approach, use type aliases:

```typescript
type Person = { name: string, age: number };

let aCompany: {
  companyName: string,
  boss: Person,
  employees: Person[],
  employeeOfTheMonth: Person,
  moneyEarned: number
};
```

These type aliases make the code more readable and reduce redundancy.

Let's practice with a function using object types:

```typescript
function sayHappyBirthdayWithObject(personObject: { name: string, age: number, giftWish: string, success: boolean }) {
  // Function body
}

let birthdayBabies: { name: string, age: number, giftWish: string, success: boolean }[] = [
  { name: 'Liam', age: 0, giftWish: 'karate skills', success: false },
  { name: 'Olivia', age: 0, giftWish: 'a bright future', success: true },
  { name: 'Ava', age: 0, giftWish: '$0.25', success: true }
];

birthdayBabies.forEach(sayHappyBirthdayWithObject);
```

## Type Aliases

Enhance code readability and reduce redundancy with type aliases. They're alternate names for existing types, useful for complex types like object types or tuple types:

```typescript
type MyString = string;

let myVar: MyString = 'Hi'; // Valid code.
```

For instance, simplify repetitive object type definitions:

```typescript
type Person = { name: string, age: number };

let aCompany: {
  companyName: string,
  boss: Person,
  employees: Person[],
  employeeOfTheMonth: Person,
  moneyEarned: number
};
```

Type aliases are just names; they don't influence how types work:

```typescript
type MyString = string;
type MyOtherString = string;

let firstString: MyString = '

test';
let secondString: MyOtherString = firstString; // Valid code.
```

Practice with a type alias for coordinates:

```typescript
type Coord = [number, number, string, number, number, string];

let codecademyCoordinates: Coord = [40, 43.2, 'N', 73, 59.8, 'W'];
let bermudaTCoordinates: Coord = [25, 0, 'N', 71, 0, 'W'];
```

With this refined content, you've mastered the essentials of TypeScript's custom types, including Enums, object types, and type aliases. Continue practicing and exploring advanced topics to become a TypeScript pro!