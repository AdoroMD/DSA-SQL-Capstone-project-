# Project Topic: Kultra Mega Stores (KMS), Order Review 
## Aim: To analyze KMS order data and generate key insights

## Objectives: To answer set of sales questions using the data provided 
### Questions for Case Scenario 1: 

### Q1. Which product category had the highest sales

### Q2. what are the top 3 and bottom 3 regions in terms of sales 

### Q3. What were the total sales of appliances in Ontario
  
### Q4. Advice the management of KMS on what to do, to increase the revenue from the bottom  10 customers.
  
### Q5. KMS incurred the most shipping cost using which shipping methods 

### To create a data base for this project, 
- Go to new query-> create database DSA_SQL_Capstone_Project
execute to create the database.

- right click on the created database
- go to Task --> Import Flat file --> next --> select data source-->  browse file location --> open --> next -->set data type --> finish and close

### Answering Questions 

 1. To determine which product category has the highest sales.
 - first let's ensure the category column and the sales column does not have a missing values 

  - select product_category from KMS,
  - where product_category is null
  
#### we do same for the sales column
- select sales from KMS,
- where sales is null

#### From the output, both products_category and sales do not have missing values.

### Q1. Which product_category had the highest sales?
  
- select product_category,  sum(sales) as total_sales from KMS group by product_category order by product_category DESC
- The Technology product_category had the highest number of sales with total_sales of 5.9 million 

### Q2. What are the top 3 and bottom 3 regions in terms of sales?

### Q2a. what are the top 3 regions in terms of sales?

 - select regions, sum(sales) as total_sales from KMS group by region
order by total_sales  DESC
- executing the codes above we have, The west region being the highest, then Ontario and Prarie, these are the top 3 regions in terms of sales.

### Q2b. The bottom 3 regions in terms of sales?
 - select regions, sum(sales) as total_sales from KMS group by region
order by total_sales  ASC

- output: the Bottom 3 regions interms of sales are Nunavut which had the least sales, then northwest Territories and Yukon respectively.

### Q3. What were the total sales of appliances in Ontario?

 - select region, product_sub_category, sum(sales) as total_sales_of_appliances from KMS, where products_sub_category='appliances' and region='Ontario', group by region, product_sub_category
 - executing this, we have the total sales of appliances in Ontario = 202,346.6
