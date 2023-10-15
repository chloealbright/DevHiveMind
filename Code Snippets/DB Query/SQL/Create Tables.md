
```SQL
CREATE TABLE mycampaign ( 

    id INTEGER PRIMARY KEY, 

    campaign_name VARCHAR, 

    company_id INTEGER 

); 

CREATE TABLE creative ( 

    id INTEGER PRIMARY KEY, 

    fb_post_id INTEGER, 

    campaign_id INTEGER 

); 

CREATE TABLE company ( 

    id INTEGER, 

    name VARCHAR 

);

```
