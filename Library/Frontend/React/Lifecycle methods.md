---
tags:
  - web
  - frontend
  - library
author:
  - jacgit18
Comments: This documentation discusses
Status: Done
Started: 
EditDate: 2024-02-06
Relates:
---
The mounting lifecycle methods in React are invoked when a component instance is being created and inserted into the DOM. The process begins with the constructor, where state is initialized and event handlers are bound to the class instance or state. It's essential to call the `super(props)` method with the prop parameter to invoke the base class constructor, providing access to the overall props.

Avoid making HTTP requests in the constructor.

The `getDerivedStateFromProps` static method is used when the component's state depends on changes in props over time. It can be used to update the state based on props.

In the `render` method, a pure function, read props and state, and return JSX/components. Avoid changing state, interacting with the DOM, or making requests here.

The `componentDidMount` method is invoked once, right after the component and its children are rendered to the DOM. It's suitable for causing side effects, such as network requests or DOM interactions.