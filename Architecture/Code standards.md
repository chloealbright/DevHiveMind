---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
# Imports 

A good rule-of-thumb for importing files at the top of your component is to group external imports at the top followed by internal imports. Order doesn't really matter, but alphabetizing by package name and file path will help find components in a long list. 

import useMediaQuery from "@material-ui/core/useMediaQuery" 

import Grid from "@material-ui/core/Grid" 

import AddIcon from "@material-ui/icons/Add" 

import Button from "../components/Button" 

import TextField from "../components/TextField" 

# React Standards 

Write Numbers as Numbers When Possible 

If using a number, without units, it should never be a string. 

Incorrect fontWeight: "700", 

[https://tracflo.slab.com/posts/react-standards-eijb0gjk](https://tracflo.slab.com/posts/react-standards-eijb0gjk) 

# Errors and Warnings 

Never merge your code or create a pull request with errors or warnings in the terminal from Eslint or otherwise. 

# File, Function, and Variable Names 

React components should always use PascalCase, and are the only files that use PascalCase (first letter uppercase). All other files should use camelCase (first letter lowercase). Stick with .js, we don't use .jsx. 

ReactComponent.js 

functionFile.js 

While there are probably exceptions, function and variable names will also follow the above rule. If a function or variable name refers to a react component, it will use PascalCase, otherwise use camelCase. 

If you need to define a constant, like the environment variables, it should use uppercase snake_case, eg: UPPERCASE_SNAKE_CASE. 

# Acronyms 

In PascalCase and snakeCase, acronyms should generally only have the first letter capitalized: 

RgbCode, UrlEndpoint 

# Avoid Abbreviations 

no args => yes arguments 

here are times where abbreviations can make sense. Using i and/or l in a for loop for example  

for (let i = 0, l = array.length; i < l; i++) {} 

# General Formatting 

Your text editor should honor .editorconfig files. Our editor config sets the editor to match Prettier and Eslint rules where possible. Tabs, for example, will be two spaces. This is a common JavaScript development standard.

# Codebase tips

Deprecation, in its programming sense, is the process of taking older code and marking it as no longer being useful within the codebase, usually because it has been superseded by newer code. The deprecated code is not immediately removed from the codebase because doing so may cause regression errors. 

When reading documentation about new features always learn about why something was created.  

Identify how important the feature is its priority, if it is a dependency for other work streams. Then keep track of key info &  Submit what you learned when asking to be reassigned to a new feature or task  

# code review 

Look at the comments and description. 

	Is there enough context so someone could review it? Is the back-and-forth discussion polite and helpful, perfunctory?  
	
	Who is doing the review (manager, tech lead, engineer?) and how long does it take? 
	
	Look at the code. Are there tests being added? Are there comments? Are there one character variable names or functions with no more than 7 arguments? 
	
	Look at the build pipeline. Are tests being run automatically? 
	
	Ask about how it was deployed. Was the process manual or automatic?  
	
	Was there a staging environment, canarying? 

Use this question as the entry point to ask about the "life of a commit" and to see the cultural dynamics on the team. If they aren't willing to show an actual review - this happened about 20% of the time for Alex - then ask the remaining follow-up questions. 

Relax constraints solve problems you want to solve within the problem or alternate problem that is similar or close to the original