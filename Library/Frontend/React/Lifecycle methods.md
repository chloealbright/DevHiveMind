---
tags: 
author:
  - jacgit18
Comments: 
Status: 
Started: 
EditDate: 
Relates:
---
Mounting life cycle methods are called when an instance of a component is being created and inserted into DOM 

The Life Cycle method are executed in a specific order the first being the constructor which is called whenever a component is created and is used to initialize state and binding event handlers to class instance or state  

You need to call super method with prop param which calls base class constructor which allows access the props overall  

Never do http req in constructor 

The next method is a static method called  getDerivedStateFromProps(props, state)  with param of props and state  

This method is rarely used but is used when the state of the component depend on changes in the prop over time an example would be you have a component that depends on the props being passed to the component this method can be used to set the state  

This keyword is supported by this method  

Third method is render which is a pure function that is required in classes and reads props and state and return jsx/ components 

You should not change state or interact with DOM in this method or perform request 

Forth is componentDidMount which is called only once in the whole lifecycle of a given component  and is invoke immediately after a component and all its children are rendered  to DOM 

You can cause side effect in it make network request or interact with DOM