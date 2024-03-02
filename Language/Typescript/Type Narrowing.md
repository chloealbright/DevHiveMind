---
tags:
  - types
  - FunctionTypes
  - javascript
Comments: This documentation discusses type narrowing.
author:
  - jacgit18
  - chatgpt
Status: Done
Started: 
EditDate: 2024-03-02
Relates:
---
### TypeScript and Type Narrowing

In TypeScript, the ability to understand and infer more specific types during runtime is known as "type narrowing." When we compile TypeScript code to JavaScript, the compiler performs type checks and uses the provided type information to catch any errors related to variable types. This process extends beyond simple compilation, as TypeScript's capability to evaluate runtime code allows it to infer specific types based on the actual execution of the code.

### Unions and Type Narrowing

TypeScript excels in handling variables with union types, where a variable can have multiple possible types. Type narrowing comes into play when TypeScript evaluates the runtime code and infers more specific types based on the variable's surrounding context. For example:

```typescript
function formatDate(date: string | number) {
  // date can be a number or string here
  if (typeof date === 'string') {
    // date must be a string here
  }
}
```

In this scenario, TypeScript narrows down the type of `date` to `'string'` within the conditional block, allowing for the use of string-specific methods and properties.

### Type Guards

TypeScript employs type guards to narrow down variable types using conditional statements that check for specific types. One commonly used type guard is `typeof`. For instance:

```typescript
function formatStatistic(stat: string | number) {
  if (typeof stat === 'number') {
    return stat.toFixed(2);
  }
  if (typeof stat === 'string') {
    return stat.toUpperCase();
  }
}
```

Here, TypeScript uses `typeof` as a type guard to determine whether `stat` is a `'number'` or a `'string'` at runtime.

### Using `in` with Type Guards

The `in` operator serves as a type guard when checking for the existence of a property on an object or within its prototype chain. For example:

```typescript
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
```

Here, TypeScript uses `in` to check for the presence of the `'serve'` property, narrowing down the type within the conditional block.

### Type Narrowing with `else`

TypeScript recognizes the `else` block of an `if/else` statement as the opposite type guard check of the `if` statement's type guard check. For example:

```typescript
function formatPadding(padding: string | number) {
  if (typeof padding === 'string') {
    return padding.toLowerCase();
  } else {
    return `${padding}px`;
  }
}
```

In this case, TypeScript infers that `padding` is a `'number'` within the `else` block since it was determined to be a `'string'` in the preceding `if` statement.

### Type Narrowing After a Type Guard

TypeScript's type inference extends beyond an `else` block. If there's a return statement within a type guard, TypeScript can infer types without needing an `else` statement. For example:

```typescript
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
```

Here, TypeScript immediately infers that the code following the conditional must be of type `Coffee` after encountering the `return` statement within the `if` block.

These examples illustrate how TypeScript's type narrowing enhances type safety by dynamically inferring specific types based on the actual execution of code.