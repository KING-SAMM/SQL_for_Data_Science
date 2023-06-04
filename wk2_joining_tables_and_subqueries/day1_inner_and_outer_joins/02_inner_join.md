### Lessin 2

# Inner Join

![Inner Join](https://sqlfordatascience.com.ng/img/week2/inner-join.png "Inner join")

## i. Definition of an inner join and its purpose in combining data from multiple tables:
   - An inner join is a type of join operation that combines data from two or more tables based on a common column or columns. It retrieves only the rows that have matching values in both tables, excluding non-matching rows. The purpose of an inner join is to retrieve related data from multiple tables, allowing us to analyze and connect information across different datasets.

## ii. Syntax of the INNER JOIN clause and its usage in queries:
   - The syntax of the INNER JOIN clause is as follows:
     ```sql
     SELECT columns
     FROM table1
     INNER JOIN table2 ON table1.column = table2.column;
     ```
     The INNER JOIN clause specifies the two tables to be joined and the column(s) on which the join is based. The columns listed after the SELECT keyword represent the desired output columns from the joined tables.

## iii. Explanation of the matching criteria in an inner join:
   - The matching criteria in an inner join is defined by the condition specified in the ON clause. It determines how the tables are connected and which rows should be included in the result. The columns used in the ON clause are typically related between the tables, such as primary keys and foreign keys. The join operation matches the values of these columns, returning only the rows where the values match.

### Use of table aliases to simplify query writing:
   - Table aliases provide shorthand names for tables in a query, making the query more readable and reducing typing effort. They are especially useful when working with long table names or when joining multiple tables. Table aliases are assigned using the AS keyword or by directly assigning a short name to the table name.
   
   Example:
   ```sql
   SELECT t1.column1, t2.column2
   FROM table1 AS t1
   INNER JOIN table2 AS t2 ON t1.column = t2.column;
   ```
   In the above example, "t1" and "t2" are table aliases for table1 and table2, respectively. They are used to reference the columns from each table in the SELECT clause and the ON clause, simplifying the query structure.

### Examples with real-world datasets and tables:

Consider two tables, "employees" and "departments", that store employee information and department details, respectively.

Table: employees
| employee_id | employee_name | department_id |
|-------------|---------------|---------------|
| 1           | John Smith    | 1             |
| 2           | Jane Doe      | 2             |
| 3           | Alex Johnson  | 1             |

Table: departments
| department_id | department_name |
|---------------|-----------------|
| 1             | Sales           |
| 2             | Marketing       |

Example 1: Retrieve employee names and their corresponding department names using an inner join.

```sql
SELECT e.employee_name, d.department_name
FROM employees AS e
INNER JOIN departments AS d ON e.department_id = d.department_id;
```

Output:
| employee_name | department_name |
|---------------|-----------------|
| John Smith    | Sales           |
| Jane Doe      | Marketing       |
| Alex Johnson  | Sales           |

Example 2: Retrieve employee names and their department names along with the employee ID.

```sql
SELECT e.employee_id, e.employee_name, d.department_name
FROM employees AS e
INNER JOIN departments AS d ON e.department_id = d.department_id;
```

Output:
| employee_id | employee_name | department_name |
|-------------|---------------|-----------------|
| 1           | John Smith    | Sales           |
| 2           | Jane Doe      | Marketing       |
| 3           | Alex Johnson  | Sales           |
