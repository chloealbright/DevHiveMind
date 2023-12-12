---
tags: 
author:
  - jacgit18
Status: init
Started: 
EditDate: 
Relates:
---
Crafting acceptance criteria is an iterative process that unfolds at the story's inception, matures in the middle, and gains additional insights towards completion. It is a crucial aspect written from the product perspective, defining scope and standing as one of the benchmarks for the definition of done.

Consider the following user story as an illustration:

> As a website visitor, I can see all flights departing from my selected airport to my desired destination on the selected day to pick a flight that meets my travel needs.

Within the acceptance criteria, complexities may surface, potentially leading to the identification of additional user stories for future development. Each acceptance criterion functions like a sequential list, detailing outcomes based on the process flow.

Multiple acceptance criteria can sometimes evolve into stories with their own acceptance criteria, emphasizing that the definition of ready is conventionally applied at the user story level rather than at the granularity of acceptance criteria.

For instance, the acceptance criteria for the aforementioned story could break down as follows:

- The visitor can see a list of all available flights that fit the criteria.
- If no flight fits the criteria, the visitor can choose to see alternative dates.
- If no flights fit the criteria, the visitor can choose to see alternate destinations.
- If no flight fits the criteria, the visitor can choose to see alternate departures.
- Once the visitor picks a flight, the booking window will be offered.

It is paramount to keep the criteria in scope concerning the story, differentiating it from out-of-scope elements, such as potential reward points for the visitor.

An additional example, "Fred requesting recommended training topics," demonstrates the interconnectedness of the acceptance criteria in a story:

```vb
Given Fred is logged into the website
And Fred has unfinished training topics
When Fred requests a training plan
Then Fred's customized training plan is viewable.
```

A guiding principle emerges: avoid working on stories that do not meet the definition of ready. This underscores the importance of a single user story containing multiple acceptance criteria, contributing to a comprehensive and well-defined understanding of the development scope.