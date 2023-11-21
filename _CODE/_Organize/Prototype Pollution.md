---
tags:
  - security
  - javascript
author:
  - jacgit18
Status: refinement
Started: 2023-11-21
EditDate: 
Relates:
---
Prototype pollution is a security vulnerability in JavaScript that occurs when an attacker manipulates the prototype of an object to introduce or modify properties and methods. This can have unintended consequences, leading to security risks. Here's an explanation of prototype pollution:

### Understanding Prototype Pollution:

1. **Prototypes in JavaScript:**
   JavaScript is a prototype-based language, meaning objects can inherit properties and methods from other objects through their prototypes. Each object, including functions, has a prototype from which it inherits. You also should watch out for libraries because they could have prototype pollution  

2. **Object Prototype Manipulation:**
   Attackers exploit the ability to manipulate an object's prototype to inject or modify properties at a broader scope. If an object's prototype is altered, the changes affect all instances derived from that prototype.

### Example of Prototype Pollution:

Consider the following example:

```javascript
// Initial object
const baseObject = {};

// User input with potential pollution
const userInput = '{"__proto__": {"polluted": true}}';
const userObject = JSON.parse(userInput);

// Extending the base object with user input
Object.assign(baseObject, userObject);

// Now baseObject inherits the polluted property
console.log(baseObject.polluted); // Outputs: true
```

In this example, the user manipulates the prototype using the `__proto__` property, introducing a `polluted` property to all objects derived from `baseObject`.

### Risks and Consequences:

1. **Unintended Property Overwrites:**
   Prototype pollution can lead to unintended overwrites of existing properties or the introduction of malicious properties. This can result in unexpected behavior and security vulnerabilities.

2. **Security Implications:**
   If sensitive properties or methods are affected, an attacker could compromise the integrity and security of the application. This is particularly dangerous in environments where user input is not properly validated.

### Mitigating Prototype Pollution:

1. **Input Validation:**
   Ensure that user inputs, especially those derived from external sources, are properly validated and sanitized to prevent malicious input.

2. **Immutable Objects:**
   Use immutable objects where possible to avoid unintentional modifications. Libraries like `Object.freeze` can help make objects immutable.

3. **Property Whitelisting:**
   Explicitly define the properties that an object can have, preventing unexpected additions through prototype pollution.

4. **Security Tooling:**
   Employ security tools and static analysis to detect and prevent prototype pollution vulnerabilities in the codebase.

Understanding and mitigating prototype pollution is crucial for building secure JavaScript applications. Developers should be vigilant in validating and sanitizing user inputs to prevent such vulnerabilities.




JavaScript's prototype inheritance provides a mechanism for objects to inherit properties and methods from other objects. While JavaScript does not have traditional classes like some other programming languages, it introduces syntax sugar that mimics class-based syntax. This includes the `class`, `extends`, and `super` keywords.

### Prototype Inheritance:

1. **Prototype Chain:**
   JavaScript objects have a prototype, which is another object from which they inherit properties. This creates a prototype chain where objects can inherit from each other.

2. **Object Creation:**
   Objects in JavaScript can be created using constructor functions or object literals. Constructor functions, when invoked with the `new` keyword, create instances with a link to their prototype.

### Class Syntax Sugar:

1. **Class Keyword:**
   The `class` keyword was introduced in ECMAScript 2015 (ES6) to provide a more familiar syntax for defining constructor functions and their prototypes.

   ```javascript
   class Animal {
     constructor(name) {
       this.name = name;
     }

     speak() {
       console.log(`${this.name} makes a sound.`);
     }
   }
   ```

2. **Extends Keyword:**
   The `extends` keyword is used to create a subclass that inherits from a superclass. It simplifies the process of prototype chaining.

   ```javascript
   class Dog extends Animal {
     speak() {
       console.log(`${this.name} barks.`);
     }
   }
   ```

   Here, `Dog` is a subclass extending the `Animal` superclass, inheriting its properties and methods.

3. **Super Keyword:**
   The `super` keyword is used to call the constructor of the superclass within the constructor of the subclass.

   ```javascript
   class Dog extends Animal {
     constructor(name, breed) {
       super(name); // Calls the constructor of the superclass
       this.breed = breed;
     }
   }
   ```

### Syntax Sugar for Class-like Inheritance:

While JavaScript's prototype inheritance is different from classical inheritance, the class syntax sugar provides a more familiar and readable way to work with prototypes. It makes the language feel more like class-based languages, even though it is still based on prototypes.

```javascript
class Shape {
  constructor(color) {
    this.color = color;
  }

  draw() {
    console.log(`Drawing a ${this.color} shape.`);
  }
}

class Circle extends Shape {
  constructor(color, radius) {
    super(color);
    this.radius = radius;
  }

  draw() {
    console.log(`Drawing a ${this.color} circle with radius ${this.radius}.`);
  }
}
```

In this example, the `Circle` class extends the `Shape` class, showcasing the class-based syntax sugar for prototype inheritance in JavaScript.




Certainly! The class syntax sugar in JavaScript is essentially a more convenient way of expressing prototype-based inheritance. Here's the equivalent code using prototype-based syntax:

```javascript
// Prototype-based Animal "class"
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function () {
  console.log(`${this.name} makes a sound.`);
};

// Prototype-based Dog "subclass" extending Animal
function Dog(name, breed) {
  Animal.call(this, name); // Call the constructor of the superclass
  this.breed = breed;
}

// Inherit from Animal's prototype
Dog.prototype = Object.create(Animal.prototype);

// Set Dog's constructor to itself
Dog.prototype.constructor = Dog;

// Override the speak method
Dog.prototype.speak = function () {
  console.log(`${this.name} barks.`);
};

// Creating instances using the "classes"
const genericAnimal = new Animal('Generic');
genericAnimal.speak(); // Outputs: Generic makes a sound.

const myDog = new Dog('Buddy', 'Labrador');
myDog.speak(); // Outputs: Buddy barks.
```

In this prototype-based version:

- The `Animal` "class" is defined with a constructor function and methods added to its prototype.
- The `Dog` "subclass" is created by calling `Animal.call(this, name)` in its constructor to initialize the superclass properties.
- `Object.create(Animal.prototype)` sets up the prototype chain, linking `Dog`'s prototype to `Animal`'s prototype.
- `Dog.prototype.constructor = Dog;` corrects the constructor property, which is overridden by the previous line.
- Methods like `speak` are added to the `Dog` prototype, allowing method overriding.

While this version is more verbose, it illustrates the underlying prototype inheritance mechanism that the class syntax sugar is built upon in JavaScript.





Protecting against prototype pollution involves implementing defensive coding practices to mitigate the risks associated with manipulating object prototypes. Here are some best practices to help safeguard against prototype pollution:

1. **Input Validation:**
   Always validate and sanitize user inputs, especially when dealing with data that might be used to modify object prototypes. Avoid blindly trusting and using user-provided data without proper validation.

2. **Avoid Modifying Object Prototype Globally:**
   Refrain from modifying built-in object prototypes globally, as this can have unintended consequences across the entire application. Instead, extend or modify prototypes locally for specific use cases when necessary.

3. **Use Object.freeze() and Object.seal():**
   The `Object.freeze()` and `Object.seal()` methods can be used to make objects immutable or prevent further additions/deletions of properties. Freezing or sealing objects can help prevent unintended modifications.

   ```javascript
   const safeObject = Object.freeze({});
   safeObject.newProperty = 'This will throw an error'; // Attempting to modify a frozen object will fail
   ```

4. **Property Whitelisting:**
   Explicitly define the properties that an object can have. This can help prevent unexpected additions through prototype pollution.

   ```javascript
   const allowedProperties = ['prop1', 'prop2'];
   const userObject = { prop1: 'value1', prop2: 'value2', '__proto__': { pollute: 'unexpected' } };

   // Filtering out unexpected properties
   const sanitizedObject = Object.fromEntries(Object.entries(userObject).filter(([key]) => allowedProperties.includes(key)));
   ```

5. **Avoid Using for...in Loop for Object Iteration:**
   The `for...in` loop iterates over all enumerable properties, including those in the prototype chain. Instead, use `Object.keys()`, `Object.values()`, or `Object.entries()` to iterate over object properties.

   ```javascript
   const obj = { a: 1, b: 2 };
   for (const key in obj) {
     console.log(key); // Avoid using for...in to prevent prototype pollution
   }
   ```

6. **Security Audits and Tools:**
   Regularly perform security audits on your codebase and use static analysis tools to detect and prevent potential prototype pollution vulnerabilities. Tools like ESLint with relevant plugins can help identify risky patterns.

7. **Educate Development Team:**
   Ensure that the development team is aware of the risks associated with prototype pollution and follows best practices. Providing training on secure coding practices is crucial.

By incorporating these practices into your development process, you can reduce the risk of falling victim to prototype pollution vulnerabilities in your JavaScript applications. Always stay informed about emerging security threats and updates in the JavaScript ecosystem to maintain a secure codebase.