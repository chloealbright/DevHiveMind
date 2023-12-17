---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
When running react App the code from the component gets translated into elements that will get mounted on the DOM. This process has two phase which are the render phase & commit phase  

## Initial Render Process 

React render is declarative no side effects 

During the Render phase we start at the root and traverse down the leaf nodes(components) while traversing for each of the components react invokes the create element method and converts the component to JSX into react elements & stores that render output react elements are basically JavaScript objects that describe the structure of the UI once that conversion happens for all the components in the tree all the elements are handed over to the commit phase  

Before commit phase react perform reconciliation - Diff old and new tree of react elements(aka VDOM) 

In the commit phase the elements are applied to the DOM using the react dom package  

## Re-Render Process  

As we go down the component tree we check which components have been flagged for re-render  

A component can flag itself for an update by calling the useState setter function or useReducer dispatcher function  

For each of the flagged components  react invokes the create element method  and converts the component to JSX into react elements & stores that render output 

Once the conversion is done for all the flagged components  & the components affected by the flagged components react will compare the new set of react elements with the ones that were produced from the last render  



Then a list is created with all the changes to the DOM and handed to the commit phase where changes are applied to the DOM 

Rendering isn't the same as updating the Dom  

A component can be rendered without visible changes to the DOM  

For example during rendering if the component converts into the same react element as it did in the previous  render the elements are discarded and no elements are discarded and no changes are applied to the DOM 

All updates in react are batched and applied at once which helps with performance the commit phase tends to be fast but the render can be slow  

The behavior is similar in useState where we flag a component and go to the similar process above

Note: React Strict Mode double renders in dev mode


# State Immutability

Make a copy of state from an object and reference that new object reassigning state values and setting state instead of using original state object similar with array but you making a copy of array to push into then setState if your using useState hook or useReducer hook 

Similar to render phase but with arrays & object you need to make a copy of and mutate that otherwise no re-render this is more of JavaScript then react


#  Parent and Child

Parent & child component render on pg load when parent re-render which happens when new state is different than old state 

button 2 which set value to 0 has same new and old state so wont re-render after initial render  and thus the child wont retender 

Third button has similar behavior but with value of 5 and renders parent & child then on next render just parent since react stops the re-render after it see no diff in state value  

Child goes though render phase but not commit 

Same with useReducer 

When a parent component render, React will recursively render all of its child component 

New state same as old state after initial render ? Both parent & child do not re-render 

New state same as old state after re-renders? Parent re-renders one more time but child never re-renders  

## Avoiding Unnecessary render with  Same Element Reference 

Basically passing child as a prop when nesting child component between parent component  

A component can change its state but not its props so while react traverse component tree and see parent has props it see,s that props is the child component  

React automatically see,s that parent component is dependent on state re-renders parent but not child since prop & the component has no means of directly changing the prop so children prop doesn’t change  

Make use of the react element that was previously created  

Children props has to be referencing the same element from the previous render, will skip the render phase for the child component  

In react when a parent component  renders react will recursively render all of its child components this can lead to unnecessary renders where the child component goes through the render phase but not the commit phase   

But to optimize performance you can extract expensive child component and instead pass it down as props to the parent component  

Whenever there is a re-render caused by a change in the state of the parent component React will optimize the re-render for you by knowing that the props has to be referencing the same element before and after the render 

This will prevent you having to wrap components in react memo  

When to use  Same Element Reference vs React memo  

When your parent component re-renders because of state change in the parent component  

The technique does not work if the parent component re-renders because of changes in its props 

State change ? Yes 

Props change? No  

If your component doesn’t have props use same element ref to avoid having memo every where  

When your child component is being asked to re-render due to changes in the parents state which do not affect the child components props in anyway 

If React used memo all the time it wouldn’t be good 

Because Shallow Comparison aren't free.  They're Big O(prop count) And they only buy something  if it bails out. 

All comparison where we end up re-rendering are wasted. Why would expect always comparing to be faster? Considering many components always get different props 

Ex  

Initial component renders 10ms 

Then we do a optimized render 2ms 

Then re-render over & over again adding 2ms to the 10ms render which would suck 

When you optimize the rendering of one component, react will also skip rendering that components entire subtree because its effectively stopping the default render children recursively  behavior of react