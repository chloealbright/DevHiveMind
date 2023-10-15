Certainly! The Single Responsibility Principle (SRP) is one of the SOLID principles in object-oriented programming, emphasizing that a class should have only one reason to change. Here are examples in different programming languages:

1. **Java:**
   ```java
   // Before SRP
   class Report {
       String content;
       
       void generateReport() {
           // logic to generate report
       }
       
       void saveToFile() {
           // logic to save report to file
       }
   }
   
   // After SRP
   class Report {
       String content;
       
       void generateReport() {
           // logic to generate report
       }
   }
   
   class ReportSaver {
       void saveToFile(Report report) {
           // logic to save report to file
       }
   }
   ```

2. **Python:**
   ```python
   # Before SRP
   class Report:
       def __init__(self, content):
           self.content = content
       
       def generate_report(self):
           # logic to generate report
       
       def save_to_file(self):
           # logic to save report to file
           
   # After SRP
   class Report:
       def __init__(self, content):
           self.content = content
       
       def generate_report(self):
           # logic to generate report
           
   class ReportSaver:
       def save_to_file(self, report):
           # logic to save report to file
   ```

These examples demonstrate separating the responsibilities of generating a report and saving it to a file into distinct classes, adhering to the Single Responsibility Principle.