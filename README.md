# Window_Function_PostgreSQL

PostgreSQL Window Functions – Product Analysis

This project demonstrates the use of PostgreSQL Window Functions to analyze product data.
It includes ranking products by price and calculating cumulative totals within each category.

Dataset Structure

The products table contains the following columns:

Column Name	Description
product_name	Name of the product
category	Category to which the product belongs
price	Price of the product
SQL Queries and Explanation
Task	SQL Query	Description
View All Products	sql SELECT * FROM products;	Retrieves all records from the products table to inspect the dataset.
Rank Products by Price (Category-wise)	sql SELECT product_name, category, price, DENSE_RANK() OVER (PARTITION BY category ORDER BY price DESC) AS ranking FROM products;	Assigns a ranking to each product within the same category based on price. The highest-priced product receives rank 1. DENSE_RANK() ensures ranks are not skipped when prices are tied.
Calculate Running Total of Prices	sql SELECT product_name, category, price, SUM(price) OVER (PARTITION BY category ORDER BY price ASC) AS running_total FROM products;	Computes a cumulative total of product prices within each category. The total increases as the query moves from the lowest price to the highest price in the category.
Key SQL Concepts Used

Window Functions

DENSE_RANK()

SUM() OVER()

PARTITION BY

ORDER BY

Cumulative Aggregation
