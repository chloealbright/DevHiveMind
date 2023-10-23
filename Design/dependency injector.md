---
tags:
  - SOLID
  - refine
---
A dependency injector is a component or framework that facilitates the process of managing and resolving dependencies in a software system. It provides mechanisms to automatically instantiate and inject dependencies into classes, relieving developers from manually wiring dependencies together.

A dependency injector typically follows a set of principles:

1. Dependency Registration: The injector allows developers to register dependencies by associating them with their corresponding interfaces or classes.

2. Dependency Resolution: When a class requests a dependency, the injector resolves it by looking up the registered dependencies based on their associated interfaces or classes.

3. Dependency Injection: The injector automatically injects the resolved dependencies into the requesting class, either through constructor injection, setter injection, or other injection methods.

Here's a simple example in Java using the popular dependency injection framework, Spring:

```java
public interface MessageService {
    void sendMessage(String message);
}

public class EmailService implements MessageService {
    public void sendMessage(String message) {
        System.out.println("Sending email: " + message);
    }
}

public class SMSService implements MessageService {
    public void sendMessage(String message) {
        System.out.println("Sending SMS: " + message);
    }
}

public class NotificationService {
    private MessageService messageService;

    public NotificationService(MessageService messageService) {
        this.messageService = messageService;
    }

    public void sendNotification(String message) {
        messageService.sendMessage(message);
    }
}

public class Main {
    public static void main(String[] args) {
        // Create an instance of the dependency injector (Spring container)
        ApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);

        // Retrieve an instance of the NotificationService from the injector
        NotificationService notificationService = context.getBean(NotificationService.class);

        // Use the NotificationService, which has its dependency automatically injected
        notificationService.sendNotification("Hello, World!");
    }
}
```

In this example, we have an interface `MessageService` and two implementations: `EmailService` and `SMSService`. The `NotificationService` class depends on the `MessageService` interface.

The `Main` class demonstrates the usage of the dependency injector (Spring container). It creates an instance of the injector using an application configuration class (`AppConfig`), which defines the mappings between interfaces and their corresponding implementations.

By retrieving the `NotificationService` bean from the injector, the injector automatically resolves the `MessageService` dependency and injects an instance of either `EmailService` or `SMSService`, depending on the configuration.

When calling `notificationService.sendNotification("Hello, World!");`, the appropriate implementation of `MessageService` (either email or SMS) is used to send the notification.

The dependency injector handles the creation, resolution, and injection of dependencies, allowing for loosely coupled and modular code.