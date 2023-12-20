---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Reformat with other notes from [[Test Cases]]


### Simple Test Cases:

- Simple test cases are designed to test the most common and straightforward scenarios of a software application.
- They typically cover typical user interactions and expected behaviors.
- These test cases are often used to verify that the software functions as intended under standard conditions.
- Simple test cases may not always uncover subtle or rare issues in the software.

### Base Test Cases:

- Base test cases are the most straightforward inputs and expected outputs for a problem.
- Focus on these first to ensure your code handles the fundamental requirements correctly.


While "base test cases" and "simple test cases" may seem similar, there is a subtle difference in their focus:

1. Base Test Cases:
    
    - Base test cases refer to a set of test cases that cover the fundamental and essential functionality of a software application.
    - They encompass a broader range of scenarios, including both common and complex use cases.
    - Base test cases are designed to ensure that the core features of the software work correctly and that the application functions as expected under standard conditions.
    - These test cases may involve various combinations of inputs and interactions.
2. Simple Test Cases:
    
    - Simple test cases, on the other hand, specifically focus on testing the most straightforward and common scenarios of an application.
    - They typically cover the most basic use cases and are often used to verify that the software behaves as expected under typical or everyday conditions.
    - Simple test cases are less likely to explore complex or edge scenarios and instead aim to validate that the software meets basic requirements for common user interactions.

In summary, the key difference between the two lies in their scope. Base test cases encompass a wider range of scenarios, including both common and more complex situations, while simple test cases concentrate on the most basic and everyday interactions with the software. The terminology used may vary depending on the testing process and the specific testing objectives of an organization.




### Edge Case Testing

Edge cases are errors that occur very infrequently. These errors can be as minor as a visual inconsistency or as serious as a total software crash. In order to root out these edge cases before they become an issue, regression testing can be employed to find the source of the problem.


### Corner Case Testing

While edge cases occur when only one operating parameter is at an extreme, corner cases occur when multiple parameters are at an extreme. In corner case testing, multiple parameters are tested to identify where issues could arise.


### Iron Corner Case Testing
Iron corner case testing is also known as boundary value analysis, and it seeks to test cases just outside and just inside edge cases.



### User Scenario Case Testing

User scenario case testing asks the tester to step into the shoes of the end user. It utilizes actual test cases to ensure that all possible scenarios are addressed. This type of testing focuses on end-to-end scenarios to handle complex problems.

### Decision/ Truth Table Testing

Decision table testing is a form testing that assesses different combinations of inputs and places them in a table. The corresponding outputs are categorized into “true” or “false,” and these are used to determine where there is a problem that needs resolving. 


### Error Guessing

Error guessing is the process by which a developer or tester determines where there may be errors in the software and writes corresponding test cases to address these potential errors so that they may be corrected.




## Ranorex: Black Box Security Testing Tools

Ranorex Studio is a GUI test automation framework provided by Ranorex GmbH, a software development company. The framework is used for the testing of desktop, web-based and mobile applications.

It provides an array of tools for different types of black box testing as a comprehensive solution, so regardless of what type of testing you need to employ, we can help you implement it.


### Black Box Test Automation

With Ranorex Studio, you can automate your black box testing by selecting from a range of various test types. These will help you address a range of issues that may arise..

### UI Object Recognition

Ranorex Studio also tracks and analyzes all elements of your user interface and inputs them into a repository for your convenience. This allows you to maintain and manage all identified objects with ease even when your UI changes.


### Data-Driven Testing

You can additionally automate data-driven testing by using corner, edge, or boundary cases by setting up variables, linking them to external data sets, and looping through the data. Ranorex Studio even allows you to determine whether to stop a test as a result of a failure or to continue with the next test.


### Keyword-Driven Testing

Keyword-driven testing relies on action words that represent the user’s behavior. These include words like “Log On” or “Close Window.” It separately documents the steps that the user actually takes to perform the action. Ranorex Studio provides tools to make automated keyword-driven testing accessible and repeatable.


### Cross-Device and Cross-Browser Testing

Ranorex Studio allows you to automate tests on one operating system and then execute them locally or remotely on another. This type of testing ensures that all users, regardless of their system, have a consistent experience.


### Customizable Reporting

You can monitor the results of your testing with Ranorex Studio’s customizable reports. These reports can include pie charts, screenshots, and detailed error logs. Additionally, you can jump directly into testing from the report.


### Black Box Penetration Testing

Black box penetration testing demonstrates how an attacker would try to perform an attack on a software without any knowledge about the internal code. This test can also be automated to ensure potential weaknesses are addressed before a breach occurs.


## Benefits of Automated Black Box Testing

#### Simple implementation

To perform the tests, users don’t need to have technical knowledge/skills because the tests do not look at the code of a particular software.

#### Convenient execution

Execution can be outsourced to external testers or automated because you are solely looking at the functionality of the software.

#### Accuracy

The risk of false positives is extremely low, and you can be certain that your testing will address all possible issues.

#### Reduced complexity

Tests can be quite simple since they seek to model common user behavior. As such, they don’t require learning the system details.