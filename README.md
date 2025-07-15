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
  
- select product_category,  sum(sales) as total_sales from KMS group by product_category order by total_sales DESC
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

### Q4. Advising the KMS management on what to do, in order to increase revenue.

 - select customer_Name, Product_category, region, ship_mode, Sum(sales) as total_sales from KMS group by Customer_Name, Product_category, region, Ship_Mode order by total_sales ASC
- Executing the above query, gives us an overview of the 10 bottom customer to identify trends in the kind of products they purchase and the shipping methods used.
-#### Base on the data, the bottom 10 customers purchases products mostly within the office supplies category, and few furniture and all ship mode used were, the Regular Air ship mode, which is relatively high in cost.

 - I will Advice that the sales team should enhance customer relationships with these customers, and come up with market strategies to upscale sales.
   
 - The bottom 10 customers didn't purchase products in the technology category which is a high revenue generating products, this could probably be due to lack of awareness about the use and benefits of the product. sale team can introduce and encourage the 10 bottom customers on the use and benefits of technology products
   
 - suggest and encourage the use of other ship_mode with less cost to the customers, to cut down cost on KMS.
   
 - Introduce value added services and incentives to encourage the customers to make more purchases

 - Conduct a customer feedback survey to get customers views on their satisfaction with KMS products and services, And possible areas of improvement to better meet customers needs.

### Q5. KMS incurred the most shipping cost using which shipping method?

 - The KMS incurred the most shipping cost using the Delivery Truck which cost 51,971.9.

### For SQL Queries used [click here](https://docs.google.com/document/d/1Jf_n9xeL3N0pjz5xWDDbzDjFuP3hpdLY/edit?usp=drivesdk&ouid=106287249642968225191&rtpof=true&sd=true)

