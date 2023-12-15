---
tags: 
author:
  - jacgit18
Status: refinement
Started: 
EditDate: 
Relates:
---
![[Camel Case.png]]
Be cognizant of naming convention  

like for a method that check truth value name it with the word "IS" at the beginning and a proper name like "isFunctionName"   

Think about where would this type of problem solution be applied to in real world to come up with a name or some other arbitrary name based on the scenario you come up with put things into context so you can understand and draw a image to establish better names



Pascal Casing - capitalizes each word:  
  
ThisShouldBePascalCase  
  
Camel Casing - is similiar to pascal case but the first word is not capitalized:  
  
thisShouldBeCamelCase



- Choose descriptive and unambiguous names.
- Make meaningful distinction.
- Use pronounceable names.
- Use searchable names.
- Replace magic numbers with named constants.
- Avoid encodings. Don't append prefixes or type information.

 beyond names, however. I also look at whether an object or method is doing more than one thing. If it’s an object, it probably needs to be broken into two or more objects. If it’s a method, I will always use the Extract Method refactoring on it,

Closure methods naming convention the outer function should include something like a gate in the name and the inner function should be something with the name of the door  


 
He says that beautiful code  makes the language look like it was made for the problem! So it’s   our  responsibility to make the language look simple! Language bigots everywhere, beware! It is not the language that makes programs appear simple. It is the programmer that make the language appear simple!


 
You get the drift. Indeed, the ratio of time spent reading vs. writing is well over 10:1. 
We are  constantly reading old code as part of the effort to write new code. 
Because this ratio is so high, we want the reading of code to be easy, even if it makes the writing harder. Of course there’s no way to write code without reading it, so  making it easy to read actually makes it easier to write. 

There is no escape from this logic. You cannot write code if you cannot read the surrounding code. The code you are trying to write today will be hard or easy to write depending on how hard or easy the surrounding code is to read. So if you want to go fast, if you want to get done quickly, if you want your code to be easy to write, make it easy to read.



These are sometimes a special case for encodings. For example, say you are building an ABSTRACT FACTORY for the creation of shapes. This factory will be an interface and will be implemented by a concrete class. What should you name them? IShapeFactory and ShapeFactory? I prefer to leave interfaces unadorned. The preceding I, so common in today’s legacy wads, is a distraction at best and too much information at worst. I don’t want my users knowing that I’m handing them an interface. I just want them to know that it’s a ShapeFactory. So if I must encode either the interface or the implementation, I choose the implementation. Calling it ShapeFactoryImp, or even the hideous CShapeFactory, is preferable to encoding the interface.


Class Names
Classes and objects should have noun or noun phrase names like Customer, WikiPage, Account, and AddressParser. Avoid words like Manager, Processor, Data, or Info in the name of a class. A class name should not be a verb. 


Method Names
Methods should have verb or verb phrase names like postPayment, deletePage, or save.

 
Use Solution Domain Names
Remember that the people who read your code will be programmers. So go ahead and use computer science (CS) terms, algorithm names, pattern names, math terms, and so forth. It is not wise to draw every name from the problem domain because we don’t want our coworkers to have to run back and forth to the customer asking what every name means when they already know the concept by a different name. 



Use Problem Domain Names
When there is no “programmer-eese” for what you’re doing, use the name from the problem domain. At least the programmer who maintains your code can ask a domain expert what it means. 

Separating solution and problem domain concepts is part of the job of a good programmer and designer. The code that has more to do with problem domain concepts should have names drawn from the problem domain.





In domain-driven design, when naming events or creating classes around events, it is advisable to use the past tense. For instance, you might name events like "AppointmentCreated" or "AppointmentConfirmed." Here's an example in TypeScript:

```typescript
// Event class for appointment creation
class AppointmentCreated {
    constructor(public appointmentId: string, public details: string) {}
}

// Event class for appointment confirmation
class AppointmentConfirmed {
    constructor(public appointmentId: string, public confirmationDate: Date) {}
}

// Example usage
const newAppointmentEvent = new AppointmentCreated("123", "Meeting with client");
const confirmedAppointmentEvent = new AppointmentConfirmed("123", new Date());

// Further actions with these events...
```

Using past tense in event naming helps convey that the event represents something that has already occurred in the domain.