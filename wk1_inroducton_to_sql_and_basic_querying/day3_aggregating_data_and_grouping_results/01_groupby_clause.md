# Lesson 1
# THE GROUP BY CLAUSE

## 1. Simple GROUP BY example
**Database**: Sales<br>
**Table**: Orders<br>
**Columns**: order_id, customer_id, order_date, total_amount

Rows:

| order_id	| customer_id |	order_date | total_amount |
|:----------|:-----------:|:----------:|:-------------|
|1	        |101	      |2022-01-01  |	100.00    |
|2	        |101          |2022-01-05  |    50.00     |
|3      	|102	      |2022-01-10  |    75.00     |
|4          |103          |2022-01-15  |    200.00    |


Query:

`SELECT customer_id, SUM(total_amount)
FROM Orders
GROUP BY customer_id;`


Output:

| customer_id | SUM(total_amount)|
|:-----------:|:----------------:|
|101          |    150.00        |
|102	      |    75.00         |
|103          |    200.00        |

---

2. GROUP BY with HAVING example
Database: Sales
Table: Orders
Columns: order_id, customer_id, order_date, total_amount


Rows:

order_id	customer_id	order_date	total_amount
1	101	2022-01-01	100.00
2	101	2022-01-05	50.00
3	102	2022-01-10	75.00
4	103	2022-01-15	200.00


Query:

SELECT customer_id, SUM(total_amount)
FROM Orders
GROUP BY customer_id
HAVING SUM(total_amount) > 100;


Output:

customer_id	SUM(total_amount)
103	200.00
101	150.00
---

3. GROUP BY with multiple columns example
Database: Sales
Table: Orders
Columns: order_id, customer_id, order_date, total_amount


Rows:

order_id	customer_id	order_date	total_amount
1	101	2022-01-01	100.00
2	101	2022-01-05	50.00
3	102	2022-01-10	75.00
4	103	2022-01-15	200.00
5	101	2022-01-20	75.00


Query:

SELECT customer_id, YEAR(order_date), SUM(total_amount)
FROM Orders
GROUP BY customer_id, YEAR(order_date);


Output:

customer_id	YEAR(order_date)	SUM(total_amount)
101	2022	225.00
102	2022	75.00
103	2022	200.00
