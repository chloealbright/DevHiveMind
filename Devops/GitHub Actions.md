GitHub Actions work on a basis of workflows. A workflow is a series of jobs that are run when a certain triggering event happens. The jobs that are run then themselves contain instructions for what GitHub Actions should do. 

A typical execution of a workflow looks like this: 

	Triggering event happens (for example, there is a push to the main branch). 
	
	The workflow with that trigger is executed. 
	
	Cleanup




Basic needs 

In general, to have CI operate on a repository, we need a few things: 

	A repository (obviously) 
	
	Some definition of what the CI needs to do: This can be in the form of a specific file inside the repository or it can be defined in the CI system 
	
	The CI needs to be aware that the repository (and the file within it) exist 
	
	The CI needs to be able to access the repository 
	
	The CI needs permissions to perform the actions it is supposed to be able to do: For example, if  
	
	the CI needs to be able to deploy to a production environment, it needs credentials for that environment. 

That's the traditional model at least, we'll see in a minute how GitHub Actions short-circuit some of these steps or rather make it such that you don't have to worry about them! 

GitHub Actions have a great advantage over self-hosted solutions: the repository is hosted with the CI provider. In other words, Github provides both the repository and the CI platform. This means that if we've enabled actions for a repository, GitHub is already aware of the fact that we have workflows defined and what those definitions look like.