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

----5. KMS incurred the most shipping cost using which shipping method?
Select Shipping_Cost, Ship_Mode from [dbo].[KMS Sql Case Study]
where shipping_cost = (select  Max(shipping_cost) as Max_shipping_Cost from [dbo].[KMS Sql Case Study])

---Case Scenario II--

--6. Who are the most valuable customers, and what products or services do they typically purchase? 
select * from [dbo].[KMS Sql Case Study]
select Top 5 Profit, sales, Product_Name, Customer_Name
FROM [dbo].[KMS Sql Case Study]
ORDER BY Profit DESC

---Select Top 5 sales, Product_Name,Customer_Name
---FROM [dbo].[KMS Sql Case Study] where Customer_Name = 'Jasper Cacioppo'

---Select Top 5 sales, Product_Name,Customer_Name
FROM [dbo].[KMS Sql Case Study] where Customer_Name = 'Jasper Cacioppo'


---7. Which small business customer had the highest sales?
Select Top 1 Customer_Name, SUM(Sales) AS Total_Sales
FROM [dbo].[KMS Sql Case Study]
WHERE Customer_Segment = 'Small Business'
GROUP BY Customer_Name
ORDER BY Total_Sales DESC

---8. Which Corporate placed the most number of orders in 2009-2012?
SELECT Top 1 Customer_Name, COUNT(Order_ID) AS Order_Count
FROM [dbo].[KMS Sql Case Study]
WHERE Customer_Segment = 'Corporate'
GROUP BY Customer_Name
ORDER BY Order_Count DESC

---9. Which consumer customer was the most profitable one?
SELECT Top 1 Customer_Name, SUM(Profit) AS Total_Profit
FROM [dbo].[KMS Sql Case Study]
WHERE Customer_Segment = 'Consumer'
GROUP BY Customer_Name
ORDER BY Total_Profit DESC

---10. Which customer returned items, and what segment do they belong to?



---11. If the delivery truck is the most economical but the slowest shipping method and Express Air is the fastest but the slowest shipping method and Express Air is the fastest but the most expensive one, do you think the company appropriately spent shipping costs based on the Order Priority? Explain your answer
Select Ship_mode, order_priority, shipping_cost, order_date, ship_date from [dbo].[KMS Sql Case Study]
order by shipping_cost DESC

````````CASE CLOSED!
