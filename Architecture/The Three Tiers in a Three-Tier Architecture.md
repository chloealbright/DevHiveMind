You have your presentation tier (user interface/client) 

logic tier (virtual server/services) 

data tier (storage/databases) 

In the case of horizontal scaling, you can delegate each tier (or the functions responsible for them) to a different node.  

However, you may already be running these tiers on different servers but find that one of these servers is underperforming or no longer meets demands. Once again, you can choose to scale this server vertically or horizontally. You may upgrade it with more resources or add another server to share the workload.  

For further illustration, let’s consider databases. If you host your database on a single dedicated server and it gets too large, horizontal scaling would mean adding a new node, partitioning, and sharing the data between the old server and the new. 

In our “lifting weights” analogy, horizontal scaling would mean buying new clothes while vertical scaling would be modifying your old clothes to handle your new gains.