---
tags:
  - web
  - frontend
  - "#CodebaseDecision"
  - library
author:
  - jacgit18
Comments: This documentation discusses when to use close components vs wrapper components.
Status: Done
Started: 
EditDate: 2024-02-06
Relates: "[[React High Level]]"
---
In React, the decision to use close components or wrapper components depends on the specific requirements and design of your application. Let's understand each concept:  
  
1. Close Components:  
	- Close components, also known as "presentational" or "dumb" components, focus solely on rendering the UI and receive data through props. They don't manage state or have any side effects. Close components are reusable and often represent a specific UI element or small component of your application.  
  
Use close components when:  
- You have a small, self-contained UI element that doesn't require state management or complex logic.  
- You need to encapsulate a specific part of your UI and make it reusable across multiple components.  
- You want to keep your codebase modular, allowing for easier maintenance and testing.  
  
Example close component:  
```jsx  
function Button(props) {  
return <button onClick={props.onClick}>{props.label}</button>;  
}  
```  
  
2. Wrapper Components:  
Wrapper components, also known as "container" or "smart" components, are responsible for managing state, handling data fetching, and orchestrating the behavior of one or more close components. They typically provide data and behavior through props to their child components.  
  
Use wrapper components when:  
- You need to manage state or handle data fetching for a specific part of your application.  
- You want to encapsulate complex logic and provide a clean interface to the close components.  
- You need to connect to external data sources or APIs and pass the relevant data to the close components.  
  
Example wrapper component:  
```jsx  
class TodoList extends React.Component {  
constructor(props) {  
super(props);  
this.state = {  
todos: [],  
};  
}  
  
componentDidMount() {  
// Fetch todos from API and update state  
// ...  
}  
  
render() {  
return <TodoItems todos={this.state.todos} />;  
}  
}  
```  
  
In summary, close components focus on UI rendering and reusability, while wrapper components handle state management and provide data and behavior to their child components. Striking a balance between these two types of components helps to maintain a modular and manageable codebase.




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