# Lesson 1 
# COMPARISON AND LOGICAL OPERATORS

## What are comparison operators?
Comparison operators are used in SQL to compare two values and evaluate whether they are equal or not, less than, greater than, less than or equal to, greater than or equal to, or not equal to.

## Common comparison operators: =, <, >, <=, >=, <>

`=`: checks if two values are equal.<br>
`<`: checks if the left-hand side value is less than the right-hand side value.<br>
`>`: checks if the left-hand side value is greater than the right-hand side value.<br>
`<=`: checks if the left-hand side value is less than or equal to the right-hand side value.<br>
`>=`: checks if the left-hand side value is greater than or equal to the right-hand side value.<br>
`<>`: checks if the two values are not equal.<br>

## What are logical operators?
Logical operators are used in SQL to combine two or more conditions and evaluate whether the combined conditions are true or false.

## Common logical operators: AND, OR, NOT

*AND*: combines two or more conditions and returns true if all of the conditions are true.

*OR*: combines two or more conditions and returns true if any of the conditions are true.

*NOT*: negates a condition and returns true if the condition is false.

## Using comparison and logical operators in WHERE clauses

To use comparison and logical operators in `WHERE` clauses, you can combine them to create more complex conditions that filter data based on specific criteria.

Example 1: Using the *=* operator in a `WHERE` clause to filter data

```sql
SELECT * FROM customers
WHERE country = 'USA';
```

This query retrieves all customers from the *customers* table whose country is *USA*.

Example 2: Using the *AND* operator in a `WHERE` clause to filter data

```sql
SELECT * FROM customers
WHERE country = 'USA' AND age >= 25;
```

This query retrieves all customers from the *customers* table whose country is *USA* and age is greater than or equal to 25.

Example 3: Using the *OR* operator in a `WHERE` clause to filter data

```sql
SELECT * FROM customers
WHERE country = 'USA' OR country = 'Canada';
```

This query retrieves all customers from the *customers* table whose country is either *USA* or *Canada*.

Example 4: Using the *NOT* operator in a `WHERE` clause to filter data

```sql
SELECT * FROM customers
WHERE NOT country = 'USA';
```

This query retrieves all customers from the *customers* table whose country is not *USA*.





