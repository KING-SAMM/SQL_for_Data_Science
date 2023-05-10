# Lesson 4 
# Basic SQL Syntax

## SQL keywords: SELECT, FROM, WHERE

***SELECT***: used to specify the columns that you want to retrieve from a table

***FROM***: used to specify the table or tables from which to retrieve data

***WHERE***: used to specify the conditions that must be met for a row to be returned

## Data types: integer, float, text, date/time

**Integer**: a whole number without a decimal point

**Float**: a number with a decimal point

**Text**: a string of characters, such as a word or sentence

**Date/time**: a specific date or time value

## Writing basic queries:

Retrieve all data from a single table:

`SELECT * 
FROM customers;`

---

Retrieve specific columns from a single table:

`SELECT customer_name, customer_email`<br>
`FROM customers;`

---

Retrieve data based on a condition using WHERE:

`SELECT * `<br>
`FROM orders`<br>
`WHERE order_date > '2022-01-01';`

---

Retrieve data from multiple tables using JOIN:

`SELECT customers.customer_name, orders.order_date`<br> 
`FROM customers`<br> 
`JOIN orders`<br> 
`ON customers.customer_id = orders.customer_id;`

---

Sort data in ascending order using ORDER BY:

`SELECT *`<br>
`FROM products`<br>
`ORDER BY product_name ASC;`

---

Limit the number of rows returned using LIMIT:

`SELECT *`<br> 
`FROM orders`<br> 
`LIMIT 10;`

---

Count the number of rows that meet a condition using COUNT:

`SELECT COUNT(*)`<br>
`FROM orders`<br>
`WHERE order_date > '2022-01-01';`




