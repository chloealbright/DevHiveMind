---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Use context  is used when you have nested components and you need to pass down props to a component deep inside another component which can be shitty in terms of performance  


This known as prop drilling 
 

Use context provides a way to pass data through the component tree without having to pass props down manually at entry level 

 
Use context is related to context Api 


useContext is Another way to trigger re-renders  


After initial render react look for changes in state & React context provider if it has been given a new value when state is altered the context has a new value and react will make a note to re-render all the components that consume the context value which include child components  

 
Then the render phase go through the same stages of behavior of render & commit  


Memo cam help with optimization  


Also Same Element Reference 


Context provides a way to pass data through component tree without having to pass down props manually at every level 
 

# When to Use Context 

Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language. For example, in the code below we manually thread through a “theme” prop to style the Button component. 



```javascript
const ThemeContext = createContext('light') 

function App() { 

return ( 

    <div className="App"> 

       <ThemeContext.Provider value={'red'}> 

         <Content/> 

       </ThemeContext.Provider> 

    </div> 

  ); 

} 

function Content(){ 

   const theme = useContext(ThemeContext) 

   return( 

       <div className={theme}> 

         <h2>Hello, World</h2> 

       </div> 

     ); 

} 

export default App;
```

 