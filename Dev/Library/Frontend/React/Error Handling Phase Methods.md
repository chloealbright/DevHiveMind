Static getDeriviedStateFromError(error) 

Static componentDidCatch(error, info) 

These are used when an error occurs during rendering in a lifecycle method or in the constructor of any child component 

These are also known as error boundaries and can be both use or individually used  

getDeriviedStateFromError is used to render a fallback UI after an error is thrown so the error pg that comes up if you mistype something it is also might be used in production code  

componentDidCatch logs to error info a little redundant