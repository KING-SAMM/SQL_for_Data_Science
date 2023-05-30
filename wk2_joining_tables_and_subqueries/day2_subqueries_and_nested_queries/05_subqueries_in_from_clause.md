## Lesson 5: 

# Subqueries in FROM Clause (Derived Tables)

## i. Introduction to subqueries in the FROM clause:
   - Subqueries in the FROM clause, also known as derived tables, are subqueries that appear as a table within the main query. They allow you to create temporary result sets that can be treated as tables and used in complex queries. Derived tables provide a way to break down complex problems into smaller, more manageable parts.

## ii. Creating derived tables using subqueries:
   - Derived tables are created by placing a subquery within the FROM clause of the main query. The subquery generates a result set that is treated as a table, and the main query can reference and join the derived table with other tables as needed.

## iii. Applying derived tables in complex queries:
   - Derived tables are useful in complex queries where intermediate result sets or calculations are required. They can be used to filter, aggregate, or transform data before joining it with other tables or performing further analysis. Derived tables allow you to break down complex logic into smaller steps, making the overall query more readable and maintainable.

## iv. Advantages and use cases of derived tables:
   - Derived tables provide several advantages, including:
     - Simplifying complex queries by breaking them down into smaller, logical steps.
     - Improving query performance by reducing the amount of data processed in each step.
     - Enabling the use of aggregate functions and grouping within the derived table.
     - Supporting complex filtering and conditional logic.
   - Use cases for derived tables include generating summary reports, performing calculations, filtering data based on specific conditions, and combining data from multiple sources.

## Resources:
- Text resource: [Derived Tables in SQL](https://www.sqlshack.com/derived-tables-in-sql-server/)
- Video resource: [Using Derived Tables in SQL](https://www.youtube.com/watch?v=YPgAVU2Qf8Q)

### Example with real-world datasets and tables:

Consider two tables, "orders" and "customers," with the following structures:

Table: orders
| order_id | customer_id | order_date | total_amount |
|----------|-------------|------------|--------------|
| 1        | 101         | 2022-01-01 | 1000         |
| 2        | 102         | 2022-02-01 | 2000         |
| 3        | 101         | 2022-03-01 | 1500         |
| 4        | 103         | 2022-04-01 | 500          |

Table: customers
| customer_id | customer_name | city     |
|-------------|---------------|----------|
| 101         | John Smith    | New York |
| 102         | Jane Doe      | Boston   |
| 103         | Alex Johnson  | Chicago  |

Example: Retrieve the total order amount for each customer and display the results as a derived table.

```sql
SELECT c.customer_name, dt.total_order_amount
FROM customers c
JOIN (
    SELECT customer_id, SUM(total_amount) AS total_order_amount
    FROM orders
    GROUP BY customer_id
) AS dt ON c.customer_id = dt.customer_id;
```

Output:
| customer_name | total_order_amount |
|---------------|--------------------|
| John Smith    | 2500               |
| Jane Doe      | 2000               |
| Alex Johnson  | 500                |

In the above example, a derived table is created using a subquery within the FROM clause. The subquery calculates the total_order_amount by customer_id in the orders table. The main query then joins the derived table with the customers table based on the customer_id column, resulting in the desired output.

Note: The provided SQL code is just an example and may vary depending on the specific database system and table structures.

Additional resources for Lesson 5:

- Text resource: [Using Derived Tables in SQL](https://www.sqlservertutorial.net/sql-server-basics/sql-server-derived-table/)
- Video resource: [Derived Tables in SQL](https://www.youtube.com/watch?v=4gxdQKpxQ3M)

By studying the concepts and examples covered in Lesson 5, you will gain a solid understanding of subqueries in the FROM clause and how to create and utilize derived tables. Remember to practice writing and executing queries with derived tables using various scenarios to strengthen your skills.

Feel free to explore the provided resources for more in-depth explanations and examples to enhance your learning experience.