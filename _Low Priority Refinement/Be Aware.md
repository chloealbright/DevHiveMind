---
tags: 
author:
  - jacgit18
Status: Perpetual
Started: 
EditDate: 
Relates:
---
![[Learning Approach.png]]

## Practice and Repetition
You can expand short term memory with practice and repetition  
  
Specifically purposeful practice focusing on one aspect of a sub skill  
  
  
Try differently not harder  
  
Try alternating approaches


When you learn something new you tend to get excited and want to utilize that thing  

But that can sometimes be a mistake because sometimes you fail to pay attention to the key details especially on a technical interview

Avoid reinventing the wheels search for solutions that exists first

Make a lot of different connections at all different levels and scopes and different areas  

Keep logs of errors and how you solved using git branches to track

Think Input output dependencies

Kiss(Keep it simple stupid) principal

## debugging

“The art of debugging is figuring out what you really told your program to do rather than what you thought you told it to do.”” — Andrew Singer 

Reassess: Take a step back. Look at the problem from another perspective. Is there anything that can be abstracted to a more general approach? 

“Sometimes we get so lost in the details of a problem that we overlook general principles that would solve the problem at a more general level. […]

type debugger; // in code and browser console


## Tip <mark style="background: #FFF3A3A6;">find were to put </mark>

don't do docker build unless you recreate the package file  

Add npm package one by one and commit that change to avoid breaking stuff 

use keywords when searching for problems  coding on Google

rubber ducky updating the firmware of a flash drive to register as a keyboard and make it register keystrokes

## Tips to Understand the code base 

Refactoring code can make it easier to understand a codebase by creating a method or something that describes what's going on 

Creating unit tests or integration test




## Use abstraction to your advantage 

it is process of hiding implementation details and only showing the functionality to the user. Abstraction focus on what the object does instead of how it does. It is achieved by using Abstract class and Interface. abstract methods (methods without body, cannot be static and final), interface must implemented and abstract classes must be extended by regular classes in order to achieve abstraction (because abstract methods can only be exist in abstract class and interface). A class can implement multiple interfaces,  but it can extend only single abstract class. 

I love asking complicated interview problems. If a problem involves several different components, you as the interviewer get such great insights into how a candidate manages their thinking when there is so much to deal with all at once. 

The key to successfully solving these problems is to use abstraction. At its core, this means breaking out your code into smaller functions with more specific purposes. 

Consider a simple example. Let’s say that we wanted to print out a linked list in reverse order. After working through this problem we realize that there is an O(n) time and space solution to the problem using a stack (push each element onto the stack as we iterate over the list and then pop each item and print), but we can solve the problem in O(n) time and O(1) space by reversing the linked list. 

Now it would be easy enough to reverse the linked list in our code, but what if we had a function to do that for us? That would make our lives way easier. We just call the function on the linked list, iterate over everything in the list and print it, and then reverse the list again so that we return our input to the original state. 

With that logic, we can now isolate the process of reversing a linked list and think about how to do that effectively. While this problem is a very simple example, it is easy to see how this reduces the amount of complexity we have to think about at any given time. 

With more complicated problems, I recommend you ask yourself the question “What function, if it existed, would make my life easier right now?” If there is a clear function or functions, write your code assuming those functions already exist. Then you can go back afterwards and implement those functions, now that the rest of your code already works. 

## This has several advantages: 

If you run out of time, you still have a basically working code. Abstraction allows you to focus on the overall structure without having to get bogged down in the minutiae. If you have extra time, you can worry about the minutiae, but even if you don’t, it’s clear to your interviewer that you know what’s up. 

Clarity of thinking and code. They say that a clear desk means a clear mind and the same is true with code. The better you organize your code and break it up into manageable components, the easier it is to think about. 

I find that the more involved the problem is, the more valuable it can be to break things up into manageable components.





move somewhere 

Try not to add too much complexity in certain aspects of a project if affordable because you'll also have to maintain that code and data 

Avoiding using too many global variables can be taxing on memory 

checkout git hub issues when building off code and you run into a problem



First step to do a dev position 

Ask and identify auth and authentication also look into data model & test 

Identify input & outputs in codebase  constantly to reoriented self within codebase and logic your developing



think about time and cost when it comes to advanced functionality keep things basic some times and move on and come back  

90/90 rule first 90 is getting features done then second 90 is getting things polished like error handling and screen size fixing etc … 

Spaghetti code a whole bunch of functions and variables everywhere decentralized basically functions and variables all over the place not very organized well

