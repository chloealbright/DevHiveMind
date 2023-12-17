---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[Deployment Patterns.jpeg]]

Deployment patterns are automated methods of introducing new application features to your users. Your ability to cut downtime depends on the deployment style you use. Some patterns also let you roll out extra functionality. By doing this, you can test new features with a small group of users before making them available to everyone.  We have different options for deployment patterns:  

𝟭. 𝗖𝗮𝗻𝗮𝗿𝘆 𝗿𝗲𝗹𝗲𝗮𝘀𝗲𝘀  A canary release is a method of spotting possible issues before they affect all consumers. Before making a new feature available to everyone, the plan is to only show it to a select group of users. In a canary release, we keep an eye on what transpires after the feature is made available. If there are issues with the release, we fix them. We transfer the canary release to the actual production environment once its stability has been established.  

𝟮. 𝗕𝗹𝘂𝗲/𝗴𝗿𝗲𝗲𝗻 𝗱𝗲𝗽𝗹𝗼𝘆𝗺𝗲𝗻𝘁𝘀  Here we have run two similar environments simultaneously lowering risk and downtime. These surroundings are referred to be blue and green. Only one of the environments is active at any given moment. A router or load balancer that aids in traffic control is used in a blue-green implementation. The blue-green deployment also provides a quick means of performing a rollback. We switch the router back to the blue environment if anything goes wrong in the green environment.  

𝟯. 𝗙𝗲𝗮𝘁𝘂𝗿𝗲 𝘁𝗼𝗴𝗴𝗹𝗲𝘀  Here we can turn a switch on/off with feature toggles at runtime. We may roll out new software without exposing our users to any other brand-new or modified functionality. When we build a new functionality we can use feature toggles to enable continuous deployments, by splitting releases from deployments.  

𝟰. 𝗔/𝗕 𝘁𝗲𝘀𝘁𝗶𝗻𝗴  Two versions of an app are compared using A/B testing to see which one performs better. An experiment is like A/B testing. In A/B testing, we present users with two or more page versions at random. Then, we use statistical analysis to determine which variant is more effective in achieving our objectives.  

𝟱. 𝗗𝗮𝗿𝗸 𝗹𝗮𝘂𝗻𝗰𝗵𝗲𝘀  In a "dark launch," we introduce a new feature to a select group of users rather than the general public. These users are unaware that they are helping us test the functionality. We don't even point out the new functionality to them. It is nicknamed a "dark launch" for this reason. Users are introduced to the program so that we can get feedback and test its effectiveness.