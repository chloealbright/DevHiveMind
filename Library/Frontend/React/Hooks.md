A feature that allows you to use react features without creating class but cannot be used within classes it was created for more functional code 

Cons of classes  

you need to have a understanding of this keyword, you have also remember to bind event handlers and classes in general don’t minify very well and makes hot reloading very unreliable      

No particular way to reuse stateful component logic 

Hoc and render props patterns address some of these problems  



Hooks makes it easier to reuse stateful logic without changing component hierarchy  

Hooks also is good for complex components that involve data fetching and event subscription and helps organize related code in one place defining nested function inside a parent function   



Data fetching happens in componentDidMount  & componentDidUpdate 

Event listeners are used in componentDidMount  & componentWillUnmount  

Hooks let you split one component  into smaller functions based on what features are related   

Hooks should only be call at the top level or parent component, hooks shouldn’t be called in a loop, condition or nested function and should be only called from a react function not regular JavaScript function 


a state vairiable can be a string, boolean, number, & object, array   



UseState allows you to add state to functional component and in classes state is a object with use state hook state doesn’t need to be a object 

Takes in 2 params current state and state setter which is used as function taking in a new value and us in a anonymous callback function to update state 

New state value depends on previous state value  

When dealing with array or object always spread your state variable and then call the setter function