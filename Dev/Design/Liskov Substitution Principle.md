The Liskov Substitution Principle (LSP) states that objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program. Here are examples in different programming languages:

1. **Java:**
   ```java
   // Before LSP
   class Bird {
       void fly() {
           // logic to fly
       }
   }
   
   class Penguin extends Bird {
       void fly() {
           // Penguins can't fly
           throw new UnsupportedOperationException("Penguins can't fly");
       }
   }
   
   // After LSP
   interface FlyingBird {
       void fly();
   }
   
   class Bird implements FlyingBird {
       void fly() {
           // logic to fly
       }
   }
   
   class Penguin implements FlyingBird {
       void fly() {
           // Penguins can't fly
           throw new UnsupportedOperationException("Penguins can't fly");
       }
   }
   ```

2. **Python:**
   ```python
   # Before LSP
   class Bird:
       def fly(self):
           # logic to fly
           pass
   
   class Penguin(Bird):
       def fly(self):
           # Penguins can't fly
           raise NotImplementedError("Penguins can't fly")
   
   # After LSP
   from abc import ABC, abstractmethod
   
   class FlyingBird(ABC):
       @abstractmethod
       def fly(self):
           pass
   
   class Bird(FlyingBird):
       def fly(self):
           # logic to fly
           pass
   
   class Penguin(FlyingBird):
       def fly(self):
           # Penguins can't fly
           raise NotImplementedError("Penguins can't fly")
   ```

In these examples, before adhering to LSP, the `Penguin` subclass broke the expectation that all birds can fly. After applying LSP, the code ensures that subclasses (`Penguin`) can be substituted for their base class (`Bird`) without causing unexpected behavior or violating the contract defined by the base class.