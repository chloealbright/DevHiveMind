---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Rate limiting is a control mechanism employed by API owners to prevent the system from being overtaxed by API data traffic and to tie API usage to specific business outcomes. There are various subcategories of rate limits, and in fact the whole topic is specifically tied to the general area of traffic management. We will cover all the options later in Chapter 8. 

Before getting to the technical details, however, it is important to discuss how business-level rate limits, which we call quotas, affect the design of the API. 

A quota is a rate limit that attaches a business outcome to a specific number of transactions. Its purpose is to maintain a business policy related to API usage. On Twitter, for example, application developers are allowed to check their timelines between 150 and 350 times an hour, depending on the current state of the Twitter infrastructure. Those who go over that quota receive an error. A common purpose for a quota is to divide developers into segments, each of which has a different quota, and thus a different relationship with the API. For example, it is common to offer API access with a small quota to any developer who signs up for an account, but require either additional verification, or even a charge, for a higher rate limit. 

As with hardware and infrastructure, the need for a quota has a lot to do with scale and usage characteristics. The guiding question is, “How valuable is my information, and what happens if the API is enormously successful?” For example, some content APIs are fully open, require no user authentication, and thus need to be protected from too much traffic. Twitter has to have a rate limit because of the likelihood that users could check their timelines 1,000 times per second. The infrastructure can’t absorb that level of traffic. 

Clearly, it is possible to go overboard with quotas. Sometimes they are applied punitively, making the service almost unusable. It becomes difficult to test the service, and eventually developers move away from it. We encourage some flexibility—rates inevitably go higher when developers test their applications. A mechanism to charge developers for higher than normal rates can help manage those requests. 

Don’t forget that quotas have a benefit for private APIs too, even inside the corporate firewall, because they can help reduce risk. For instance, an organization may be considering opening up some of the enterprise “crown jewels” as an API to speed creation of future business products, but those “crown jewels” run on expensive and critical infrastructure. By deploying a quota, the team that owns the API has the option of making that content or service available for internal innovation, while reducing the risk of internal problems—and reducing the risk of an unpleasant meeting with the operations team! In other words, effective use of quotas can help an internal API team bring some of the agility of the Internet to the enterprise.