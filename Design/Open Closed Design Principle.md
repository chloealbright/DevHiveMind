The Open/Closed Principle (OCP) states that a class should be open for extension but closed for modification. Here are examples in different programming languages:

1. **Java:**
   ```java
   // Before OCP
   class Shape {
       String type;
       
       void draw() {
           if (type.equals("circle")) {
               // draw circle
           } else if (type.equals("square")) {
               // draw square
           }
           // more shapes...
       }
   }
   
   // After OCP
   interface Shape {
       void draw();
   }
   
   class Circle implements Shape {
       void draw() {
           // draw circle
       }
   }
   
   class Square implements Shape {
       void draw() {
           // draw square
       }
   }
   ```

2. **Python:**
   ```python
   # Before OCP
   class Shape:
       def __init__(self, type):
           self.type = type
       
       def draw(self):
           if self.type == "circle":
               # draw circle
           elif self.type == "square":
               # draw square
           # more shapes...
   
   # After OCP
   from abc import ABC, abstractmethod
   
   class Shape(ABC):
       @abstractmethod
       def draw(self):
           pass
   
   class Circle(Shape):
       def draw(self):
           # draw circle
           
   class Square(Shape):
       def draw(self):
           # draw square
   ```

In the examples, before adhering to OCP, the `Shape` class had conditional statements to handle different shapes. After applying OCP, the code is open for extension by introducing new shape classes (`Circle`, `Square`) without modifying the existing `Shape` class, thus adhering to the Open/Closed Principle.