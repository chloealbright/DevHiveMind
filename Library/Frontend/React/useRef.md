---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
const refContainer = useRef(initialValue); 

useRef returns a mutable ref object whose .current property is initialized to the passed argument (initialValue). The returned object will persist for the full lifetime of the component. 

A common use case is to access a child imperatively: 

```Javascript
functionTextInputWithFocusButton(){
	constinputEl =useRef(null);
		onstonButtonClick=()=>{
			 // `current` points to the mounted text input 
			 elementinputEl.current.focus();};
			 return(
					 <>       
					  <inputref={inputEl} type="text"/>       
					  <buttononClick={onButtonClick}>Focus the input </button>     
					  </>
					  ); 
```

Essentially, useRef is like a “box” that can hold a mutable value in its .current property. 

You might be familiar with refs primarily as a way to [access the DOM](https://reactjs.org/docs/refs-and-the-dom.html). If you pass a ref object to React with <div ref={myRef} />, React will set its .current property to the corresponding DOM node whenever that node changes. 

However, useRef() is useful for more than the ref attribute. It’s [handy for keeping any mutable value around](https://reactjs.org/docs/hooks-faq.html#is-there-something-like-instance-variables) similar to how you’d use instance fields in classes. 

This works because useRef() creates a plain JavaScript object. The only difference between useRef() and creating a {current: ...} object yourself is that useRef will give you the same ref object on every render. 

Keep in mind that useRef doesn’t notify you when its content changes. Mutating the .current property doesn’t cause a re-render. If you want to run some code when React attaches or detaches a ref to a DOM node, you may want to use a [callback ref](https://reactjs.org/docs/hooks-faq.html#how-can-i-measure-a-dom-node) instead.




useRef can store the reference of a DOM node using ref attribute it can also be used to store any mutable value and the values will persist through re-renders while also not causing additional renders when it's values changes  

useRef hook can be used to create a generic container which can hold a mutable value similar to instance properties on a class component and doesn’t cause re-renders when the data it stores changes & at the same time it remembers the stored data even after other state variables trigger a re-render of the component





Find a common owner component (a single component above all the components that need the state in the hierarchy). 

Either the common owner or another component higher up in the hierarchy should own the state. 

If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component. 

Then Data flow 

Ref lets you access DOM nodes directly like a login page when you go to one you have react focus on the username field to just start typing instead of clicking on text box  typically stored and created in constructor then you add ref property to a tag and assign it to ref from constructor   

Then reference the ref on componentDidMount to focus on tag 

You also use ref to access input value on eventHandler 

Doesn’t work with functional components   

 Forwarding Refs passing ref from component to its child

#EDIT