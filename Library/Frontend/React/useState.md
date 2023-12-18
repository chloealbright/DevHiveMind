---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
```Javascript
import React, { useState } from 'react';  
function Example() {   
// Declare a new state variable, which we'll call "count"  
const [count, setCount] = useState(0); 
```

***What does calling useState do?*** It declares a “state variable”. Our variable is called count but we could call it anything else, like banana. This is a way to “preserve” some values between the function calls — useState is a new way to use the exact same capabilities that this.state provides in a class. Normally, variables “disappear” when the function exits but state variables are preserved by React. 

***What do we pass to useState as an argument?*** The only argument to the <mark style="background: #FFF3A3A6;">useState()</mark> Hook is the initial state. Unlike with classes, the state doesn’t have to be an object. We can keep a number or a string if that’s all we need. In our example, we just want a number for how many times the user clicked, so pass 0 as initial state for our variable. (If we wanted to store two different values in state, we would call <mark style="background: #FFF3A3A6;">useState()</mark> twice.) 

***What does useState return?***  It returns a pair of values: the current state and a function that updates it. This is why we write ***const [count, setCount] = useState()***. This is similar to this.state.count and this.setState in a class, except you get them in a pair. If you’re not familiar with the syntax we used, we’ll come back to it [at the bottom of this page](https://reactjs.org/docs/hooks-state.html#tip-what-do-square-brackets-mean). 

Now that we know what the useState Hook does, our example should make more sense: 

```Javascript
import React, { useState } from 'react';  
function Example() {   
// Declare a new state variable, which we'll call "count"  
const [count, setCount] = useState(0); 
```

We declare a state variable called count, and set it to 0. React will remember its current value between re-renders, and provide the most recent one to our function. If we want to update the current count, we can call setCount. 

Is you reuse setState on different buttons It wont render changes when you refresh pg because if you call a setter function(is what flags react to update) but set the state has the same value as current state the component wont reRender or be limited to one initial render which can reRender & go through the process of updating component & exit that process in later stage where we compare previous render to new render 

Which happens when you update the same value after a reRender




What is this setState in React? 

setState() setState(updater, [callback]) setState() enqueues changes to the component state and tells React that this component and its children need to be re-rendered with the updated state. This is the primary method you use to update the user interface in response to event handlers and server responses.


Controlled Components 

In HTML, form elements such as 

```Javascript
<input>, <textarea>, and <select>
``` 

typically maintain their own state and update it based on user input. In React, mutable state is typically kept in the state property of components, and only updated with setState().


```
setState(updater[, callback]) 
```

setState() enqueues changes to the component state and tells React that this component and its children need to be re-rendered with the updated state. This is the primary method you use to update the user interface in response to event handlers and server responses. 

Think of setState() as a request rather than an immediate command to update the component. For better perceived performance, React may delay it, and then update several components in a single pass. In the rare case that you need to force the DOM update to be applied synchronously, you may wrap it in [flushSync](https://reactjs.org/docs/react-dom.html#flushsync), but this may hurt performance. 

setState() does not always immediately update the component. It may batch or defer the update until later. This makes reading this.state right after calling setState() a potential pitfall. Instead, use componentDidUpdate or a setState callback (setState(updater, callback)), either of which are guaranteed to fire after the update has been applied. If you need to set the state based on the previous state, read about the updater argument below. 

setState() will always lead to a re-render unless shouldComponentUpdate() returns false. If mutable objects are being used and conditional rendering logic cannot be implemented in shouldComponentUpdate(), calling setState() only when the new state differs from the previous state will avoid unnecessary re-renders. 

The first argument is an updater function with the signature: 

```
(state, props) => stateChange 
```

state is a reference to the component state at the time the change is being applied. It should not be directly mutated. Instead, changes should be represented by building a new object based on the input from state and props. For instance, suppose we wanted to increment a value in state by props.step: 

```
this.setState((state, props) => {   return {counter: state.counter + props.step}; }); 
```

Both state and props received by the updater function are guaranteed to be up-to-date. The output of the updater is shallowly merged with state. 

The second parameter to setState() is an optional callback function that will be executed once setState is completed and the component is re-rendered. Generally we recommend using componentDidUpdate() for such logic instead. 

You may optionally pass an object as the first argument to setState() instead of a function: 

```
setState(stateChange[, callback]) 
```

This performs a shallow merge of stateChange into the new state, e.g., to adjust a shopping cart item quantity: 

```
this.setState({quantity: 2}) 
```

This form of setState() is also asynchronous, and multiple calls during the same cycle may be batched together. For example, if you attempt to increment an item quantity more than once in the same cycle, that will result in the equivalent of: 

```
Object.assign(   previousState,   {quantity: state.quantity + 1},   {quantity: state.quantity + 1},   ... ) 
```

Subsequent calls will override values from previous calls in the same cycle, so the quantity will only be incremented once. If the next state depends on the current state, we recommend using the updater function form, instead: 

```
this.setState((state) => {   return {quantity: state.quantity + 1}; });
```


