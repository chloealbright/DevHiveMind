![[0_EitUXT-pqbaQSCTt.gif]]

-   React was created because of the need to manipulate the [DOM](onenote:Markup%20Language.one#DOM&section-id={da439dc5-1ba5-4ca1-a3ec-ea25cd45339b}&page-id={fc0baa67-e76e-42ee-a04a-daffc5d782d4}&end) more efficiently so it created a virtual DOM to do this which made things more secure especially in terms of data when handling it. 
    

-   The virtual DOM is a programming concept where an ideal, or “virtual”, representation of a UI is kept in memory and synced with the “real” DOM by a library such as ReactDOM. This process is called [reconciliation](https://reactjs.org/docs/reconciliation.html). 
    

-   Data flows from top to bottom it uses a virtual DOM to solve the issue with altering the actual DOM. 
    

-   JSX stands for JavaScript XML. It allows us to write JavaScript with HTML-like syntax, Not HTML nor a String! without using createElement() or appendChild() methods. 
    

But renders down to JS 

Instead of returning html if you were not using jsx you return something like this React.createElement('div', null, "hello")  and pass in other React.createElement for other tags 

-   Use react-bootstrap for the general components then when you want to get specific use bootstrap. 
    

-   react-app look into configurations set up by create-react-app 
    
    -   So create-react-app forces you to have the directory in the same place as your package.json location. If you’re going to change how your directories are organized, you can run yarn run eject, but that means you won’t be using the configurations set up by create-react-app. 
        
    
    [https://reactjs.org/docs/getting-started.html](https://reactjs.org/docs/getting-started.html) 
    
    [https://create-react-app.dev/docs/available-scripts/](https://create-react-app.dev/docs/available-scripts/)