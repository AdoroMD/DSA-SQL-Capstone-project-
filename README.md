# Project Topic: Kultra Mega Stores (KMS), Order Review 
## Aim: To analyze KMS order data and generate key insights

## Objectives: To answer set of sales questions using the data provided 
### Questions for Case Scenario 1: 

- Q1. Which product category had the highest sales

- Q2. what are the top 3 and bottom 3 regions in terms of sales 

- Q3. What were the total sales of appliances in Ontario
  
- Q4. Advice the management of KMS on what to do, to increase the revenue from the bottom  10 customers.
  
- Q5. KMS incurred the most shipping cost using which shipping methods 

## To create a data base for this project, 
### Go to new query-> create database DSA_SQL_Capstone_Project 
### execute to create the database.

### right click on the created database 
--> Task --> Import Flat file --> next --> select data source-->  browse file location --> open --> next -->set data type --> finish and close 

### To determine which product category has the highest sales.
#### first let's ensure the category column and the sales column does not have a missing values 

- select product_category from KMS,
- where product_category is null
  
### we do same for the sales column
- select sales from KMS,
- where sales is null

### From the output, both products_category and sales do not have missing values.

- Q1. Which product_category had the highest sales?
  
 - select productcategory,  sum(sales) as total_sales from KMS group by product_category order by product_category DESC

### The Technology product_category had the highest number of sales with total_sales of 5.9 million 

- Q2. What are the top 3 and bottom 3 regions in terms of sales?

  -  
- 
  - 
