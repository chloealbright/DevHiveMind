---
tags: 
author:
  - jacgit18
Comments: 
Status: 
Started: 
EditDate: 
Relates:
---
![[React Portal Modal.png]]
A modal is one of the built in windows in a web site like when you go to a newspaper and they ask you to signup 

React Portals allows you the functionality to break out of the root DOM tree so you can render to a different DOM node that isn't root  

Portals are helpful for deal with a parent component css when the child component is a modal, pop up, or a tool tip 

Portal code samples 

[https://codesandbox.io/s/00254q4n6p](https://codesandbox.io/s/00254q4n6p)  

Index.js comment out see effect with and without portal  
```javascript
   return ( 

      // return ReactDOM.createPortal( 

….. 

      </div>//, 

      // modalRoot, 

) 
```

[https://codepen.io/gaearon/pen/jGBWpE](https://codepen.io/gaearon/pen/jGBWpE)