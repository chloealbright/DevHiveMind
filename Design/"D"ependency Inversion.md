---
tags:
  - SOLID
  - refine
---
Don’t ask for dependency; it will be provided to you by the framework. This has been very well implemented in the [Spring framework](http://www.java67.com/2017/11/top-5-free-core-spring-mvc-courses-learn-online.html), one of the most popular Java frameworks for writing real-worth applications.

> _The beauty of this design principle is that any class which is injected by Dependency Injection framework is easy to test with the mock object and easier to maintain because object creation code is centralized in the framework and client code is not littered with that._

There are multiple ways to implemented [**Dependency injection**](http://javarevisited.blogspot.com/2012/12/inversion-of-control-dependency-injection-design-pattern-spring-example-tutorial.html) like using bytecode instrumentation, which some AOP (Aspect Oriented Programming) framework like AspectJ does or by using proxies just like used in Spring.




## D — ependency Inversion Principle

Try to minimize the dependency between objects by using abstraction.

If for example you have a _App_ class that depends on very specialized classes; _Database_ and _Mail_ (dependencies).

Instead, we could have _App_ object that deals with _Service_ class, which is more abstract, rather than something very specific. So, now the _App_ class is not dependent on the concrete classes, but on abstraction.

And the benefit of that is we are able to replace and extend the functionality of _Service_ class without changing the _App_ class at all.

Perhaps we can replace the _Database_ and _Mail_ classes, or add additional classes like _Logger_ and _Auth_ as well.







Certainly! Let's illustrate the Dependency Inversion Principle with a TypeScript example. In this example, we'll create a simple notification system where a high-level module (`NotificationService`) depends on low-level modules that implement specific notification methods. We'll apply the Dependency Inversion Principle to decouple these dependencies using interfaces.

Here's the TypeScript code:

```typescript
// Abstraction: Define an interface for notification methods
interface NotificationProvider {
  sendNotification(message: string): void;
}

// Low-level modules implementing the interface
class EmailNotification implements NotificationProvider {
  sendNotification(message: string): void {
    console.log(`Sending email: ${message}`);
  }
}

class SMSNotification implements NotificationProvider {
  sendNotification(message: string): void {
    console.log(`Sending SMS: ${message}`);
  }
}

// High-level module depending on abstractions
class NotificationService {
  private provider: NotificationProvider; // Dependency inversion using an interface

  constructor(provider: NotificationProvider) {
    this.provider = provider;
  }

  sendNotification(message: string) {
    this.provider.sendNotification(message);
  }
}

// Usage
const emailProvider = new EmailNotification();
const smsProvider = new SMSNotification();

const emailService = new NotificationService(emailProvider);
const smsService = new NotificationService(smsProvider);

emailService.sendNotification("Hello via email");
smsService.sendNotification("Hello via SMS");
```

In this example:

1. We define an interface `NotificationProvider` that specifies a contract for sending notifications.
2. The `EmailNotification` and `SMSNotification` classes implement this interface and provide the concrete implementations for sending email and SMS notifications.
3. The `NotificationService` class represents a high-level module that depends on the `NotificationProvider` interface, which is an abstraction. It can work with any class that implements this interface.

This decouples the `NotificationService` from the specific notification methods, following the Dependency Inversion Principle. You can easily swap out different notification providers without modifying the `NotificationService` class, making the system more flexible and maintainable.