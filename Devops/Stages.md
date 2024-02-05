---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
![[Software Life Cycle.gif]]




Tries to remove roadblocks in terms of the different processes in software development from the idea stage to the implementation to the testing to the building to the deployment and observation of the system 

By automating and streamlining processes optimizing the system 

Developer and operation managers work together to close the gap to do this I suppose that I'm working separately in terms of developers working on new features and operations maintaining the system that is there 

The implementation of DevOps can vary from company to  company 

Continuous integration & delivery of source code  


Package management 

Source code management 

Treating infrastructure as code 

Container orchestration  

Cloud  

Continuous monitoring 

![[Development Stages to Production.png]]

DevOps may help with releasing things quickly but it isn't the most stable thing that is where the site reliability engineer role comes in 

What’s a feedback loop? 

When the pipeline runs unit tests on your code, and it fails a test? That’s just one example of feedback. You know that your code isn’t ready for production. 

An excellent pipeline should take care of the following: 

Compiling and testing the code (Continuous Integration) 

Producing an artifact from the code, ready to be deployed (Continuous Delivery) 

Deploying the application to a server automatically (Continuous Deployment) 

# The trigger 

The best pipelines are triggered automatically when new code is committed to the repository. 

You can either configure your CI/CD tool to poll for changes to a Git repository, or you can set up a Webhook to notify your CI/CD tool whenever a developer makes a push. 

The main reason for doing this is to make running the pipeline automatic, and friction-free. 

If you leave the pipeline to be run manually, people will sometimes forget to run it, or choose not to. It’s far better to just make this an automated step. 

There is huge confidence that comes from knowing that your code is going to be tested on every single change. 

# Code checkout 

In this first stage, the CI server will check out the code from the source code repository, such as GitHub or Bitbucket. 

The CI/CD tool usually receives information from a poll, or a webhook, which says which specific commit triggered the pipeline. 

The pipeline then checks out the source code at a given commit point, and starts the process. 

# Compile the code 

If you’re developing in a compiled language like Java, the first thing you’ll probably need to do is compile your program. 

This means that your CI tool needs to have access to whatever build tools you need to compile your app. For example, if it’s Java, you’ll use something like Maven or Gradle. 

Ideally this stage should run in a clean, fresh environment. This is one of the great use cases for Docker containers – being able to create fresh build environments easily and repeatably. 

# Run unit tests 

The next key element of your CI/CD pipeline is unit testing. This is the stage where you configure your CI/CD tool to execute the tests that are in your codebase. 

You might use Maven or Gradle to do this in Java, or Jest in JavaScript. 

The aim at this point is not only to verify that all the unit tests pass, but that the tests are being maintained and enhanced as the code base grows. 

If the application is growing rapidly, but the number of tests stays the same, this isn’t great, because it could mean that there are large parts of the code base which are untested. 

According to Martin Fowler, the bulk of your tests should be unit tests. Unit tests offer the biggest “bang for your buck”. They are easy to write, cheap to run and have the lowest cost to maintain. 

# Package the code 

Once all of the tests are passing, you can now move on to packaging the code. Exactly how you package your application depends on your programming language and target environment. 

If you’re using Java, you might build a JAR file. If you’re using Docker containers, you might build a Docker image. 

Whatever packaging format you choose, a good practice is that you should build the binary only once. Don’t build a different binary for each environment, because this will cause your pipeline to become very complex. 

# Run acceptance tests 

Now comes the time to perform acceptance testing on your application. 

Acceptance tests are a way of ensuring that your software does what it is meant to do, and that it meets the original requirements. 

But manual acceptance testing is very tedious and time-consuming. So there are a growing number of ways that you can perform automated acceptance testing. 

	# What is automated acceptance testing? 
	
	A lot of acceptance tests can be automated. You can use tools like Cucumber and its Gherkin syntax for describing acceptance test criteria, or Selenium, which can simulate user actions, such as opening web sites or clicking on links. 
	
	The point of this stage is to reduce or eliminate the time spent manually testing. 
	
	If your current process requires building a binary, and then sending it over to a test team to be manually tested, then you will know that this takes a lot of time. By automating as many tests as possible, you can reduce the time it takes to get your software into the hands of real users. 

# Delivery or Deployment 

Finally, when the application has been tested, it can move into the delivery or deployment stage. 

At this stage, you have an artifact ready to be deployed (continuous delivery). Or, you can continue to CI/CD heaven and automatically deploy your software (continuous deployment). 

Most pipelines don’t make it to this final stage, and that’s a shame. There is enormous value in being able to automatically deploy your software into production. 

To achieve continuous deployment, you need a production environment to deploy into. If you’re deploying to a public cloud, you can use the cloud provider’s API to deploy your application. Or if you’re using Kubernetes, you might use a Helm chart to deploy your app. 

And finally, this is the end of your pipeline! 

The next time a developer commits code into the repository, it will be run all over again.



