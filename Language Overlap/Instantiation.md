---
tags: 
author:
  - jacgit18
Status: Capture
Started: 
EditDate: 
Relates:
---
In programming, instantiation typically refers to the process of creating an instance of a class, which can represent an object or, in the context of servers and microservices, an independent unit or occurrence. It involves allocating memory and setting up the initial state of the instance based on the blueprint provided by the class or template.


```typescript
class MyClass {
  private myProperty: string;

  constructor(initialValue: string) {
    this.myProperty = initialValue;
  }

  public displayProperty(): void {
    console.log(this.myProperty);
  }
}

// Instantiating an object of MyClass
const myObject = new MyClass("Hello, TypeScript!");

// Calling a method on the instantiated object
myObject.displayProperty();
```

This example defines a class `MyClass` with a private property `myProperty` and a method `displayProperty()`. It then creates an instance of `MyClass` called `myObject` and calls the `displayProperty` method, printing the initialized property to the console.