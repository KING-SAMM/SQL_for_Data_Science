Lesson 4. BASIC SQL SYNTAX

i. SQL Keywords: SELECT, FROM, WHERE

SELECT: used to specify the columns that you want to retrieve from a table

FROM: used to specify the table or tables from which to retrieve data

WHERE: used to specify the conditions that must be met for a row to be returned

ii. Data Types: integer, float, text, date/time

Integer: a whole number without a decimal point
Float: a number with a decimal point
Text: a string of characters, such as a word or sentence
Date/time: a specific date or time value

iii. Examples of Writing Basic Queries:

Retrieve all data from a single table:

SELECT * 
FROM customers;

Retrieve specific columns from a single table:

SELECT customer_name, customer_email 
FROM customers;

Retrieve data based on a condition using WHERE:

SELECT * 
FROM orders 
WHERE order_date > '2022-01-01';

Retrieve data from multiple tables using JOIN:

SELECT customers.customer_name, orders.order_date 
FROM customers 
JOIN orders 
ON customers.customer_id = orders.customer_id;

Sort data in ascending order using ORDER BY:

SELECT * 
FROM products 
ORDER BY product_name ASC;

Limit the number of rows returned using LIMIT:

SELECT * 
FROM orders 
LIMIT 10;

Count the number of rows that meet a condition using COUNT:

SELECT COUNT(*) 
FROM orders 
WHERE order_date > '2022-01-01';




