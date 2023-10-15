
### Coupling(Glasses vs surgery) vs Cohesion(master none /  master of specifics things)


The goal is to have Loose Coupling & High Cohesion 

Coupling and cohesion are terms which occur together very frequently. Coupling refers to the inter-dependencies between modules/classes, 

## Tight Coupling 

Tight coupling would be the eyes. If I want to fix my vision, I'ts very expensive to get an eye transplant and holds a fair amount of risk. But what if the designer (being the human race) found a better way. Add a feature that is loosely coupled to the body so it can be easily changed! (yes.. glasses) 

## Loose coupling 

I can easily replace my glasses without breaking my underlying vision. I can take off the glasses and my vision will be how it was before (not better or worse). Using different pairs of glasses changes how we see the world through our eyes with little risk and easy maintainability. 

Microservices should be loosely coupled, meaning that **they should not have a tight dependency on each other, to ensure scalability and ease of deployment.**

For example, if one microservice is down, the others should still be able to function normally. Here is a diagram which illustrate tightly coupled and loosely coupled Microservices:

![[coupling.jpg]]


while cohesion describes how related the functions within a single module/class are. 

## Example of Low Cohesion: 


--------------------------- 

|         Staff           | 

---------------------------- 

| checkEmail()     | 

| sendEmail()       | 

| emailValidate()  | 

| PrintLetter()       | 

----------------------------- 

##  Example of High Cohesion: 

----------------------------------------- 

|                Staff                    | 

------------------------------------------ 

| -salary                                | 

| -emailAddr                         | 

------------------------------------------ 

| setSalary(newSalary)       | 

| getSalary()                         | 

| setEmailAddr(newEmail) | 

| getEmailAddr()                  | 

------------------------------------------ 

[https://www.youtube.com/watch?v=TCMGU7-Ir_k&list=WL&index=15&ab_channel=QuiCap](https://www.youtube.com/watch?v=TCMGU7-Ir_k&list=WL&index=15&ab_channel=QuiCap)