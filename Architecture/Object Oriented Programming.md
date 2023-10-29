

  






## Polymorphism

- Polymorphism
  - Means “many forms,” which allows methods with similar signatures to accomplish different tasks.
  - It consists of either compile time or runtime polymorphism.
    - Compile time polymorphism involves method overloading when two methods with the same name have different required parameters.
    - Run time polymorphism is resolved through method overriding, called through the reference variable of a superclass or parent class. Overriding methods have the same signature.






# Testing Private Methods

- How do you test a private method?
  - To test a private method, create an instance of that class and try to print the output of the variable or method that was private.
    - You could try to call the private method in a class that should have access and asserts that the call failed.

