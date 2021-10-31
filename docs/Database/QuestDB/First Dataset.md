---
sidebar_position: 4
---
# Working on Dataset

Now lets learn how one can perform some operations in the QuestDB like :-

- Creating a Table
- Inserting data into Tables
- Some Queries to perform
- Deleting Tables

## Creating Dataset

This is the first step one can do while playing with the database. You have to create a table to start storing data and working with it. `Create` command is used for this :-

    CREATE TABLE tableName (col1 dataType1, col2 dataType2, col3 dataType3);

<strong>Note - </strong> To check the metadata of the table, run the following command to return the schema of the table:

    table_columns('tableName');

## Inserting data into Tables

To insert any record/data into the table, use `INSERT` command.

One can generally insert data into table in 3 ways :-

### Inserting all columns
Here we will insert the values of all columns specified in the schema and that too in the specifies order of the column names.

<strong>Note -</strong>  Character, Timestamp and String values are stored in single quotes <strong>''</strong>


    INSERT INTO tableName VALUES(
    value1, 'value2', value3, value4, 'value5');


### Inserting by specifying schema

Here we will insert the values of all columns by again writing the column names and the values will be inserted in that manner.

<strong>Note -</strong> Columns can be omitted during <strong>INSERT</strong> in which case value will be <strong>NULL</strong>

    INSERT INTO tableName (col1, col2, col3 ) VALUES(
    'value1', value2, value3);

### Inserting only specific columns

Here we will insert the values of only specified columns by writing the column names and the values will be inserted in that manner.

    INSERT INTO tableName (col1, col2, col3, col4) VALUES(
    'value1', value2, value3, 'value4');

## Some Queries to perform

QuestDB attempts to implement standard ANSI SQL clauses which have the following execution order :-

<strong>

- FROM
- ON
- JOIN
- WHERE
- LATEST BY
- GROUP BY (optional)
- WITH
- HAVING (implicit)
- SELECT
- DISTINCT
- ORDER BY
- LIMIT

</strong>

Some other useful commands or subqueries which we can use to instruct QuestDB to perform operations on our queries are :- 

```
ALTER,    CASE,    CAST,
COPY,    EXCEPT & INTERSECTION,    FILL,
JOIN,   LATEST BY,    LIMIT,
RENAME TABLE,    SAMPLE BY,    SHOW,
TRUNCATE TABLE,    UNION,    WITH
```
## Backup Tables

Backing up a database or tables requires a backup directory which is set using the cairo.sql.backup.root configuration key in a server.conf file:

<strong>server.conf</strong>

    cairo.sql.backup.root=/Users/UserName/Desktop

### Single table
    BACKUP TABLE tableName;
### Multiple tables
    BACKUP TABLE table1, table2, table3;
### All table
    BACKUP DATABASE;
## Deleting Tables
But <strong>careful</strong>. Once you run this command you will loose all your data and you won't be able to recover it so its better to first make a Backup of that table as learnt above.

    DROP tableName;
