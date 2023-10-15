As react app scales you need to decide which components need to re-render on state change this were memo comes in were something only re renders if props or state change 

A new component re-renders when it's parent component re-renders and when dealing with function being passed as props values we need to be aware of reference equality  

Even though two functions have the same behavior it doesn’t mean they are equal to each other so the function before a re-render is different to  the function after a re-render a when passing a prop react.Memo sees the prop has change and will not prevent the re-render  

This is where Use callback hook comes in  

useCallback is a hook that will return a memoized version of the callback function  that only changes if one of the dependencies has changed 

It is useful when passing callbacks to optimized child components that rely on reference equality to prevent unnecessary renders