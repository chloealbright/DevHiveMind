“pages/” vs. “ui/” 

The split between src/pages/ and src/ui/ is also purposeful and by design. While ui/ is meant to be a collection of reusable React code(i.e. components, hooks, and contexts ), pages/ specifically (a) maps components to routes and (b) composes ui/ and lib/ code together. Generally speaking, code should never depend upon (i.e. import) code from pages/ except for (a) src/App.js setting up the top-level routes and (b) parent pages on sub-pages (i.e. component for route http://example.org/invoices imports component page handing route http://example.org/invoices/:id.). 



The “lib/” Folder 

The lib/ folder is the place to collect your non-UI code. The kind of code and operations that could/should survive completely changing your JavaScript framework. The lib/core/ folder is a personal favorite, as that is the place to collect your domain objects and business logic, usually in the form of pure functions. The wider lib/ folder should contain infrastructural code like network layer clients, formatting utilities, platform communication like Browser Storage or IndexDB, etc. 

At the start of a project, I recommend beginning with only lib/ and lib/core/, and to let the remaining folders emerge organically. 


Manifest.json file in public folder is for pwa


Dependencies: Made More Explicit 

By knowing the location of code, you should have an idea on what code is most likely to depend, or not depend, on it. In this layout, the following rules are expected to hold: 



Code from lib/ never imports code from ui/ or pages/. 

Code from pages/ should import implementation code from ui/ or lib/. 

Code from ui/ may import code from lib/ but never from pages/. 

Generally, code may import from within their own top-level namespace: i.e. pages/, lib/, ui/.