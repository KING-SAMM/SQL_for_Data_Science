## Lesson 3: 

# Multiple-Row Subqueries

## i. Definition and Usage of Multiple-Row Subqueries:
   - Multiple-row subqueries are nested queries that return multiple rows as the result. They are used when a subquery needs to compare a value against a set of values.
   - Explain the purpose and scenarios where multiple-row subqueries are commonly used, such as filtering data based on a set of conditions or retrieving matching rows from another table.

## ii. Using Subqueries to Compare a Value Against a Set of Values:
   - Demonstrate how to use multiple-row subqueries to compare a value against a set of values.
   - Provide examples of using the IN operator to match values from a subquery with values in the main query.

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
WHERE customer_id IN (SELECT customer_id FROM customers WHERE city = 'New York');
```

Output:
| order_id | total_amount |
|----------|--------------|
| 2        | 75.00        |

## iii. Applying Subqueries with IN, ANY, and ALL Operators:
   - Explain the usage of the IN, ANY, and ALL operators in multiple-row subqueries.
   - Provide examples of using the ANY and ALL operators to compare values with a subquery.

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
WHERE unit_price > ANY (SELECT unit_price FROM products WHERE product_name = 'Product A');
```

Output:
| product_name | unit_price |
|--------------|------------|
| Product B    | 15.00      |
| Product C    | 20.00      |

## iv. Understanding the EXISTS and NOT EXISTS Operators:
   - Explain the purpose and usage of the EXISTS and NOT EXISTS operators in multiple-row subqueries.
   - Demonstrate how to use EXISTS and NOT EXISTS to check for the existence of rows in a subquery.

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
FROM customers c
WHERE EXISTS (SELECT * FROM orders o WHERE o.customer_id = c.customer_id);
```

Output:
| customer_name | city     |
|---------------|----------|
| Jane Doe      | New York |
| Alex Johnson  | Los Angeles |

For further learning resources, you can refer to the following:

- Text Resource: [Multiple-Row Subqueries - SQL Tutorial](https://www.sqltutorial.org/sql-subquery/multiple-row-subqueries/)
- Video Resource: [Multiple-Row Subqueries - Oracle Database](https://www.youtube.com/watch?v=H4nRmgnHhOQ)

Please note that the provided SQL code can be executed in a database management system or in an SQL editor to retrieve the desired results. Make sure to have access to the relevant dataset or create sample tables to practice and experiment with the queries.