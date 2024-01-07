---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
MYSQL is  basically an open source version of SQL 

package name plus class name avoid name collision   

for src folder just create class package will generate automatically 

show dbs; 

use productdb; 

db.productSold.findOne()// just finds random entry 

db.productSold.find({"state.code": "NY"},{ }).pretty() 

 db.productSold.find({"summary.count": {$gt:20} }, {_id: 0, invoice: 1, "summary.count":1, state:1 }) 

db.productSold.find({"summary.count":{$gt:20}, "state.code":"ID" },{_id:0, invoice: 1, "summary.count": 1, state:1 }) 

drop database 

use nameofdatabase_to_switch_to_that_you_want_to_drop 

db.dropDatabase() 

collection creation automatically occurs when you insert a doctument like this 

db.tutorialspoint.insert({"name" : "tutorialspoint"}) 

/*   

collection are contained in db 

*/ 

db.heroesdb.insert([ 

    { 

    _id:2000, company: "marvel", 

    name: "tony starks", alias: "Iron Man",  

      abilities: [{ability: "running", level: 5 } 

                 ,{ability: "flying", level: 8} 

                 ,{ability: "Strength", level: 9} 

                 ,{ability: "wealth", level: 10} 

                 ,{ability: "intelligence", level: 10} 

                ]) 

sudo service mongodb start 

sudo service mongodb restart



MongoDB 

--------------------------------------- 

mongod --port 27018 

or  

mongod  

crtl c exits out of mongodb 

MongoDB and javaScript 

----------------------------------------------- 

running javascript in terminal 

node file.js 

tab at the end for the javascript file in the terminal when running a javascript file for MongoDB 

use nameofdb;   

db 

show dbs 

show collections 

db.stocks.drop(); 

for (i = 0; i < 100 ; i++){ 

   let data = {_id: i 

             , name: "international business machine-" + i 

             , symbol:"ibm-" + i 

             , price: 30 + i  } 

   db.stocks.insert(data)  

} 

db.stocks.count() 

db.stocks.find() 

db.stocks.find({symbol: "ibm-1"}).pretty() 

db.stocks.find({symbol: {$eq: "ibm-1"}  } ).pretty() 

db.stocks.find({price: {$gt: 30}  } ).pretty() 

db.stocks.find({price: {$lte: 50}  } ).pretty()// lesser than or equal could also do gte 

-1 is decending order and 1 is accending limit gives you the ability to control how many values display in a row than skip allows you to





## MongoDB v Mongoose

In terms of Node. js, MongoDB is the native driver for interacting with a MongoDB instance and Mongoose is an Object modeling tool for MongoDB. mongoose is built on top of the MongoDB driver to provide programmers with a way to model their data. 

[https://mongoosejs.com/docs/](https://mongoosejs.com/docs/)

## Mongoose v Sequelize

Sequelize is a tool or a level of abstraction which converts data in a relational database into programmatic objects that can be manipulated by a developer using a programming language, such as JavaScript. Mongoose is an Object Document Mapper (ODM), a JavaScript layer to access MongoDB. 

[https://medium.com/sequelize-to-mongoose-and-vice-versa-a-developers/sequelize-to-mongoose-and-vice-versa-a-developers-guide-906bdf79e81#:~:text=Sequelize%20is%20a%20tool%20or,JavaScript%20layer%20to%20access%20MongoDB](https://medium.com/sequelize-to-mongoose-and-vice-versa-a-developers/sequelize-to-mongoose-and-vice-versa-a-developers-guide-906bdf79e81#:~:text=Sequelize%20is%20a%20tool%20or,JavaScript%20layer%20to%20access%20MongoDB).