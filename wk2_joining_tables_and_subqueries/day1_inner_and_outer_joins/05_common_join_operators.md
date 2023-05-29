## Lesson 5: 

# Common Join Operators

## i. Equi-join: Explanation of equi-joins, which involve comparing columns with equal values:
   - Equi-joins are used to combine tables based on the equality of values in specified columns. It compares the values of the columns and retrieves the matching rows. The columns being compared are typically primary and foreign keys. Equi-joins are denoted using the equal (=) operator.
   
## ii. Non-equi join: Introduction to non-equi joins, where columns are compared with inequality operators:
   - Non-equi joins involve comparing columns with inequality operators such as less than (<), greater than (>), less than or equal to (<=), or greater than or equal to (>=). This type of join is useful when there is a need to retrieve rows based on specific conditions that are not based on equality.
   
## iii. Self-join: Understanding self-joins, where a table is joined with itself:
   - Self-joins occur when a table is joined with itself. This technique is used to retrieve related information within the same table. It involves aliasing the table with different names to differentiate between the joined instances. Self-joins are helpful when data has hierarchical or recursive relationships.
   
### Examples with real-world datasets and tables:

Consider a table called "employees" that stores employee information.

Table: employees
| employee_id | employee_name | manager_id | salary |
|-------------|---------------|------------|--------|
| 1           | John Smith    | 3          | 5000   |
| 2           | Jane Doe      | 3          | 4500   |
| 3           | Alex Johnson  | 4          | 6000   |
| 4           | Emily Brown   | NULL       | 7000   |

Example 1: Perform an equi-join to retrieve employees along with their respective manager names.

```sql
SELECT e.employee_name, m.employee_name AS manager_name
FROM employees AS e
JOIN employees AS m ON e.manager_id = m.employee_id;
```

Output:
| employee_name | manager_name  |
|---------------|---------------|
| John Smith    | Alex Johnson  |
| Jane Doe      | Alex Johnson  |
| Alex Johnson  | Emily Brown   |

Example 2: Use a non-equi join to retrieve employees with a higher salary than their managers.

```sql
SELECT e.employee_name, e.salary, m.employee_name AS manager_name, m.salary AS manager_salary
FROM employees AS e
JOIN employees AS m ON e.manager_id = m.employee_id AND e.salary > m.salary;
```

Output:
| employee_name | salary | manager_name  | manager_salary |
|---------------|--------|---------------|----------------|
| John Smith    | 5000   | Alex Johnson  | 6000           |
| Jane Doe      | 4500   | Alex Johnson  | 6000           |

Example 3: Perform a self-join to retrieve employees and their direct reports.

```sql
SELECT e.employee_name, e.salary, r.employee_name AS report_name, r.salary AS report_salary
FROM employees AS e
JOIN employees AS r ON e.employee_id = r.manager_id;
```

Output:
| employee_name | salary | report_name   | report_salary |
|---------------|--------|---------------|---------------|
| Alex Johnson  | 6000   | John Smith    | 5000          |
| Alex Johnson  | 6000   | Jane Doe      | 4500          |
| Emily Brown   | 7000   | Alex Johnson  | 6000          |

In the above examples, the equi-join is used to match employees with their respective managers based on the equality of the "manager_id" and "employee_id" columns. The non-equi join compares the salary of employees with the salary of their managers. The self-join allows the retrieval of employees and their direct reports by matching the "employee_id" with the "manager_id" within the same table.

These examples demonstrate how equi-joins, non-equi joins, and self-joins can be used to extract meaningful information from a dataset based on specific conditions and relationships within the data.