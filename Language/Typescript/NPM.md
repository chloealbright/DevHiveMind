(@) prefix on npm packages 

This is a new feature of NPM called 'scoped packages', which effectively allow NPM packages to be namespaced. Every user and organization on NPM has their own scope, and they are the only people who can add packages to it. 

This is useful for several reasons: 

-   It allows organizations to make it clear which packages are 'official' and which ones are not. 
    
    -   For example, if a package has the scope @angular, you know it was published by the Angular core team. 
        
-   The package name only has to be unique to the scope it is published in, not the entire registry. 
    
    -   For example, the package name http is already taken in the main repository, but Angular is able to have @angular/http as well. 
        

The reason that [scoped packages don't show up in public search](https://github.com/npm/npm/issues/8244) is because a lot of them are private packages created by organizations using NPM's paid services, and they're not comfortable opening the search up until they can be totally certain they're not going to make anything public that shouldn't be public - from a legal perspective, this is pretty understandable.