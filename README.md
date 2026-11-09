#Task 3: SQL for Data Analysis
Objective
Use SQL queries to extract, join, summarize, and analyze ecommerce data.
Tools
SQLite 3 (also adaptable to MySQL/PostgreSQL)
DB Browser for SQLite, SQLiteStudio, or Python's built-in sqlite3
Dataset
This project contains a small sample ecommerce database with four tables:
customers – customer details
products – product names, categories, and prices
orders – order dates and statuses
order_items – products and quantities in each order
Project files
Task_3_SQL_for_Data_Analysis/
├── task3_sql_analysis.sql   # Complete schema, sample data, and analysis queries
├── README.md               # Project guide
├── data/
│   └── ecommerce_sample_data.csv
└── outputs/
    ├── query_outputs.txt   # Results of the analysis queries
    ├── customer_revenue.csv
    └── category_revenue.csv
How to run
Install DB Browser for SQLite, SQLiteStudio, or use Python.
Open a new SQLite database.
Open task3_sql_analysis.sql and execute the full script. It creates the tables, inserts sample data, creates indexes, and runs the analysis queries.
View the query results in the SQL tool.
The outputs/ folder contains example results generated from the same sample data.
Run using Python
import sqlite3

connection = sqlite3.connect("ecommerce.db")
with open("task3_sql_analysis.sql", "r", encoding="utf-8") as file:
    connection.executescript(file.read())

print("Database created and SQL script executed successfully.")
connection.close()
SQL concepts covered
SELECT, WHERE, ORDER BY
INNER JOIN and LEFT JOIN (SQLite equivalent approach for a RIGHT JOIN use case)
GROUP BY, HAVING
SUM(), AVG(), COUNT()
Subqueries
Views
Indexes and EXPLAIN QUERY PLAN
NULL handling with COALESCE()
Notes
SQLite does not support RIGHT JOIN in older versions. The project demonstrates the same result using a LEFT JOIN with the tables reversed.
Revenue is calculated as quantity * unit_price.
Average revenue per user is calculated using customers who placed at least one order. task-3