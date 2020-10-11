# The Holy Grail of Internet Storage with SQL

What Databases are for the internet, is what your Hard-Disk is for you, except that databases have commands other than just a visual interface to move, copy, add, remove files, these commands help computers from everywhere to communicate with others and manipulate these storage containers using Structured Query Language (SQL).


SQL with [SQLBolt](https://sqlbolt.com/) will be the primary way to learn about these commands. Postgres is the language that we are going to learn at LTUC. Databases come in different taste and types, some are called [NoSQL Databases](https://www.mongodb.com/nosql-explained) (really famous to work with mongoDB) that are basically the opposite of relational databases. Relational means tables in two dimensions are related with other two dimensional tables, and data means lots of things depending on what it is connected to.

## Commands
SQL Query is the way, and it starts with `SELECT` in conjunction with `FROM`, it looks for the data and tried to pull it depending on the query after the `SELECT *`. `*` means all data, `FROM table1` specifies which able to get that data from. Now all commands are case insensitive, but just like many aspects of coding there are some syntax rules to help make code readable, of which all commands should be in UPPERCASE and all variables are in lowercase.

Instead of `*` all, there is per column select by typing out the column name, if there are more than one table you would perpend column with table name as `table1.column2` just like you would to access an object property.

### Conditional Select

Additional `WHERE condition` appended after the `FROM` command allows for more granular `SELECT` data. Conditions could be chained with `AND/OR` and `NOT` statements in addition to brackets to denote which comes first. `LIMIT` is your limit of data presentation if you only need some of the total data available.

Including the past conditions are constraint parameters such as `=`, `!=` or `<>` for case sensitive comparisons, `LIKE`, `NOT LIKE` for case insensitive strings, `%` would try to match zero or more strings around it `%bat%`, while `_` matches only one string instead of it, and finally ` column1 IN ('A','B','C')` and `column1 NOT IN ('A','B','C')` would try to match such strings inside column1.

### Filters and Sorts

`DISTINCT` helps filter only unique rows, its is positioned right after `SELECT` and before the column selection, and `ORDER BY column ASC/DESC` helps with data arrangement with `ASC/DESC`, it is positioned after `WHERE` conditional statement.

`LIMIT` also accepts `OFFSET` to select next data after the limit, such as `LIMIT 5 OFFSET 4` pick 4 data after the 5 limit instead of the 5.

## Schemas 

It means how data is structured in a table into columns with each column defining what type of data it contains such as `int` and `string`.

### Insert
```
INSERT INTO mytable
VALUES (value_or_expr, another_value_or_expr, …),
```
mytable is where the insert happens, and values specify row data, assuming you have all columns covered with data, if there are missing data we need `(column, another_column, …)` in between `INSERT INTO` and `VALUES`. 

### Update
```
UPDATE mytable
SET column = value_or_expr, 
    other_column = another_value_or_expr, 
    …
WHERE condition
```
Works by selecting the exact table, column (with `SET` column) and row (with `WHERE` conditions) and updates its value. Data types have to be respected.
Using `SELECT` before `UPDATE` makes sure we are using the correct constraints and conditions to then update that data safely.

### Delete
`DELETE FROM mytable WHERE condition;` deletes the whole row, again use select to make sure its the correct row!!1

### Creating Tables
```
CREATE TABLE IF NOT EXISTS mytable (
    column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value,
    …
);
```
Creates the table with the following Schema: 
* *DataType* specifies what data the column would hold.
* *TableConstraint* specifies additional value constraints.
* default_value helps fill the cell with data if it was not specified in `INSERT`.
`IF NOT EXISTS` helps to not get an error if that table already exists by same name.

*DataType* are of `INTEGER`, `BOOLEAN`, `FLOAT`, `DOUBLE`, `REAL`, `CHARACTER`(num_chars), `VARCHAR`(num_chars), `TEXT`, `DATE`, `DATETIME`, and finally binary `BLOB`s. (num_chars) specifies max length of string.

*TableConstraint* include 
- `PRIMARY KEY`: Unique numbers and refers to the row.
-	`AUTOINCREMENT`: Filled automatically by 1 increment.
- `UNIQUE`: Unique but does not have to be key.
- `NOT NULL`: No null values.
- `CHECK(expression)`: For complex conditions such as no negative etc.
-	`FOREIGN KEY`: Makes sure this value matches the same row that has that key in another column.

```
CREATE TABLE movies (
    id INTEGER PRIMARY KEY,
    title TEXT,
    director TEXT,
    year INTEGER, 
    length_minutes INTEGER
);
```
### Altering Tables
These operations would edit existing tables.

#### Add Columns With
```
ALTER TABLE mytable
ADD column DataType OptionalTableConstraint 
    DEFAULT default_value;
```
#### Removing Columns With
```
ALTER TABLE mytable
DROP column_to_be_deleted;
```
#### Renaming Table With
```
ALTER TABLE mytable
RENAME TO new_table_name;
```
#### Additional [Postgres](http://www.postgresql.org/docs/9.4/static/sql-altertable.html) Alter Commands

### And Drop Mic
```
DROP TABLE IF EXISTS mytable;
```
Don't forget to update dependant tables with `FOREIGN KEY` by removing dependant rows or whole tables.
