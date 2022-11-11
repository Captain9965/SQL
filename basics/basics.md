# Introduction:

How to list all table columns in Postgresql:
```
SELECT table_schema, table_name, column_name, data_type 
FROM INFORMATION_SCHEMA.COLUMNS 
WHERE table_name = '<table_name>' 
```

or in the `psql` command line: `\dS your_table_name`

Showing tables:
```
\dt or \dt+ for more information like size

```
