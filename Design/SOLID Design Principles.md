---
tags:
  - CodebaseDecision
  - CleanPrinciples
  - ClassStructure
  - MacroCodebaseDecision
---
[["S"ingle Responsibility Principle]]
[["O"pen Closed Design Principle]]
[["L"iskov Substitution Principle]]
[["I"nterface Segregation Principle]]
[["D"ependency Inversion]]

The SOLID principles are a set of five principles aimed at making software designs more understandable, flexible, and maintainable. Here's an example of TypeScript code that incorporates all the SOLID principles:

```typescript
// Single Responsibility Principle (S)
class UserService {
  public createUser(user: User): void {
    // Create user logic
  }
}

class EmailService {
  public sendEmail(user: User, message: string): void {
    // Send email logic
  }
}

// Open/Closed Principle (O)
interface PaymentProcessor {
  processPayment(amount: number): void;
}

class CreditCardPayment implements PaymentProcessor {
  processPayment(amount: number): void {
    // Credit card payment logic
  }
}

class PayPalPayment implements PaymentProcessor {
  processPayment(amount: number): void {
    // PayPal payment logic
  }
}

// Liskov Substitution Principle (L)
class PaymentGateway {
  constructor(private paymentProcessor: PaymentProcessor) {}

  makePayment(amount: number): void {
    this.paymentProcessor.processPayment(amount);
  }
}

// Interface Segregation Principle (I)
interface Printable {
  print(): void;
}

class Document implements Printable {
  print(): void {
    // Document printing logic
  }
}

class Scanner implements Printable {
  print(): void {
    // Scanner printing logic
  }
}

// Dependency Inversion Principle (D)
class OrderProcessor {
  constructor(private paymentGateway: PaymentGateway) {}

  processOrder(order: Order, amount: number): void {
    // Order processing logic
    this.paymentGateway.makePayment(amount);
  }
}
```

In this code:

1. Single Responsibility Principle (S): `UserService` and `EmailService` have single responsibilities, one for user management and the other for sending emails.

2. Open/Closed Principle (O): The `PaymentProcessor` interface is open for extension (new payment methods can be added) but closed for modification (existing code doesn't need to change when new methods are added).

3. Liskov Substitution Principle (L): The `PaymentGateway` class uses the `PaymentProcessor` interface, allowing different payment methods to be used interchangeably without issues.

4. Interface Segregation Principle (I): The `Printable` interface segregates printing functionality, so classes that implement it only need to implement what's relevant to them.

5. Dependency Inversion Principle (D): The `OrderProcessor` class depends on the `PaymentGateway` abstraction, not on concrete implementations. This makes it easy to switch between payment methods without changing the `OrderProcessor` class.

These principles help create code that's more maintainable and easier to extend or change as the software evolves.