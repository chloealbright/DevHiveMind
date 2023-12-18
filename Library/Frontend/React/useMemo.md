---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Used for optimization  

useMemo is similar to use callBack and cache something like a function and takes in a array or dependencies as it second param  

The difference between the two hooks is that useCallback caches the provided function instance itself whereas useMemo invokes the provided function and caches its result  so if you need to cache a function use useCallback & if you need to cache the result of an invoked function use useMemo  

React doesn’t care if props change when rendering but react Memo can make it where we can make things render base on props 

React memo performs a shallow comparison of the previous and new props & re-render the child component only if the props have changed 

Giving you a performance boost in some scenario  

## React memo no no's 

	there is no reason to wrap your child component with react memo if the child component itself has children elements  

	Incorrect memo with Impure Component impure meaning props & state staying the same but component chagrining like maybe the a component with time in it   or random func that is being used in conjunction with some calculation 

	If a component has object or functions and your wrapping one of the its child components with react memo not good todo but useCallback can fix this issue  



React.memo is a higher order component. 

If your component renders the same result given the same props, you can wrap it in a call to React.memo for a performance boost in some cases by memoizing the result. This means that React will skip rendering the component, and reuse the last rendered result. 

React.memo only checks for prop changes. If your function component wrapped in React.memo has a useState, useReducer or useContext Hook in its implementation, it will still rerender when state or context change. 

By default it will only shallowly compare complex objects in the props object. If you want control over the comparison, you can also provide a custom comparison function as the second argument.