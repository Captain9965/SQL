# SQL SELECT:
This is used to retrieve data from a database table eg:
```
    SELECT first_name, last_name FROM <table name>

```
To select ALL, use `*`

## SELECT WHERE Clause:

The `SELECT` statement can have an optional `WHERE` clause that that allows us to fetch a record matching a specific condition. eg.

```
SELECT *
FROM Customers
WHERE last_name = 'Lenny';
```
**N/B: Do not use ""**

## SQL operators:
Whe have the usual conditional and logical operators: ` = , <, AND, OR, NOT, `

## SELECT DISTINCT statement:
It selects unique rows from a database table.
```
SELECT DISTINCT first_name FROM <table name>;
```
## DISTINCT with COUNT:
To get the number of distinct rows, we can use `COUNT()` function with `DISTINCT`
```
SELECT COUNT(DISTINCT first_name) FROM <table name>;
```

## SELECT AS alias:
The `AS` keyword is used to give a column a temporary name that can be used to identify the table later in the result set.

```
SELECT first_name AS fn FROM <table name>
```
One can also use aliases with more than one column:

```
SELECT customer_id AS cid, first_name AS name
FROM <table name>;
```
## SELECT AS with an expression:

