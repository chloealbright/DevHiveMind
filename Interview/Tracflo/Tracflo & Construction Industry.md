


## Tracflo Buisness Requirements Thoughts 

A mid-size project consisting of 1500-2800 square feet will typically take 6-9 months. A large renovation or new construction project consisting of 3,000-5,000 square feet with high-end details can take 9-12 months. Projects over 5,000 square feet are typically highly specialized and can easily exceed 12 months. 

So a construction project May include bulk purchases of equipment and materials each month depending on the needs 

Or maybe even weeks 

Thus tickets that have materials and equipment that need to be purchased will probably be like 4 tickets a month maybe even more 

Need to calculate tickets created each month



### Construction Industry & Data 

Company Hire gc from construction companies 

Hire General contractors 

General contractors Hire Subcontractor 

 Subcontractor include  

Plumbers | Carpenters | Electricians | HVAC | etc… 

Subs are companies with multiple crew members  

Each subcontractor has a budget they do partial work then re adjust if they see there on route to go over budget thus come approval review and negotiating  

Tickets are line order for change orders  

The scope of the general contractor’s responsibilities is broad. But their specific responsibilities are likely to vary by project and owner. But the common responsibilities for a construction project include: 

-   Creating and managing the construction schedule 
    
-   Organizing and managing the jobsite 
    
-   Hiring subcontractors and managing their quality 
    
-   Contracting suppliers and vendors 
    
-   Licensing and renting equipment 
    
-   Providing field management and labor 
    

What is a Change Order? "Change order" is just the industry term for an amendment to a construction contract that changes the contractor's scope of work.  

a minor change or addition designed to improve a text, piece of legislation, etc. 

Assisting with cleanup, safety procedure, and demolition 

On projects that require this level of project management, the general contractor usually submits a bid, or a project proposal, which outlines the scheduling, cost, and labor details of the project. Often, creating these proposals demands significant effort from the contractor, requiring quantity and material takeoff from the project specifications to create detailed cost estimates. In creating these cost estimates, the contractor considers and bills for materials, equipment rental, labor, office space, insurance expenses, worker’s compensation, and time. 

[https://www.levelset.com/retainage/](https://www.levelset.com/retainage/)  

### FIX 

Tracflo is a Fintech company in the construction industry that was created to address the problem of large construction projects being delayed because of a lot of contract disputes. The source of these disputes basically comes from unorganized paper documentation between the different parties within the project which ends up affecting financial agreements being made. 

Tracflo's solution to his problem is providing a platform that eliminates change orders by digitizing the whole construction project workflow including things like documentation generated between all the different  parties within the project  to reduce time and come to a financial agreement for a project quicker. 

So all the contracts, finances and paper work is managed by the app. Everything from the owner to the contractors and subcontractors. a lot of process occurring 

  multiple users tiers where different user can have individual access or shared access like a social media app where you can collaborate with other type of users and share documentation about certain things 

Tracflo also allow user To share updated project cost, approval signatures, photo/video/documentation 

Allows user to track manage input change project cost depending on what role you are like a general contractor can have more access than a subcontractor  

The main goal of the app is to track the change order process and give project managers access to proper documentation from different parties to form financial agreements and shorten the window It takes too get these deals done by digitizing a lot of the documentation associated with a construction project from all different parties. 

Track Labor & Material Rates like stock market so closing & open price, high, low, volume, estimates, date, Tracking things across weeks, months, years and retrieve that data and use it 

letter >change order > ticket 

letters are collection of change orders 

change orders are a collection of tickets 

Procore is an all-in-one construction management software built to help you finish quality projects—safely, on time, and within budget. Agave construction api shares data from Procore to 3rd-party systems and vice versa and gets notifications when there is a change in data And maybe other systems. 

Change order" is just the industry term for an amendment to a construction contract that changes the contractor's scope of work. 

**Table relation dependency order left to right with description  

| Role | Markup | Action | User | File | Company |
|------|--------|--------|------|------|---------|

| Payment | Company_user  | Material_type  | Equipment_type  | Project | Contact  |
|------|--------|--------|------|------|---------|
 
| Break_material | Break_equipment | Letter  | Proj_user  | Proj | Proj_subcontractor |
|------|--------|--------|------|------|---------|


| Chg_order | Rev_letter | Labor_type | Rev_chg_order | Break_labor | Rev_tick | history |
|--------------|------------|------------|------------------|-------------|------------|---------|



```javascript

const overviewResponse = async (project_id) => { 

Project Overview: 

Overdue = ticket past 60 days waiting to be approved 

In review = Ticket sent by the sub, waiting for GC for action 

Open = tickets waiting to be communicated by the sub, after GC has approved the T&M 

Owner Review = When the ticket has been completed by GC & sub and is in owners court to approve it tickets in a month 

Resolved = owner approved/ cost approved in our system 

Received = tickets sent by subs 

Average response time = action made on the ticket for the first time by GC 

Average resolved time = how long it took to get the cost approved by the GC 

Ticket resolved = % of ticket that has been cost approved 

  //unresolved tickets 

  const data = { 

	    overdue: 0, 
	
	    open: 0, 
	
	    tm_review: 0, 
	
	    cost_review: 0, 
	
	    trends: { 
	
		      ticket_history: new Array(), 
		
		      cost_resolved: 0, 
		
		      received: 0, 
		
		      response_time: "33m", 
		
		      resolve_time: "3h 8m", 
		
		      percent_resolved: "93%", 
	    }, 

	    sub_unresolved: 0, 
	
	    gc_unresolved: 0, 
	
	    owner_unresolved: 0, 

  } 

const statsResponse = async (proj_id) => { 

  const data = { 

	    price_history: response, 
	
	    factors: [ 
	
	      { name: "labor", value: 0 }, 
	
	      { name: "material", value: 0 }, 
	
	      { name: "equipment", value: 0 }, 
	
	    ], 
	    
	  }
}
```