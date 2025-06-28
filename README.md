# Capstone-Project-2
Let's dive right into Sql! Shall we?

## PROJECT TOPIC: MEGA STORES INVENTORY
### Project Overview 



#### Data Source: Provided by DSA
#### Tools Used 
 - MS Excel for data cleansing
    -For data collection
    -For data manipulation
    -For data munching
 - SQL Sever for querying and analysis
   
```  SQL QUERY
create database capstone_project

Use Capstone_project 
---Case scenario 1
select * from [dbo].[KMS Sql Case Study]

---1. Which product category had the highest sales?---
select Product_Category, Sales from [dbo].[KMS Sql Case Study]
where sales = (select max(sales) from [dbo].[KMS Sql Case Study])

--2. What are the top 3 and bottom 3 regions in terms of sales?
select top 3 region, SUM(sales) as totalsales from [dbo].[KMS Sql Case Study]
GROUP BY Region 
ORDER BY totalsales DESC

select top 3 region, SUM(sales) as totalsales from [dbo].[KMS Sql Case Study]
GROUP BY Region
ORDER BY totalsales ASC

---3. What were the total sales of appliances in Ontario?---
Select sum(sales) as TotalSales from [dbo].[KMS Sql Case Study]
where Region = 'Ontario'

---4. Advise the management of KMS on what to do to increase the revenue from the bottom 10 customers?--
Select Top 10 * from [dbo].[KMS Sql Case Study]
ORDER BY profit DESC

Select Top 10 * from [dbo].[KMS Sql Case Study]
ORDER BY Profit ASC 

---- I will advise KMS to probably increase discounts to attract and bring more customers in. 
---- Also, increase in advertisement would be good.
---- The unit price can be reduced to increase quantity of goods being bought.
---- Shipping cost


