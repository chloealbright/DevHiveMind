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