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
We can combine data from multiple columns and represent data in a single column using the `CONCAT()` function.

```
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM < table name>

```

## SELECT TOP:

`TOP` is used to select a fixed number of rows from a database. For example:
```
SELECT TOP 2 * FROM <table name> 
```
The `TOP` clause is not supported by all RDBMS:
- `TOP` is used by `SQL server, MS Access`
- `LIMIT` is used by `MySQL, PostgreSQL, SQLite`
- 'FETCH FIRST' is used by `Oracle`

## SELECT LIMIT:
`TOP` for the DBMS listed above.
```
SELECT first_name, last_name FROM <table name> LIMIT 4
```

## SELECT with OFFSET clause:

`OFFSET` clause is used to specify the starting rows from where to select rows. 
```
SELECT first_name, last_name FROM <table name>  LIMIT 2 OFFSET 3;
```
The first 3 rows are excluded

## FETCH FIRST clause:
Used only in the Oracle RDBMS 
```
SELECT * FROM <table name> FETCH FIRST 5 ROWS ONLY;

```
## PERCENT clause with TOP:
Used to select  the first `n` percent of total rows.
```
SELECT TOP 40 PERCENT FROM <table name>;

```
## WITH TIES clause with TOP:
Used to select more rows if there are similar values to the last row:
```
SELECT TOP 3 WITH TIES first_name, country
FROM Customers
ORDER BY country DESC;
```
This first sorts by country in descending order, then selects the first 3 rows. Rows containing similar `country` field values to the last row are also selected. 
**Note that `ORDER BY` must always be used with the `WITH TIES` clause**

## SQL IN operator:
Used in conjuction with the `WHERE` clause to match values in a list. 
```
SELECT first_name, last_name FROM <table name> WHERE first_name IN ('Lenny', 'Orengo');

```

## SQL IN in columns:

The `IN` operator can also be used to select rows in which certain values exist in a given field.

```
SELECT first_name, country FROM <table name> WHERE 'usa' IN (country);
```

## SQL NOT IN operator:
`NOT IN` operator is used to exclude values that do not match the values given in the list. 

```
SELECT first_name country FROM < table name> WHERE country NOT IN ('usa', 'france');

```



*N/B: The `IN` operator ignores duplicate values in the list* 

## SQL IN with subqueries:

Example:
```
SELECT name FROM product_product WHERE product_id IN (SELECT id FROM order_orderitem);

```
## SQL BETWEEN operator:
This is used with the `WHERE` clause to match values in a range. For example:
```
SELECT * FROM order_orderitem WHERE product_amount BETWEEN 3000 AND 5000;
```
## SQL NOT BETWEEN operator:
This excludes values in a given range:
```
SELECT * FROM order_orderitem WHERE product_amount NOT BETWEEN 3000 AND 5000;
```

## SQL BETWEEN operator with Texts:
It also works with text:
```
SELECT * FROM product_product WHERE name BETWEEN 'a' AND 'c';
```
*Note that we can use the ~ to include all the words starting with a 'c'*
ie..
```
SELECT * FROM product_product WHERE name BETWEEN 'a' AND 'c~';
```

## SQL IS NULL:
This is a condition used to select a row/rows if the specified field is `NULL`..
```
SELECT * FROM order_order WHERE paid_amount IS NULL;
```

*Note that only empty values are NULL, spaces, '' and 0 are not NULL*

## SQL IS NOT NULL:
Selects rows whose specified fields are not `NULL`

## SQL IS NULL with COUNT() function:
Used to count the number of rows with an empty field.
```
SELECT COUNT(*) FROM order_order WHERE paid_amount IS NULLL;
```
## SQL MIN() and MAX() functions:
These return the minumum and maximum values in a column respectively.

```
SELECT MAX(price) FROM product_product;
```
They can also be used with aliases which provide custom names for the columns:
```
SELECT MAX(price) AS max_price FROM product_product;
```





