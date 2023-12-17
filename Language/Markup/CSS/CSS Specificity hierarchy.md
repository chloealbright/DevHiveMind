---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
CSS reads top to bottom meaning everything on the top will override things on the bottom  

Override order 

! Important > Inline style > ID > Classes > Tags > Order > Inherited > Browsers default 

! Important (don't use) > Inline style is above all > ID are more specific then classes so they override classes > Classes are more specific than > tags so anything changed by a class versus a tag will be overridden by the class declaration >Order(top to bottom)>Inherited(child tag basically enhance the parent tags style)>Browsers default 

If you have multiple classes for a tag whichever one is defined on the on the bottom gets picked and used  

If you have something like H1 header change color to red and header to class change clothes to Green red would be selected because it's more specific 

0                                  0        0         0 

!important(Inline)    #id    .class   element 

[https://blog.webdevsimplified.com/2020-02/css-specificity/](https://blog.webdevsimplified.com/2020-02/css-specificity/)