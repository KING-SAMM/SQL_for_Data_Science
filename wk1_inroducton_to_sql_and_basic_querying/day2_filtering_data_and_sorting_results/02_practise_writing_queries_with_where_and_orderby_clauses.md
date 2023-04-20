Lesson 2: Practice Writing Queries with WHERE and ORDER BY Clauses

i. Using the WHERE clause to filter data based on specific criteria:

Example 1: Selecting all customers from a customer table with a specific last name:

`SELECT * FROM customer WHERE last_name = 'Smith';`

Example 2: Selecting all products from a product table with a price less than a certain value:

`SELECT * FROM product WHERE price < 50;`

ii. Sorting query results with ORDER BY:

Example 1: Sorting customers from a customer table by last name in ascending order:

`SELECT * FROM customer ORDER BY last_name ASC;`

Example 2: Sorting products from a product table by price in descending order:

`SELECT * FROM product ORDER BY price DESC;`
iii. Sorting by multiple columns:

Example 1: Sorting customers from a customer table by last name in ascending order, then by first name in ascending order:

`SELECT * FROM customer ORDER BY last_name ASC, first_name ASC;`

Example 2: Sorting products from a product table by category in ascending order, then by price in descending order:

`SELECT * FROM product ORDER BY category ASC, price DESC;`


iv. Using the DESC keyword to sort in descending order:

Example 1: Sorting customers from a customer table by last name in descending order:

`SELECT * FROM customer ORDER BY last_name DESC;`

Example 2: Sorting products from a product table by price in descending order:

`SELECT * FROM product ORDER BY price DESC;`


