---
tags:
  - web
  - frontend
  - library
author:
  - jacgit18
Comments: 
Status: 
Started: 
EditDate: 
Relates:
---
The component's life cycle involves several key methods. The constructor initializes state and binds event handlers. Remember to call `super(props)` to access the props.

Avoid making HTTP requests in the constructor.

The `getDerivedStateFromProps` static method is used when the component's state depends on changes in props over time. It can be used to update the state based on props.

In the `render` method, a pure function, read props and state, and return JSX/components. Avoid changing state, interacting with the DOM, or making requests here.

The `componentDidMount` method is invoked once, right after the component and its children are rendered to the DOM. It's suitable for causing side effects, such as network requests or DOM interactions.