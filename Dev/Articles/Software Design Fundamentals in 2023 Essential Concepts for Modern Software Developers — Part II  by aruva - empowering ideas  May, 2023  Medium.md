In [Part 1](https://aruva.medium.com/software-design-fundamentals-in-2023-essential-concepts-for-modern-software-developers-part-i-ae7d9893ff59) of the series, we looked at architectural patterns, including monolithic and microservices architecture, load balancing and reverse proxies. We did a quick overview of relational and NoSQL databases., Communication methodologies and basic Design Pattern principles.

This part of the series will focus on programming principles like SOLID. We will also discuss software development methodologies like Agile, Scrum, DevOps, Version Control systems, Testing and Quality Assurance, Test Driven Development (TDD), and continuous integration and deployment (CI/CD).

![](https://miro.medium.com/v2/resize:fit:700/0*VmdGqNBtS5fbWo-3)



## 6\. SOLID Principles

SOLID is an acronym for five design principles that help improve software systems' maintainability, flexibility, and scalability. These principles are:

1.  **Single Responsibility Principle (SRP)**: A class should have only one reason to change, meaning it should have only one responsibility.

```python
# Violates SRP  
class ReportGenerator:  
    def gather_data(self):  
        pass  
  
    def generate_report(self):  
        pass  
  
# Adheres to SRP  
class DataGatherer:  
    def gather_data(self):  
        pass  
  
class ReportGenerator:  
    def generate_report(self):  
        pass
```

**2\. Open/Closed Principle (OCP):** Software entities (classes, modules, functions, etc.) should be open for extension but closed for modification.

```python
# Violates OCP  
class AreaCalculator:  
    def calculate_area(self, shapes):  
        total_area = 0  
        for shape in shapes:  
            if isinstance(shape, Rectangle):  
                total_area += shape.width * shape.height  
            elif isinstance(shape, Circle):  
                total_area += math.pi * shape.radius * shape.radius  
        return total_area  
  
# Adheres to OCP  
class Shape:  
    def area(self):  
        pass  
  
class Rectangle(Shape):  
    def area(self):  
        return self.width * self.height  
  
class Circle(Shape):  
    def area(self):  
        return math.pi * self.radius * self.radius  
  
class AreaCalculator:  
    def calculate_area(self, shapes):  
        return sum(shape.area() for shape in shapes)

```

**3\. Liskov Substitution Principle (LSP):** Objects of a derived class should be able to replace objects of the base class without affecting the correctness of the program.

```python
# Violates LSP  
class Bird:  
    def fly(self):  
        pass  
  
class Penguin(Bird):  
    def fly(self):  
        raise NotImplementedError("Penguins can't fly!")  
  
# Adheres to LSP  
class Bird:  
    def fly(self):  
        pass  
  
class Penguin(Bird):  
    pass

```

**4\. Interface Segregation Principle (ISP)**: Clients should not be forced to depend on interfaces they do not use. Instead, large interfaces should be broken down into smaller, more specific interfaces.

```python
# Violates ISP  
class AllInOnePrinter:  
    def print(self):  
        pass  
  
    def scan(self):  
        pass  
  
    def fax(self):  
        pass  
  
# Adheres to ISP  
class Printer:  
    def print(self):  
        pass  
  
class Scanner:  
    def scan(self):  
        pass  
  
class FaxMachine:  
    def fax(self):  
        pass

```

**5\. Dependency Inversion Principle (DIP)**: High-level modules should not depend on low-level modules. Both should depend on abstractions. Abstractions should not depend on details; details should depend on abstractions.

```python
# Violates DIP  
class MySQLDatabase:  
    def connect(self):  
        pass  
  
class Application:  
    def __init__(self, db):  
        self.db = db  
  
    def start(self):  
        self.db.connect()  
  
# Adheres to DIP  
class DatabaseConnector:  
    def connect(self):  
        pass  
  
class MySQLDatabase(DatabaseConnector):  
    def connect(self):  
        pass  
  
class Application:  
    def __init__(self, db):  
        self.db = db  
  
    def start(self):  
        self.db.connect()
```

## 7\. Software Development Methodologies

Software development methodologies provide structured approaches to building software applications. They help teams manage requirements, planning, development, and deployment.

## 7.1 Waterfall Model

The waterfall model is a linear, sequential approach to software development. It consists of distinct phases: requirements analysis, design, implementation, testing, and deployment. Each phase must be completed before moving on to the next.

![](https://miro.medium.com/v2/resize:fit:700/1*8c3aKC0eWmJoPrp1D2E7uQ.png)

Software Development Methodologies

## 7.2 Agile Development

Agile development is an iterative approach to software development, emphasizing flexibility, collaboration, and customer feedback. Agile methodologies prioritize delivering minor, incremental improvements to the software over rigidly following a detailed plan.

## 7.3 Scrum Framework

Scrum is an Agile framework that uses time-boxed iterations called sprints to develop software. Scrum teams have specific roles, such as Product Owner, Scrum Master, and Development Team, and use artifacts like product backlog, sprint backlog, and increment to manage work.

## 7.4 Kanban Methodology

Kanban is a workflow management method that emphasizes visualizing work, limiting work progress, and continuously improving processes. Kanban boards, with columns representing different workflow stages, help teams track and manage tasks efficiently.

## 7.5 DevOps

DevOps is a set of practices that integrate software development and IT operations. DevOps aims to increase collaboration, automate processes, and shorten the software development lifecycle.

## 8\. Version Control Systems

Version control systems help developers manage and track changes to source code, allowing for collaboration, code reviews, and the ability to revert changes when needed.

## 8.1 Git

Git is a distributed version control system widely used in software development. It enables developers to create branches, track changes, and merge code with other developers’ work.

![](https://miro.medium.com/v2/resize:fit:700/1*a9zv6YZvxEL3ZcSiz87SZQ.png)

GIT version management

The Git diagram illustrates the workflow of a Git-based version control system. Changes are made in the working directory, staged, and then committed to the local repository. The local repository can interact with a remote repository by fetching, pulling, or pushing changes.

## 8.2 Subversion

Subversion (SVN) is a centralized version control system that allows developers to track changes and collaborate on code. It uses a client-server architecture, with a central repository storing all the code and history.

![](https://miro.medium.com/v2/resize:fit:700/1*Kq0BdozjKN_-l_UnQF5l8w.png)

Subversion

The Subversion (SVN) diagram shows a simplified workflow of an SVN-based version control system. In SVN, developers have a working copy of the code and directly interact with the centralized repository. Changes are committed to the repository, and updates are fetched from the repository to the working copy.

## 8.3 Mercurial

Mercurial is a distributed version control system similar to Git. It allows developers to track changes, branch, and merge code while emphasizing ease of use and performance.

![](https://miro.medium.com/v2/resize:fit:700/1*qUsSp_gvY4h85riYGi5Mcw.png)

Mercurial

The Mercurial diagram illustrates the workflow of a Mercurial-based version control system. Similar to Git, Mercurial has a local repository and a working directory. However, unlike Git, there is no separate staging area in Mercurial. Changes are committed directly to the local repository from the working directory, and the local repository can interact with a remote repository by pulling or pushing changes.

## 9\. Testing and Quality Assurance

Testing and quality assurance ensure software applications meet requirements, function correctly, and are defect-free.

## 9.1 Unit Testing

Unit testing involves testing individual components or functions of an application in isolation. The goal is to verify that each unit performs as expected.

## 9.2 Integration Testing

Integration testing involves testing the interactions between multiple components of an application. The goal is to verify that the components work together correctly and that data flows appropriately between them.

## 9.3 System Testing

System testing involves testing the entire application, typically in an environment that simulates production. The goal is to verify that the application meets all requirements and functions correctly under different conditions.

## 9.4 Acceptance Testing

The end-users or stakeholders perform acceptance testing to validate that the application meets their needs and requirements. It is the final step before deploying the software to production.

![](https://miro.medium.com/v2/resize:fit:700/1*86jcrlbrQfosZKusJT-xxw.png)

QA testing Types

The diagram shows the testing phases typically followed in a software development lifecycle. Unit Testing focuses on testing individual components, Integration Testing tests the interaction between components, System Testing checks the entire system’s functionality, and Acceptance Testing ensures the system meets the end user’s requirements.

## 9.5 Test-Driven Development (TDD)

Test-driven development (TDD) is a software development methodology where developers write tests before writing the code. The goal is to improve code quality, ensure that requirements are met, and simplify the development process.

![](https://miro.medium.com/v2/resize:fit:700/1*VsPJa0uDT_d_dzS3rdYwgA.png)

Test Driven Development

In TDD, developers first write a test, run the test and expect it to fail, then write the code to make the test pass and refactor the code for better maintainability and optimization. The process then repeats for each new feature or functionality.

## 10\. Continuous Integration and Continuous Deployment (CI/CD)

CI/CD practices help automate the process of integrating, testing, and deploying software, enabling faster releases and higher-quality products.

## 10.1 Continuous Integration

Continuous integration (CI) is merging code changes into a shared repository frequently, ideally several times daily. Automated build and test processes help catch issues early and minimize integration problems.

## 10.2 Continuous Deployment

Continuous deployment (CD) is the practice of automatically deploying software changes to production after they pass all tests and checks. It minimizes the time between development and production release, allowing for faster feedback and improvements.

![](https://miro.medium.com/v2/resize:fit:700/1*j7XqyOnpMqlSNSGino_Kmg.png)

CI and CD

This diagram shows the flow of CI and CD pipelines. The CI pipeline involves committing code, building the application, running unit tests, and performing integration tests. The CD pipeline begins with the deployment of the application to the staging environment, followed by acceptance tests, and finally deployed to production.

The sample code for a CI/CD pipeline using Gitlab is as below

```yaml
stages:  
  - build  
  - test  
  - deploy  
  
build:  
  stage: build  
  image: python:3.9  
  script:  
    - pip install -r requirements.txt  
    - python setup.py build  
  artifacts:  
    paths:  
      - build/  
  
test:  
  stage: test  
  image: python:3.9  
  script:  
    - pip install -r requirements.txt  
    - python -m unittest discover  
  
deploy:  
  stage: deploy  
  image: python:3.9  
  only:  
    - main  
  script:  
    - echo "Deploy to production"
```

## 10.3 Popular CI/CD Tools

Numerous tools are available for implementing CI/CD pipelines, such as Jenkins, GitLab CI/CD, Travis CI, and CircleCI. These tools support various platforms and technologies, making it easier for developers to adopt CI/CD practices.

![](https://miro.medium.com/v2/resize:fit:700/1*invdWKLVtEbrM7UhkZHddQ.png)

Comparison of CI/CD Tools

