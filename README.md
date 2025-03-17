# Supply-chain-Analytics--Loginex-Company
I) PROJECT DESCRIPTION

The project provides a real-world dataset focusing on supply chain analytics. As the data analyst for Loginex, you will help solve key shipment and inventory management challenges, analyze supply chain inefficiencies, and create insightful dashboards to inform business stakeholders about potential problems and propose structural business improvements.

II) METHODOLOGY

Business demand analysis

Requirements: Create dashboard to analyze the business problem and improve the supply chain’s efficiency

Tool used: Python (Data preprocessing, data cleaning, EDA, inventory segmentation); Power BI (Dashboard)

Sales Manager: Overview and keep track of customer’s demand and product sales

=> Dashboard of overall business performance including sales, profit, orders, customers, best product,...

Inventory Manager: Control the inventory flow including order fulfillment, storing and distribution

=> Dashboard of inventory management including warehouse inventory, number of orders from customer, storing cost,...

Shipping Manager: Overseeing daily shipping and distribution operations to customers

=> Dashboard of shipping management including orders, location, timing, delay shipping,...

Overall target Create an interactive dashboard to summarize the research of the problem of the supply chain and suggest the solution

III) DATA PREPROCESSING

Data overview

The dataset provides three data tables including order_and_shipment, inventory and fulfillment. After examining the data fields, I noticed that the dataset generally represents the following key information

Customer: General information about customers including identifiers and addresses

Order: Information about the order including date of order, product and quantity ordered, order value

Shipment: Shipping information including shipping date, shipping mode

Product: Specific information about the ordered item including product name, product category, product department

Warehouse Inventory: Information on inventory management for each product name including monthly inventory, warehouse location, storage costs, order fulfillment

Data cleaning

Drop unnecessary columns (Order Item ID, Order Time)

Fix the datatype of the columns

Remove special characters in Customer Country column

Check for missing value

Check for duplicate value

Inconsistency of Product Name between order and inventory table: There are 5 product names that appear in the inventory table but not in the order table. This means that these are items that are in the company's inventory but have not been ordered by the customer. So it's impossible to dêtrmine which product category and product department those product names belong to. After investigating carefully, I decided to keep these product names as they account for a considerable amount of storage cost

Negative and unusual large shipping time: The Shipping Time = Shipment Date - Order Date has some negative values. Thís is due to the error in recording since the Shipment Date < Order Date. There are also unusually large values. Normally, in the United States, standard shipping within the same country might take anywhere from 2 to 7 business days. International standard shipping can take longer, often ranging from 1 to 4 weeks. I decided to take this information as a reference and drop the shipping time values that < 0 and > 28

Feature creation

Create Date time feature from day, month, year feature

Create Shipment feature to show which order is late or on time

Shipping Time = Shipment Date - Order Date

Delay Shipment = Late if Shipment Day - Schedule < Shipping Time and vice versa

Late Shipment Rate = Total of late order / Total number of order

Create Business performance feature
Net Sales = Gross sales - Discount * Gross sales

Unit Price = Gross sales / Order Quantity

Profit margin = Total Profit / Total Net sales

Storage cost = Inventory cost per unit * Warehouse inventory

IV) EXPLORATORY DATA ANALYSIS

In the EDA, I focus on analyzing the characteristics, behaviors, pattern and trends based on these criterions:

Questions:

Business Performance

What are the total net sales, profit and profit margin by the company?

What are the average net sales and profit per month?

How do the net sales and profit change over time?

How do the number of orders change over time?

How do the average order quantity and average unit price change over time?

Which product departments account for the majority of net sales and number of orders?

Customer

How was the distribution of customers by country and market?

How many customers does the company have over time?

Are there any patterns or trends of buying behavior over time?

Product

Which product categories and product names are most preferred?

Which product categories and product names are most profitable?

Inventory

Which product departments account for the majority of warehouse inventory and storage cost?

How is the inventory cost per unit distributed by the product department?

How do the warehouse inventory and storing costs change over time?

Which product names and product departments account for the majority of storing cost?

What is the average of the average fulfillment order?

What is the average order fulfillment of each product department?

Shipment

Which warehouses are orders shipped from?

Which shipment modes are preferred by customers?

What is the shipping time for each shipment mode?

What is the late shipment rate by product department and market?

How does the late shipment rate fluctuate over time?
