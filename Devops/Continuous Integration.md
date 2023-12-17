---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Strictly speaking, CI refers to merging developer changes to the main branch often, Wikipedia even helpfully suggests: "several times a day". This is usually true but when we refer to CI in industry, we're usually talking about what happens after the actual merge happens. 

We'd likely want to do some of these steps: 

Lint: to keep our code clean and maintainable 

Build: put all of our code together into software 

Test: to ensure we don't break existing features 

Package: Put it all together in an easily movable batch 

Upload/Deploy: Make it available to the world 

Basically the whole process of adding features to main branch  

Usually, strict definitions act as a constraint on creativity/development speed. This, however, should usually not be true for CI. This strictness should be set up in such a way as to allow for easier development and working together. Using a good CI system (such as GitHub Actions that we'll cover in this part) will allow us to do this all automagically. 

In the continuous integration process packaging and especially deployment aren't included in the scope of the process 

but in the real world there are often issues like with the packaging process where testing the  packages during the continuous integration process is needed even if you don't do anything with their package in some cases you might even test the already built package this assures us when we have tested the code in the same form as what we deployed to production 

Not when it comes to deployment we want a process that looks the same whether we're running tests on development Branch or the main branch in fact the process May literally be the same with only a check at the end to determine if we are on the main branch and need to do a deployment and just contacts and makes sense to include deployment in the continuous integration process since we'll be maintaining it at the same time we work on continuous integration 

The terms <b>Continuous Delivery</b> and <b>Continuous Deployment</b> (both of which have the acronym CD) are often used when one talks about CI that also takes care of deployments. We won't bore you with the exact definition (you can use e.g. Wikipedia or another Martin Fowler blog post) but in general, we refer to CD as the practice where the main branch is kept deployable at all times. In general, this is also frequently coupled with automated deployments triggered from merges into the main branch. 

What about the murky area between CI and CD? If we, for example, have tests that must be run before any new code can be merged to the main branch, is this CI because we're making frequent merges to the main branch, or is it CD because we're making sure that the main branch is always deployable? 

So, some concepts frequently cross the line between CI and CD and, as we discussed above, deployment sometimes makes sense to consider CD as part of CI. This is why you'll often see references to CI/CD to describe the entire process. We'll use the terms "<b>CI</b>" and "<b>CI/CD</b>" interchangeably in this part. 

# Types of CI setup 

To meet some of the requirements listed above, we want to dedicate a separate server for running the tasks in continuous integration. Having a separate server for the purpose minimizes the risk that something else interferes with the CI/CD process and causes it to be unpredictable. 

There are two options: host our own server or use a cloud service. 

# Jenkins (and other self-hosted setups) 

Among the self-hosted options, Jenkins is the most popular. It's extremely flexible and there are plugins for almost anything (except that one thing you want to do). This is a great option for many applications, using a self-hosted setup means that the entire environment is under your control, the number of resources can be controlled, secrets (we'll elaborate a little more on security in later sections of this part) are never exposed to anyone else and you can do anything you want on the hardware. 

Unfortunately, there is also a downside. Jenkins is quite complicated to set up. It's very flexible but that means that there's often quite a bit of boilerplate/template code involved to get builds working. With Jenkins specifically, it also means that CI/CD must be set up with Jenkins' own domain-specific language. There are also the risks of hardware failures which can be an issue if the setup sees heavy use. 

With self-hosted options, the billing is usually based on the hardware. You pay for the server. What you do on the server doesn't change the billing. 

# GitHub Actions and other cloud-based solutions 

In a cloud-hosted setup, the setup of the environment is not something you need to worry about. It's there, all you need to do is tell it what to do. Doing that usually involves putting a file in your repository and then telling the CI system to read the file (or to check your repository for that particular file). 

The actual CI config for the cloud-based options is often a little simpler, at least if you stay within what is considered "normal" usage. If you want to do something a little bit more special, then cloud-based options may become more limited, or you may find it difficult to do that one specific task for which the cloud platform just isn't built for. 

In this part, we'll look at a fairly normal use case. The more complicated setups might, for example, make use of specific hardware resources, e.g. a GPU. 

Aside from the configuration issue mentioned above, there are often resource limitations on cloud-based platforms. In a self-hosted setup, if a build is slow, you can just get a bigger server and throw more resources at it. In cloud-based options, this may not be possible. For example, in GitHub Actions, the nodes your builds will run on have 2 vCPUs and 8GB of RAM. 

Cloud-based options are also usually billed by build time which is something to consider. 

# Why pick one over the other  

In general, if you have a small to medium software project that doesn't have any special requirements (e.g. a need for a graphics card to run tests), a cloud-based solution is probably best. The configuration is simple and you don't need to go to the hassle or expense of setting up your own system. For smaller projects especially, this should be cheaper. 

For larger projects where more resources are needed or in larger companies where there are multiple teams and projects to take advantage of it, a self-hosted CI setup is probably the way to go.