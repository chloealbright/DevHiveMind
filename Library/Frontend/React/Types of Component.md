---
tags:
  - web
  - frontend
  - library
  - react
author:
  - jacgit18
Comments: This documentation discusses
Status: 
Started: 
EditDate: 
Relates:
---
The main responsibility of a Component is to translate raw data into rich HTML. With that in mind, the props and the state together constitute the raw data that the HTML output derives from. 

You could say props + state is the input data for the render() function of a Component, so we need to zoom in and see what each data type represents and where does it come from Because we also use [Cosmos](https://reactcosmos.org/)  library where props can contain an initial state, getting this straight is crucial. 

-   Stateless functional Component  
    
    -   General JavaScript function that might take in a prop param and return a  
        
    -   Html Tag/JSX with some prop value 
        
    -   Simple  
        
    -   Should use as much as possible 
        
    -   This keyword not required makes it more simple 
        
    -   No state object 
        
    -   Mainly responsible for UI  
        
    -   Stateless or stateful with Hooks/ Dumb / Presentational 
        

Stateless Component — Only props, no state. There's not much going on besides the render() function and all their logic revolves around the props they receive. This makes them very easy to follow (and test for that matter). We sometimes call these dumb-as-f*ck Components (which turns out to be the only way to misuse the F-word in the English language). 

-   Stateful Class Component  
    
    -   Extend to component class and contains render method that returns Html tag/JSX 
        
    -   More Features 
        
    -   Maintains their own private data / state 
        
    -   Good for complex UI Logic  
        
    -   Provides lifecycle hooks 
        
    -   Stateful / Smart / Container 
        

Stateful Component — Both props and state. We also call these state managers. They are in charge of client-server communication (XHR, web sockets, etc.), processing data and responding to user events. These sort of logistics should be encapsulated in a moderate number of Stateful Components, while all visualization and formatting logic should move downstream into as many Stateless Components as possible. 

## Planning 

Remember: React is all about one-way data flow down the component hierarchy. It may not be immediately clear which component should own what state. This is often the most challenging part for newcomers to understand, so follow these steps to figure it out: 

### For each piece of state in your application: 

	Identify every component that renders something based on that state. 

	Identify components and sub components drawing out tree 

	Identify Where Your State Should Live which component mutates, or owns, this state. 

Use class component for robust dynamic components 

Use functional components more for smaller reusable components 


Create with arrow functions if you're not exporting else regular to export function one line 

Can export arrow on one line 


```javascript
export const test= () => { 

// just no default export 

} 
```

## Parent tags use cases 

Use div when you are using some type of CSS position display like flexbox or grid 

Else use react fragments over Divs if you are still using style but not doing anything with position of a component or use empty tags <> </> If you need to use keys but empty tags are the shorthand for fragments 

```javascript
<React.Fragment key={index}>  

</React.Fragment > 
```
## React.PureComponent 

React.PureComponent is similar to React.Component. The difference between them is that React.Component doesn’t implement shouldComponentUpdate(), but React.PureComponent implements it with a shallow prop and state comparison. 

If your React component’s render() function renders the same result given the same props and state, you can use React.PureComponent for a performance boost in some cases. 

You can potentially create some type of conditional rendering to implement in main render or current class that extends to pureComponent otherwise maybe just put a shouldComponentUpdate in the first place   

A good idea look at notes on deep and shallow copy  

Basically comparing ref or memory address   

So I there is a difference between the shallow copy of prevState & currentState or prevProp and currentProp re-render but once we re-render that component wont render again 

PureComponent only works with classes so If you to mimic this behavior with functions you can use   memo Components which is a higher order component


## State in Functional components with hook 

```javascript
const Person = () => { 

  const [name, setName] = useState('Andrew') 
  return ( 
     <div> 
       <h1>{name}</h1> 
     </div> 
   ); 
} 

export default Person;
```

## State in class component 
```javascript
class Person extends React.Component { 

  constructor(props) { 
    super(props); 
    this.state = {name: "Andrew"}; 
  } 

  render() { 
    return ( 
      <div> 
        <h1>{this.state.name}</h1> 
 // if no state object 
        <h1>{this.prop.name}</h1> 
      </div> 
    ); 
  } 
}

```

## Never modify state directly ex:  

The only place where you can assign this.state is the constructor.


```javascript
class Counter extends Component { 

   constructor(props){ 

     super(props) 

     this.state = { 

      count: 0 

     } 

   } 

   changeCount(){ 

     //this.state.count = this.state.count +1; // the only place to assign state is the constructor otherwise state wont render 

     // a better way is using setState() which takes in updated state and callback 

    // this.setState({ 

    //   count: this.state.count + 1 

    // }, 

    // () =>{console.log(`Callback Val ${this.state.count}` )}) // when at 1 this.state will console log 0  

    // because calls to setstate are aysnc  

    // so you will always be 1 behind or on the previous state in term of state initial value 

    // console.log(this.state.count) // this called before state is sent so in order to get a accurate state 

    // you need to pass a callback in to setState if you need to do things after setting state do it in callback 

    // proper way to set state use previous state 

    this.setState( (prevState, props) => ({ 

      count: prevState.count + 1 

    }), ()=>{ console.log(`Callback Val ${this.state.count}`) }) 

    console.log(this.state.count) 

   } 

   multiStateChange(){ 

    // wont work the way you expect because the way react state works 

    // react will group multiple setStates into one for optimization  

    // but since that is the case the updated value isnt carried over 

    // so when pressed all will be zero and state total will be 1 then all will be 1 then state total is 2 

    this.changeCount() 

    this.changeCount() 

    this.changeCount() 

    // similar result with diff methods 

    // similar result with prev state methods increment count to 7 intial then 14 then 21 

    this.changeCount2() 

    this.changeCount3() 

    this.changeCount4() 

    this.changeCount5() 

   } 

  render() { 

    return ( 

      <> 

        <>Count - {this.state.count}</> 

        <button onClick = {() =>this.changeCount() }> Increment</button> 

        {/* <button onClick = {() =>this.multiStateChange() }> Increment</button> */} 

      </> 

    ) 

  } 

}
```