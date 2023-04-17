# SQL_CHEATSHEET
SELECT
The SELECT statement is used to retrieve data from one or more tables in a database.

```
SELECT column_name1, column_name2, ...
FROM table_name;
```
Example:

```
SELECT * FROM customers;
This will retrieve all columns from the customers table.
```

WHERE
The WHERE clause is used to filter records based on a specified condition.

```
SELECT column_name1, column_name2, ...
FROM table_name
WHERE condition;
```
Example:
```
SELECT * FROM customers WHERE city = 'New York';
This will retrieve all customers from New York.
```

ORDER BY
The ORDER BY clause is used to sort the result set in ascending or descending order.
```
SELECT column_name1, column_name2, ...
FROM table_name
ORDER BY column_name [ASC|DESC];
```
Example:

```
SELECT * FROM customers ORDER BY last_name ASC;
This will retrieve all customers sorted by last name in ascending order.
```

JOIN
The JOIN clause is used to combine rows from two or more tables based on a related column between them.
```
SELECT column_name1, column_name2, ...
FROM table_name1
JOIN table_name2
ON table_name1.column_name = table_name2.column_name;
```
Example:

```
SELECT customers.first_name, orders.order_date
FROM customers
JOIN orders
ON customers.customer_id = orders.customer_id;
This will retrieve the first name of customers who have placed an order and the date of the order.
```

GROUP BY
The GROUP BY clause is used to group rows based on a specified column and perform aggregate functions on them.

```
SELECT column_name1, COUNT(column_name2)
FROM table_name
GROUP BY column_name1;
```
Example:

```
SELECT city, COUNT(*)
FROM customers
GROUP BY city;
This will retrieve the number of customers in each city.
```

HAVING
The HAVING clause is used to filter the result set based on a condition that involves an aggregate function.

```
SELECT column_name1, COUNT(column_name2)
FROM table_name
GROUP BY column_name1
HAVING COUNT(column_name2) > value;
```
Example:
```
SELECT city, COUNT(*)
FROM customers
GROUP BY city
HAVING COUNT(*) > 2;
This will retrieve the cities with more than 2 customers.
```

INSERT INTO
The INSERT INTO statement is used to insert new rows into a table.
```
INSERT INTO table_name (column_name1, column_name2, ...)
VALUES (value1, value2, ...);
```
Example:

```
INSERT INTO customers (first_name, last_name, email)
VALUES ('John', 'Doe', 'john.doe@example.com');
This will insert a new customer with the specified values.
```

UPDATE
The UPDATE statement is used to modify existing rows in a table.

```
UPDATE table_name
SET column_name = value
WHERE condition;
```
Example:

```
UPDATE customers
SET city = 'Los Angeles'
WHERE customer_id = 1;
This will update the city of the customer with ID 1 to Los Angeles.
```

DELETE
The DELETE statement is used to delete existing rows from a table.

```
DELETE FROM table_name
WHERE condition;
```
Example:
```
DELETE FROM customers
WHERE customer_id = 1;
This will delete the customer with ID 1 from the customers table.
```
