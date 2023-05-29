## Weekly Assessment: 

# Joining Tables and Subquery Exercises

### Exercise 1: Write a query to join two tables using an inner join and retrieve specific columns from both tables.

Consider the following two tables:

Table: orders
| order_id | customer_id | product_name |
|----------|-------------|--------------|
| 1        | 101         | Laptop       |
| 2        | 102         | Smartphone   |
| 3        | 103         | Tablet       |

Table: customers
| customer_id | customer_name | city      |
|-------------|---------------|-----------|
| 101         | John Smith    | New York  |
| 102         | Jane Doe      | London    |
| 103         | Alex Johnson  | Sydney    |

Write a query to join the "orders" and "customers" tables using an inner join and retrieve the order ID, customer name, and product name.

```sql
SELECT o.order_id, c.customer_name, o.product_name
FROM orders AS o
JOIN customers AS c ON o.customer_id = c.customer_id;
```

The query combines the two tables using the inner join condition, where the "customer_id" column in the "orders" table matches the "customer_id" column in the "customers" table. The SELECT statement specifies the desired columns to be retrieved.

Output:
| order_id | customer_name | product_name |
|----------|---------------|--------------|
| 1        | John Smith    | Laptop       |
| 2        | Jane Doe      | Smartphone   |
| 3        | Alex Johnson  | Tablet       |

Explanation:
The query retrieves the order ID, customer name, and product name by joining the "orders" and "customers" tables on the "customer_id" column. It combines the related rows from both tables based on the matching values in the "customer_id" column, resulting in the desired output.

### Exercise 2: Perform a left outer join between two tables and retrieve matching records from one table.

Consider the following two tables:

Table: products
| product_id | product_name | category   |
|------------|--------------|------------|
| 1          | Laptop       | Electronics|
| 2          | Smartphone   | Electronics|
| 3          | Tablet       | Electronics|

Table: sales
| product_id | quantity | price |
|------------|----------|-------|
| 1          | 10       | 1000  |
| 3          | 5        | 800   |
| 4          | 8        | 500   |

Write a query to perform a left outer join between the "products" and "sales" tables and retrieve the product ID, product name, quantity, and price.

```sql
SELECT p.product_id, p.product_name, s.quantity, s.price
FROM products AS p
LEFT JOIN sales AS s ON p.product_id = s.product_id;
```

The query combines the two tables using a left outer join, where all rows from the "products" table are included, and only matching rows from the "sales" table are retrieved based on the "product_id" column.

Output:
| product_id | product_name | quantity | price |
|------------|--------------|----------|-------|
| 1          | Laptop       | 10       | 1000  |
| 2          | Smartphone   | NULL     | NULL  |
| 3          | Tablet       | 5        | 800   |

Explanation:
The left outer join retrieves all rows from the "products" table and includes the matching rows from the "sales" table based on the "product_id" column. In cases where there is no match, NULL values are populated for the columns from the "sales" table.


### Exercise 3: Write a query that includes a self-join to retrieve related information from a single table.

Consider the following table:

Table: employees
| employee_id | employee_name | manager_id |
|-------------|---------------|------------|
| 1           | John Smith    | 3          |
| 2           | Jane Doe      | 3          |
| 3           | Alex Johnson  | 4          |
| 4           | Emily Brown   | NULL       |

Write a query that includes a self-join to retrieve the employee name and their respective manager's name.

```sql
SELECT e.employee_name, m.employee_name AS manager_name
FROM employees AS e
JOIN employees AS m ON e.manager_id = m.employee_id;
```

The query performs a self-join on the "employees" table, where the "manager_id" column in the "e" alias matches the "employee_id" column in the "m" alias. It retrieves the employee name from the "e" alias and the manager's name from the "m" alias.

Output:
| employee_name | manager_name  |
|---------------|---------------|
| John Smith    | Alex Johnson  |
| Jane Doe      | Alex Johnson  |
| Alex Johnson  | Emily Brown   |

Explanation:
The self-join allows us to match the employees with their respective managers within the same table. By joining the "employees" table with itself using the "manager_id" and "employee_id" columns, we retrieve the employee name and their corresponding manager's name. In the output, each row displays an employee's name and their manager's name.

