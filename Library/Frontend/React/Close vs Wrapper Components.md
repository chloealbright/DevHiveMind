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










#### State 


State, in short, is like a variable scoped to a function, the state object is where you store property values that belong to the component, When the state object changes, the component re-renders. 



State is managed within the component 

Variables declared in the function body 

Can be changed so is mutable 

Functional Components – useState Hook 

Class Components – this.state 





In essence, state is comparable to a variable scoped to a function; the state object stores property values specific to the component. When the state changes, the component re-renders.

Internally managed, a component handles its own state, maintaining a private nature except for setting the initial state. It is a mutable entity confined within the component, and its management differs between functional components using the `useState` hook and class components using `this.state`.


#### Changing State  

can get initial value & cannot be changed from parent component  

Can set default values inside Component* & can change inside component  

You can also set initial value for child Component state and cannot change state in child component  

state contains “private” information for the component to initialize, change, and use on its own. 

 ... State is reserved only for interactivity, that is, data that changes over time.


## Keeping track of data between Renderings

When a component needs to keep track of information between renderings the component itself can create, update, and use state. The initial data can be hard coded ), but it can also come from props. 

You can see we have access to prevState within the callback, this will contain the previous state, even if the state has already been updated somewhere else. But React goes one step better, setState updates the state object and re-renders the component automagically. 

setState  warning one! 

It is tempting to write this.state.count = this.state.count + 1. Do not do this! React cannot listen to the state getting updated in this way, so your component will not re-render. Always use setState. 

setState warning two! 

It might also be tempting to write something like this: 


// DO NOT USE 
```javascript
this.setState({   
count: this.state.count + 1

});  
```
Although this might look reasonable, doesn’t throw errors, and you might find examples that use this syntax online, it is wrong. This does not take into account the asynchronous nature that setState can use and might cause errors with out of sync state data. 

Program as usual  and finally, render 
```javascript
render() {   
return (
<button onClick={() => this.updateCount()} >             

Clicked {this.state.count} times 

</button>
); 

}  
```

**onClick={() => this.updateCount()}** means that when the button is clicked the updateCount method will be called. We need to use [ES6’s arrow function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) so updateCount will have access to this instance’s state. 

The text rendered in the button is Clicked {this.state.count} times, which will use whatever this.state.count is at the time of rendering.