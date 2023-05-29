### Lesson 4 
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

```sql
SELECT * 
FROM customers;
```

---

Retrieve specific columns from a single table:

```sql
SELECT customer_name, customer_email
FROM customers;
```

---

Retrieve data based on a condition using WHERE:

```sql
SELECT * 
FROM orders
WHERE order_date > '2022-01-01';
```

---

Retrieve data from multiple tables using JOIN:

```sql
SELECT customers.customer_name, orders.order_date
FROM customers
JOIN orders
ON customers.customer_id = orders.customer_id;
```

---

Sort data in ascending order using ORDER BY:

```sql
SELECT *
FROM products
ORDER BY product_name ASC;
```

---

Limit the number of rows returned using LIMIT:

```sql
SELECT *
FROM orders
LIMIT 10;
```

---

Count the number of rows that meet a condition using COUNT:

```sql
SELECT COUNT(*)
FROM orders
WHERE order_date > '2022-01-01';
```




