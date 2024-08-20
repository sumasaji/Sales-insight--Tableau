?? Sales Insights Data Analysis Project
Welcome to the Sales Insights Data Analysis Project! This repository contains SQL-based data analysis and visualizations to extract valuable insights from sales data.
?? Project Overview
In this project, we:
* Set up MySQL on your local machine.
* Import a sales database.
* Perform SQL queries to extract insights.
* Visualize total revenue, sales by market, top products, and more.
??? Setup MySQL
1. Install MySQL: Follow the steps in this video tutorial to install MySQL on your local computer.
2. Import Database: Download the “db_dump.sql” file from this repository and import it as per the tutorial instructions.
?? SQL Queries for Data Analysis
* ?? Customer Data:

o Show all customer records:
SELECT * FROM customers;
o Show total number of customers:
SELECT COUNT(*) FROM customers;

* ?? Transaction Data:
o Show transactions for Chennai (market code: Mark001):
SELECT * FROM transactions WHERE market_code='Mark001';


o Show transactions in US dollars:
SELECT * FROM transactions WHERE currency="USD";


* ?? Date-Based Analysis:
* 
o Show transactions from the year 2020:
SELECT transactions.*, date.* FROM transactions
INNER JOIN date ON transactions.order_date=date.date
WHERE date.year=2020;

o Calculate total revenue for 2020:
o 
SELECT SUM(transactions.sales_amount) FROM transactions
INNER JOIN date ON transactions.order_date=date.date
WHERE date.year=2020;

o Calculate total revenue for January 2020:

SELECT SUM(transactions.sales_amount) FROM transactions
INNER JOIN date ON transactions.order_date=date.date
WHERE date.year=2020 AND date.month_name="January";

o Calculate total revenue for 2020 in Chennai:

SELECT SUM(transactions.sales_amount) FROM transactions
INNER JOIN date ON transactions.order_date=date.date
WHERE date.year=2020 AND transactions.market_code="Mark001";



?? ETL Process
The ETL process involves:
1. Extract: Data is sourced from the database (db_dump.sql) containing tables such as customers, transactions, and date.
2. Transform:
o Clean the data by handling missing values and duplicates.
o Convert currencies where necessary.
o Join transactions with the date table for time-based analysis.
3. Load: The transformed data is loaded into MySQL for querying and analysis.
You can use the db_dump.sql file to set up the initial database.


?? Visualizations

Here are the charts that showcase the insights we derived from the data:
* ?? Total Metrics:
o Total Revenue
o Total Quantity

* ?? Bar Charts:
o Sales by Market
o Revenue by Market

* ?? Line Chart:
o Revenue by Year

* ?? Column Charts:
o Top 5 Products
o Top 5 Customers

Key Insights:
* The Chennai market contributed significantly to overall sales.
* The top 5 products drove a large portion of the revenue.
* There was a noticeable revenue spike in certain months, particularly during January 2020






