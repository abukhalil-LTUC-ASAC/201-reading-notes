# Databases but normalized this time

As you could imagine by now, doing all data in a single table could be a major headache if you ever decide to modify some entries, then have to do it all over again for the same entry in other rows.

Normalized databases follow certain rules to reduce that headache by utilizing relational databases. The id column you would use for each user for an example, would be called the primary key and would refer to the same key in other tables called foreign keys. All data in a single primary key is connected that way. Until [NoSQL](https://www.mongodb.com/nosql-explained/nosql-vs-sql) barged in, however SQL is still relevant and important due to [expertise limitation](https://www.mongodb.com/nosql-explained/nosql-vs-sql).

## Make sure you understand [what databases table mean](https://www.essentialsql.com/what-is-a-database-table).

For real, before any step forward! This [website](https://www.essentialsql.com/get-ready-to-learn-sql-database-normalization-explained-in-simple-english/) is our reference for today.

## Reasons for Database Normalization
> There are three main reasons to normalize a database.  The first is to minimize duplicate data, the second is to minimize or avoid data modification issues, and the third is to simplify queries. 

### Duplicate Data and their modifications
Happens when you'd have a single id, with its direct **defining column** values such as age, name, salary etc having for an example multiples of other columns such as customers, region visited etc where each column will have the same defining features of that ID. Changing any defining feature requires that change over all duplicate rows.

- Insert Change Anomaly happens when you'd want a new entry for a row, but the defining columns would also need to be stated.
- Update Anomaly which is literally all rows that relates to the ID.
- Deletion Anomaly is the risk loosing all data on other columns than the defining column, if you ever decided to delete the id, if he retires for an example.

### Search and Show

try searching for ford.
```
SELECT SalesOffice
FROM SalesStaff
WHERE Customer1 = ‘Ford’ OR
      Customer2 = ‘Ford’ OR
      Customer3 = ‘Ford’
```

If only you had one table, column to do that all.

## So How Would You Normalize It!
***[First Normal Form](https://www.essentialsql.com/get-ready-to-learn-sql-8-database-first-normal-form-explained-in-simple-english/)*** 
- The information is stored in a relational table with each column containing atomic values. There are no repeating groups of columns.

***[Second Normal Form](https://www.essentialsql.com/get-ready-to-learn-sql-10-database-second-normal-form-explained-in-simple-english/)*** 
- The table is in first normal form and all the columns depend on the table’s primary key.

***[Third Normal Form](https://www.essentialsql.com/get-ready-to-learn-sql-11-database-third-normal-form-explained-in-simple-english/)*** 
- The table is in second normal form and all of its columns are not transitively dependent on the primary key.

Each form needs to be fulfilled by order, so no skipping and no cheating by swapping.

