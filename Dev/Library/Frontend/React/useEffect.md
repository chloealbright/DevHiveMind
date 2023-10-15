Use effect allows you to use side effects in functional components  

It is a close replacement for these life cycle methods <mark style="background: #FFF3A3A6;">componentDidMount</mark>, <mark style="background: #FFF3A3A6;">componentDidUpdate</mark>, & <mark style="background: #FFF3A3A6;">componentWillUnmount</mark>  

***Ex***: updating title on a interval  

You use ***componentDidMount*** setting the title and setting interval then set the title again on ***componentDidUpdate*** and clear interval on ***componentWillUnmount***  

Use effect takes in a param that runs after every render of a component




#### I have some side effects to apply in my react component and want to know how to organize them: 

as a single useEffect 

or several useEffects 

Which is better in terms of performance and architecture? 



The pattern that you need to follow depends on your use case. 

First: You might have a situation where you need to add event listener during the initial mount and clean them up at unmount and another case where a particular listener needs to be cleaned up and re-added on a prop change. 

In such a case, using two different useEffect is better to keep the relevant logic together as well as having performance benefits 

```
useEffect(() =>{    // adding event listeners on mount herereturn() =>{        // cleaning up the listeners here} }, []);  

useEffect(() =>{    // adding listeners everytime props.x changesreturn() =>{        // removing the listener when props.x changes} }, [props.x])  
```

Second: You need to trigger an API call or some other side-effect when any of the state or props change from a defined set. In such a case a single useEffect with the relevant dependencies to monitor would be better 

```
useEffect(() =>{     // side effect here on change of any of props.x or stateY}, [props.x, stateY])  
```

Third: You need separate side-effect for different sets of changes. In such a case, separate out relevant side-effects into different useEffects 

```
useEffect(() =>{    // some side-effect on change of props.x}, [props.x])  

useEffect(() =>{    // another side-effect on change of stateX or stateY }, [stateX, stateY]) 
```




## LOOK AT a Liitle more in deph in comparison to other notes
React will apply every effect used by the component, in the order they were specified. 

what about a middle ground between Second and Third example above?: you have logic that runs when a subset of state/props change, but each has separate logic that needs to run in addition to some common code that needs to run? You wouldn't use [] (because it's still only a subset of state/props you're awaiting changes for) but you'd also like to reuse code. Do you use separate useEffects and put the shared code in a function they each separately call?  

As the answer below suggests, React team suggests separating hooks by concern, so you would split it into multiple useEffect calls.



You’ve likely performed data fetching, subscriptions, or manually changing the DOM from React components before. We call these operations “side effects” (or “effects” for short) because they can affect other components and can’t be done during rendering. 

The Effect Hook, useEffect, adds the ability to perform side effects from a function component. It serves the same purpose as componentDidMount, componentDidUpdate, and componentWillUnmount in React classes, but unified into a single API. (We’ll show examples comparing useEffect to these methods in [Using the Effect Hook](https://reactjs.org/docs/hooks-effect.html).) 

For example, this component sets the document title after React updates the DOM: 

```javascript
import React, { useState, useEffect } from 'react'; 

function Example() {   
const [count, setCount] = useState(0);    
// Similar to componentDidMount and componentDidUpdate: 
useEffect(() => {    
// Update the document title using the browser API    
document.title = `You clicked ${count} times`;  });   
return (     
<div>       
<p>You clicked {count} times</p>       
<button onClick={() => setCount(count + 1)}> Click me </button>     

</div>   ); 
} 
```

When you call useEffect, you’re telling React to run your “effect” function after flushing changes to the DOM. Effects are declared inside the component so they have access to its props and state. By default, React runs the effects after every render — including the first render. (We’ll talk more about how this compares to class lifecycles in [Using the Effect Hook](https://reactjs.org/docs/hooks-effect.html).) 

Effects may also optionally specify how to “clean up” after them by returning a function. For example, this component uses an effect to subscribe to a friend’s online status, and cleans up by unsubscribing from it: 

```javascript
import React, { useState, useEffect } from 'react';  function FriendStatus(props) {   const [isOnline, setIsOnline] = useState(null);    function handleStatusChange(status) {     setIsOnline(status.isOnline);   }    

useEffect(() => {    ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);    return () => {      ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);    };  });   if (isOnline === null) {     return 'Loading...';   }   return isOnline ? 'Online' : 'Offline'; } 
```

In this example, React would unsubscribe from our ChatAPI when the component unmounts, as well as before re-running the effect due to a subsequent render. (If you want, there’s a way to [tell React to skip re-subscribing](https://reactjs.org/docs/hooks-effect.html#tip-optimizing-performance-by-skipping-effects) if the props.friend.id we passed to ChatAPI didn’t change.) 

Just like with useState, you can use more than a single effect in a component: 

```javascript
function FriendStatusWithCounter(props) {   

const [count, setCount] = useState(0);   
useEffect(() => {   
document.title = `You clicked ${count} times`;   
});    

const [isOnline, setIsOnline] = useState(null);   
useEffect(() => {    
ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);     

return () => {      
ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);   

			};   
				
	});    

function handleStatusChange(status) {     
setIsOnline(status.isOnline);   
}   
```

Hooks let you organize side effects in a component by what pieces are related (such as adding and removing a subscription), rather than forcing a split based on lifecycle methods.