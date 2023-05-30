## Lesson 2: 

# Single-Row Subqueries

## i. Definition and Usage of Single-Row Subqueries:
   - Single-row subqueries are used to retrieve a single value or a single row of data from a subquery. They are nested queries that return only one row as the result.
   - Discuss scenarios where single-row subqueries are commonly used, such as retrieving specific information, calculating derived values, or making comparisons.

## ii. Retrieving a Single Value using Subqueries:
   - Demonstrate how to retrieve a single value using a subquery.
   - Explain the syntax of single-row subqueries and their placement in SQL statements.
   - Provide examples of selecting a specific value based on a condition using subqueries.

### Example:

Consider a table called "orders" that stores order information.

Table: orders
| order_id | customer_id | total_amount |
|----------|-------------|--------------|
| 1        | 100         | 150.50       |
| 2        | 200         | 75.00        |
| 3        | 300         | 200.20       |

```sql
SELECT order_id, total_amount
FROM orders
WHERE total_amount = (SELECT MAX(total_amount) FROM orders);
```

Output:
| order_id | total_amount |
|----------|--------------|
| 3        | 200.20       |

## iii. Writing Subqueries in WHERE, HAVING, and SELECT Clauses:
   - Show how to write subqueries in the WHERE clause to filter data.
   - Explain the usage of subqueries in the HAVING clause for conditional filtering.
   - Demonstrate incorporating subqueries in the SELECT clause to retrieve specific values.

### Example:

Consider a table called "products" that stores product information.

Table: products
| product_id | product_name | unit_price |
|------------|--------------|------------|
| 1          | Product A    | 10.00      |
| 2          | Product B    | 15.00      |
| 3          | Product C    | 20.00      |

```sql
SELECT product_name, unit_price
FROM products
WHERE unit_price > (SELECT AVG(unit_price) FROM products);
```

Output:
| product_name | unit_price |
|--------------|------------|
| Product B    | 15.00      |
| Product C    | 20.00      |

## iv. Handling NULL Values in Subqueries:
   - Discuss the impact of NULL values in subqueries.
   - Explain how to handle NULL values effectively using subqueries.
   - Provide examples of handling NULL values in different scenarios.

### Example:

Consider a table called "customers" that stores customer information.

Table: customers
| customer_id | customer_name | city       |
|-------------|---------------|------------|
| 1           | John Smith    | NULL       |
| 2           | Jane Doe      | New York   |
| 3           | Alex Johnson  | Los Angeles|

```sql
SELECT customer_name, city
FROM customers
WHERE city = (SELECT city FROM customers WHERE customer_name = 'John Smith');
```

Output:
| customer_name | city     |
|---------------|----------|
| John Smith    | NULL     |

In the above examples, single-row subqueries are used to retrieve a single value or a single row of data. They are written in different clauses such as WHERE, HAVING, and SELECT, depending on the requirement. The examples demonstrate the practical usage of single-row subqueries with real-world datasets and tables.

Please note that the provided SQL code can be executed in a database management system or SQL tool to generate the expected output tables.