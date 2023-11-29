# Week 2 Study Guide

## Day 1

What is the cloud?

What is AWS?

What are regions?

What are availability zones?

What is the relationship between regions and availability zones?

What is AWS IAM?

What is AWS RDS?

What is a relational database?

What is the difference between relational and non-relational databases?

What is the benefit of using a relational database?

What is SQL?

What is an RDBMS?

What is PostgreSQL?

What is a schema?

What is a table/relation?

What is a column/field?

What does a row represent?

What is a primary key?

What is the difference between natural and surrogate keys?

What makes a good primary key?

What are constraints? Give an example of when you would use one.

What PostgreSQL data types would I use to represent each of the following?
- a surrogate key that auto-increments
- a first name
- a 5-character code
- a bank account balance
- an age

## Day 2

What is multiplicity?

What are the different multiplicity relationships?

What are junction tables? Which type(s) of relationships would use one?

What are lookup tables?

What are foreign keys?

What is the purpose of using a foreign key constraint?

What is referential integrity? What are orphaned records?

What is a composite key?

What is an ERD?

What is database normalization? What is the benefit of this?

Describe each normal form: 1NF, 2NF, 3NF.

What is denormalization? What is the benefit of this?

What are the sublanguages of SQL?

What is the difference between `INSERT` and `CREATE`?

What is the difference between `ALTER` and `UPDATE`?

What is the difference between `DROP` and `TRUNCATE`?

## Day 3

What does `COMMIT` do in SQL?

What does `ROLLBACK` do? Where does it rollback to?

What does the `WHERE` keyword do?

What does `ORDER BY` do?

What is the difference between `UNION` and `UNION ALL`?

What is the downside of set operations?

What is the difference between scalar and aggregate functions? Give examples of each.

What does `GROUP BY` do? When can you use it?

What are joins in SQL?

What are the different types of joins? Give an example of when you would use each one.

What are nested queries?

What is a result set?

What are indexes? How do they improve database performance?

What are views?

What is PL/SQL?

What is the difference between a function and a (stored) procedure in PostgreSQL?

## Day 4

What is Maven?

What is the benefit of build automation?

What is the basic Maven lifecycle?

What is the benefit of Maven's dependency management?

What are Maven project archetypes?

What is the Maven repository?

What is XML?

What is an XML schema? What are elements and attributes?

What are XML namespaces?

What does it mean for XML to be well-formed? What does it mean for it to be valid?

What is JDBC?

Why do you need a driver with JDBC?

What is a `Connection` object? What does it allow you to do?

What is the difference between `Statement` and `PreparedStatement`?

Why would we set autoCommit to false when using JDBC?

What are the ACID properties of a transaction?

What is the factory design pattern? Give an example of when we might use it.

What is the singleton design pattern? Give an example of when we might use it.

What is the state design pattern? Give an example of when we might use it.

What is the DAO (data access object) design pattern?

How do the above design patterns emphasize any particular SOLID principles?

## Day 5

What are some of the methods that we can use with `Statement`/`PreparedStatement`?

What is the `ResultSet`? What does `.next()` do?

What are the transaction isolation levels? What are the read anomalies associated with each?

What is transaction propagation?

What is an ORM? Why are they possible?

What is an H2 database?

Why would we use an in-memory database for testing?

What are greedy algorithms?

What is a set as a data structure?

What is a hash function?

What is a hash set? What is the benefit of using one?