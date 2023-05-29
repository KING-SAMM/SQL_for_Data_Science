## Lesson 3: 

# Outer Join

## i. Definition of outer joins, including left outer join, right outer join, and full outer join:
   - Outer joins are used to combine data from two or more tables, including non-matching rows, in addition to matching rows. There are three types of outer joins:
     1. Left Outer Join: Retrieves all rows from the left (or first) table and the matching rows from the right (or second) table. If there are no matching rows in the right table, NULL values are included for the columns of the right table.
     2. Right Outer Join: Retrieves all rows from the right table and the matching rows from the left table. If there are no matching rows in the left table, NULL values are included for the columns of the left table.
     3. Full Outer Join: Retrieves all rows from both tables, including matching and non-matching rows. If there are no matching rows, NULL values are included for the columns of the respective tables.

## ii. Syntax of the LEFT JOIN, RIGHT JOIN, and FULL JOIN clauses:
   - The syntax of the outer join clauses is as follows:
     ```sql
     SELECT columns
     FROM table1
     LEFT JOIN table2 ON table1.column = table2.column;

     SELECT columns
     FROM table1
     RIGHT JOIN table2 ON table1.column = table2.column;

     SELECT columns
     FROM table1
     FULL JOIN table2 ON table1.column = table2.column;
     ```
     The LEFT JOIN, RIGHT JOIN, and FULL JOIN clauses specify the type of outer join to perform. The columns listed after the SELECT keyword represent the desired output columns from the joined tables.

## iii. Comparison between outer joins and inner joins:
   - Outer joins include non-matching rows in the result, while inner joins exclude non-matching rows. Outer joins allow us to retrieve data even when there are no matching values between the tables, while inner joins require matching values in both tables to retrieve the data.

### Handling NULL values in outer join results:
   - In outer join results, NULL values are included for columns that do not have matching values. It is important to handle NULL values appropriately in the result set to avoid potential errors or incorrect analysis. This can be done using functions like ISNULL(), COALESCE(), or CASE statements to provide meaningful values or perform specific actions when encountering NULL values.

### Examples with real-world datasets and tables:

Consider two tables, "customers" and "orders", that store customer information and order details, respectively.

Table: customers
| customer_id | customer_name | city     |
|-------------|---------------|----------|
| 1           | John Smith    | Lagos    |
| 2           | Jane Doe      | Abuja    |
| 3           | Alex Johnson  | Lagos    |

Table: orders
| order_id | customer_id | product_name |
|----------|-------------|--------------|
| 1        | 1           | Laptop       |
| 2        | 2           | Smartphone   |
| 3        | 4           | Tablet       |

Example 1: Retrieve customer names and their corresponding order details using a left outer join.

```sql
SELECT c.customer_name, o.product_name
FROM customers AS c
LEFT JOIN orders AS o ON c.customer_id = o.customer_id;
```

Output:
| customer_name | product_name |
|---------------|--------------|
| John Smith    | Laptop       |
| Jane Doe      | Smartphone   |
| Alex Johnson  | NULL         |

Example 2: Retrieve order details and the corresponding customer names using a right outer join.

```sql
SELECT c.customer_name, o.product_name
FROM customers AS c
RIGHT JOIN orders AS o ON c.customer_id = o.customer_id;
```

Output:
| customer_name | product_name |
|---------------|--------------|
| John Smith    | Laptop       |
| Jane Doe      | Smartphone   |
| NULL          | Tablet       |

Example 3: Retrieve all customer names and order details using a full outer join.

```sql
SELECT c.customer_name, o.product_name
FROM customers AS c
FULL JOIN orders AS o ON c.customer_id = o.customer_id;
```

Output:
| customer_name | product_name |
|---------------|--------------|
| John Smith    | Laptop       |
| Jane Doe      | Smartphone   |
| Alex Johnson  | NULL         |
| NULL          | Tablet       |

### Handling NULL values: To handle NULL values, you can use the ISNULL() function to replace NULL values with a specified value. For example:

```sql
SELECT c.customer_name, ISNULL(o.product_name, 'No Order') AS product_name
FROM customers AS c
LEFT JOIN orders AS o ON c.customer_id = o.customer_id;
```

Output:
| customer_name | product_name |
|---------------|--------------|
| John Smith    | Laptop       |
| Jane Doe      | Smartphone   |
| Alex Johnson  | No Order     |

In the above example, the ISNULL() function replaces NULL values in the "product_name" column with 'No Order'. This provides a more meaningful representation of the data when NULL values are encountered.