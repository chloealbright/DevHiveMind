---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
## what are Props? 

Props are a way to pass data from parent component to child component. Props are passed to components via HTML attributes. Props are immutable meaning can't be reassigned. 

props (short for “properties”) and state are both plain JavaScript objects. While both hold information that influences the output of render, they are different in one important way: props get passed to the component (similar to function parameters) whereas state is managed within the component (similar to variables declared within a function) 

props (short for properties) are a Component's configuration, its options if you may. They are received from above and immutable as far as the Component receiving them is concerned. 



Props gets passed to component  
As functional params 
Props are immutable 
Functional Components – props are referenced by "props" 
Class Components – this.props 


## Passing props with specific names 

	Just use object brackets and put the name of the prop 

	If you have a prop called props it's not going to be treated as the actual props unless you put outside of those brackets 

Default Props  



```javascript
class Welcome extends React.Component { 

render() {    
return <h1>Hello {this.props.name}</h1>;   
 } 
}  

Welcome.defaultProps = {   name: "world", };  


// If Welcome is called without a name it will simply render <h1> Hello world</h1>. 

// So props can come from the parent, or can be set by the component itself. 

```

props should not change 

What?! I’ve totally done that! 

You used to be able to change props with setProps and replaceProps but these have been deprecated. During a component’s life cycle props should not change (consider them immutable). 

Since props are passed in, and they cannot change, you can think of any React component that only uses props (and not state) as “pure,” that is, it will always render the same output given the same input. This makes them really easy to test - win! 



1.What is Prop-drilling? 

passing values through multiple levels. Grandparent -> parent -> child 


2. Can you modify Props? 

Props are read-only and can’t be modified. Prop values must be pure values. In other words, they cannot be mutated or changed directly. 

**Higher order** function allows you to share common functionality between components 

Hoc is a pattern where a function takes a component as an arg and returns a new component 


```javascript
Const newComponent = higherOrderComponent(originalComponent) 

// You can refer to new component to > enhanced because there is new functionality 

Const EnhancedComponent =  higherOrderComponent(originalComponent) 
```

**Render prop** pattern alt to **HOC** it refers to a technique for sharing code between react components using a prop with value of a callback function