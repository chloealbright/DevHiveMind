---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
There are 5 methods 3 are rarely used but are called in this order of execution  


```javascript
getDerivedStateFromProps(props, state)  > 
shouldComponentUpdate(nextProp, nextState)  > 
render() > 
getSnapshotBeforeUpdate(prevProp, prevState) > 
componentDidUpdate(prevProp, prevState, snapshot)  
```

shouldComponentUpdate  this method receives updated prop and state  and dictates if component should re-render or not by default all components  will re-render depending on their props and change in state this method can change that default behavior by returning false you can compare the current state and prop with the next state and prop values and return true or false to let react know if it should re-render  

This method is good for performance optimization  avoid net req or state manipulation  

Third is render() 

Fourth is getSnapshotBeforeUpdate(prevProp, prevState) takes in previous props and state and is called before changes from the virtual DOM are displayed in the DOM but is rarely used and is used to get info from the DOM and it returns null or a return value. This value is passed as the third param to next method which is componentDidUpdate 

The last is componentDidUpdate(prevProp, prevState, snapshot) which is called after the render is  finished in the re-render cycles  

so an example is class goes through the mothing and calls getDerive, shouldUpdate, render then render another component from another class that calls its own calls getDerive, shouldUpdate, render then calls snapshot then goes back to the last class where it initial render that class component and calls its own snapshot then goes back to the second class component to finish the componentDidUpdate which is waited for the snapshot of the initial class to finish then the  initial componentDidUpdate  update is called 

You can do side effects here like network req but you should compare prevProps or state to the new props and state to determine if you want to make a req  

Methods triggered by props and state are the update methods so shouldComponentUpdate ,  getSnapshotBeforeUpdate, and componentDidUpdate