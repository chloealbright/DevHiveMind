***Webpack*** is an open-source JavaScript module mainly designed for JavaScript. It can transform front-end assets such as HTML, CSS, and images if corresponding loaders are included. Webpack takes the dependencies and general dependency graph allowing web developers to use a modular approach for their web application development process. It also provides built-in development server called a webpack dev server that can be used as an HTTP server for serving files while developing.

***Gulp***: is the best alternative for webpack. It is an open-source JavaScript toolkit, used for streaming build systems in front-end web development. It is a task runner which is built on nom and node.js. Mainly used for automation to save time and repeat certain tasks involved in web development like cache busting, linting, concatenation, minification, unit testing, optimization, etc. It uses code over configuration approach to define the tasks and relies on its small, single-purpose plugins and o carry them out. It allows users to write their own plugins to define their own tasks.

***Babel***: Another best alternative for webpack is babel, which is open-source JavaScript transcompiler. It is used to convert ECMAScript 2015+ code into backwards compatible version of JavaScript that can be run by older JavaScript engines. It is a popular tool for using the newest features of the JavaScript programming language. Developers use this called npm registry to convert their source code into versions of JavaScript that web browsers are able to process. It converts the syntax that is not widely supported into backward compatible versions. It can also convert nonstandard JavaScript syntax such as JSX.

enables e6 syntax in babel file

    "babel-cli": "^6.26.0",

    "babel-preset-env": "^1.7.0",

    "babel-preset-stage-0": "^6.24.1",

Parcel: is another JavaScript tool that can take any type of file as an entry point. It utilizes worker processes to compile your cod in parallel, utilizing modern multicore processors. It boosts the speed for initial builds. It also has a file system cache that saves the compiled results per file, for even subsequent startups. Parcel takes as input a single entry asset which could be any file type such as JS, HTML, image, CSS, etc.  The assets are parsed, their dependencies are extracted and they are transformed to their final compiled form.

Browserify is another alternative to webpack, an open-source JavaScript tool that allows developers to writer node.js style modules that compile for use in the browsers. Browsers does not have to require method but node.js does. With browserify user can write the code that uses require in the same way that, will use it in node. It supports operating systems such is windows, Linux and macOS. Browserify is a tool that brings many of the resources of the NPM ecosystem off of the server and into the client. It add the source of all the require modules and their dependency used in source.js and bundles them in target.js.

Grunt: It is a JavaScript task runner tool that automate the tasks such as compilation, linting, unit testing and minification. To run the custom task defined in the file, grunt uses a command line interface. It supports operations systems, such as Windows, Linux, and MacOS. Grunt allows developers to add, modify and extend the custom tasks to fit their personal needs.  Each of these task has a set of configuration options that can be set by the user. It has the ability to combine multiple existing tasks into a single task or entire new functionality.

npm: stands for the node package manager. It is a package manager for the JavaScript programming language. It is a default package manager for a JavaScript runtime environment called node.js.  It consists of command line client and an online database of public and paid for private packages. It allows users to consume and distribute JavaScript modules that are available in the registry. In npm registry packages are stored in common JS format and include metadata files in JSON format. nom can manage the packages that are local dependencies of particular objects as well as globally installed JavaScript tools.

RequireJS: is an JavaScript library and file loader that manages the dependencies between JavaScript files and in modular programming. It improves the speed and the quality of the code. RequireJS can load nested dependencies and provides asynchronous module loading. It combines and minifies modules into one script for an optimized experience.  It has the ability to gather JavaScript files from different modules. It can load more than one JavaScript file.


bundle.js use webpack 

Write or link javascript <script> tag at bottom of code before   </body> tag makes pg run better