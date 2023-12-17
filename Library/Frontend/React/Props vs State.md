---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
### Before separating props and state, let's also identify where they overlap. 
```
Both props and state are plain JS objects 

Both props and state changes trigger a render update 

Both props and state are deterministic. If your Component generates different outputs for the same combination of props and state then you're doing something wrong. 

```

### Does this go inside props or state? 

tl;dr: If a Component needs to alter one of its attributes at some point in time, that attribute should be part of its state, otherwise it should just be a prop for that Component. 

#### Props 

props (short for properties) are a Component's configuration, its options if you may. They are received from above and immutable as far as the Component receiving them is concerned. 

A Component cannot change its props, but it is responsible for putting together the props of its child Components. 

Changing Props  

can get initial value & be changed from parent component  

Can set default values inside Component* but cannot change inside component  

You can also set initial value for child Component props and change props in child component  

props contains information set by the parent component (although defaults can be set) and should not be changed. 

... props are a way of passing data from parent to child. 

#### State 

The state starts with a default value when a Component mounts and then suffers from mutations in time (mostly generated from user events). It's a [serializable](onenote:Other.one#Serialization%20vs%20Parsing&section-id={CD0BD125-5364-4419-88DB-0D13D4F31B16}&page-id={FF98ADBC-AB2F-457E-A743-195AF759DF63}&end&base-path=https://mailcitytechcuny-my.sharepoint.com/personal/joshua_carpentier_mail_citytech_cuny_edu/Documents/Notebooks/Dev)* representation of one point in time—a snapshot. 

State, in short, is like a variable scoped to a function, the state object is where you store property values that belong to the component, When the state object changes, the component re-renders. 

A Component manages its own state internally, but—besides setting an initial state—has no business fiddling with the state of its children. You could say the state is private. 

State is managed within the component 

Variables declared in the function body 

Can be changed so is mutable 

Functional Components – useState Hook 

Class Components – this.state 



#### Changing State  

can get initial value & cannot be changed from parent component  

Can set default values inside Component* & can change inside component  

You can also set initial value for child Component state and cannot change state in child component  

state contains “private” information for the component to initialize, change, and use on its own. 

 ... State is reserved only for interactivity, that is, data that changes over time.


## Keeping track of data between Renderings

When a component needs to keep track of information between renderings the component itself can create, update, and use state. The initial data can be hard coded ), but it can also come from props. 

You can see we have access to prevState within the callback, this will contain the previous state, even if the state has already been updated somewhere else. But React goes one step better, setState updates the state object and re-renders the component automagically. 

setState <mark style="background: #FF5582A6;">warning one! </mark>

It is tempting to write this.state.count = this.state.count + 1. Do not do this! React cannot listen to the state getting updated in this way, so your component will not re-render. Always use setState. 

setState <mark style="background: #FF5582A6;">warning two! </mark>

It might also be tempting to write something like this: 


<mark style="background: #FF5582A6;">// DO NOT USE </mark>
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