---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
```typescript
// Defining a type
type Student = {
  name: string;
  age: number;
};

// Defining an interface
interface Teacher {
  name: string;
  age: number;
}
```

**How they are different ?**

1)**Interface Support Declaration Merging**.Declaration Merging means we can declare multiple interfaces with the same name, and Typescript will merge them into a single interface.

**For Example:**  

```typescript
interface Teacher {
  name: string;
}

interface Teacher {
  age: number;
}
interface Teacher {
  subject: string;
}
const teacher: Teacher = {
  name: "John",
  age: 30,
  subject:"Mathematics"
};

```

On the other hand, **we can't merge types** in Typescript.

2)**type keyword supports Computed properties but interface doesn't.**

What does Computed Properties mean?

Computed properties are a way of dynamically generating property names in an object literal in TypeScript.

In TypeScript, computed properties are supported by the **type** keyword but not by the **interface** keyword. This is because **interface** is a declaration that describes the shape of an object, and its properties must be known at compile time. On the other hand, **type** is a way of defining a custom type and allows for more flexibility, including the ability to define computed properties.

Here's an example of using computed properties in a **type** definition:  

```typescript
type Student = {
  name: string;
  age: number;
  [key: string]: unknown; // Computed property
};

const student: Student = {
  name: "John",
  age: 30,
  address: "123 ABC", // Computed property
  phone: "111-111-1111", // Computed property
};
```

**type** is very useful when we want to store key:value that is coming from API because we don't know exactly about key:vaue that is coming from API response and in future if new keys:values are added or deleted then we don't need to worry about removing it from code.