## Lesson 4: 

# Correlated Subqueries

## i. Understanding correlated subqueries and their purpose:
   - Correlated subqueries are subqueries that depend on the values from the outer query. Unlike regular subqueries, which can be executed independently, correlated subqueries are evaluated for each row of the outer query. They are used to retrieve data from related tables or apply complex conditions that require referencing the outer query.

## ii. Identifying the relationship between the main query and subquery:
   - Correlated subqueries establish a relationship between the main query and the subquery through column references. The subquery references columns from the outer query, allowing the subquery to be evaluated for each row in the outer query's result set.

## iii. Using correlated subqueries for row-by-row processing:
   - Correlated subqueries are useful for performing row-by-row processing or applying conditions based on data from other rows. By referencing the outer query's columns, the subquery can dynamically adjust its results based on the values of each row in the outer query.

## iv. Performance considerations for correlated subqueries:
   - Correlated subqueries can have performance implications as they are executed for each row of the outer query. It is important to optimize correlated subqueries by ensuring proper indexing, limiting the number of rows accessed, and using appropriate join conditions to minimize the impact on query execution time.


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

Example: Retrieve customers who have placed orders with a total amount higher than the average total amount of all orders.

```sql
SELECT customer_name
FROM customers c
WHERE EXISTS (
    SELECT 1
    FROM orders o
    WHERE o.customer_id = c.customer_id
    AND o.total_amount > (
        SELECT AVG(total_amount)
        FROM orders
    )
);
```

Output:
| customer_name |
|---------------|
| John Smith    |
| Jane Doe      |
| Alex Johnson  |

In the above example, the correlated subquery is used to compare the total_amount of each customer's order with the average total_amount of all orders. The subquery is correlated with the outer query's customer_id, allowing the condition to be evaluated for each customer. The EXISTS operator is used to check if there is at least one matching order for each customer.

Note: The provided SQL code and example are for illustrative purposes. Make sure to adjust the queries based on your specific database schema and requirements.


## Resources:
- Text resource: [Correlated Subqueries in SQL](https://www.sqlshack.com/correlated-subqueries-in-sql-server/)
- Video resource: [Correlated Subqueries in SQL](https://www.youtube.com/watch?v=U70O0oGmhy0)