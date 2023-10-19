# [Introduction to SQL](https://launchschool.com/books/sql)

## GETTING STARTED

### [1. Introduction](https://launchschool.com/books/sql/read/introduction)
#### [The importance of data](https://launchschool.com/books/sql/read/introduction#data)

- When it comes to the human ability to understand and remember large amounts of information there are hard limits. We can surpass these with our ability to handle large amounts of information.
  - collecting data.
  - organizing it.
  - studying it.
  - looking for patterns and meaning.
- In order to do this we need to store it in a structured way that lends itself to studying.
- Video of Hans Rosling interpreting life expectency data in 20th century.


#### [Structured Data](https://launchschool.com/books/sql/read/introduction#structureddata)

- Structured data aims to solve the problem of unstructured data. Unstructured data is like a notice-board.
- In small amounts, unstructured data is fine. THe larger the data, the more unwieldy it becomes. THink about searching through a notebook for a single quote.
- One way to store data is in a table (rows and columns) like a spreadsheet. These are great for managing and finding information. We can sort it and do things like calculate totals.
- A database is simply *a structured set of data held in a computer*.
  
#### [Spreadsheet as Database](https://launchschool.com/books/sql/read/introduction#spreadsheetdb)

- Think of a spreadsheet on Excel. It may have multiple sheets for different aspects of the same information.
- Different sheets will have unique columns, but also columns that are the same as the others, like ID and name.
- Rows represent a single set of related fdata and columns represent a standardized way of storing data for that particular attribute.

#### [Relational Database Management Systems](https://launchschool.com/books/sql/read/introduction#rdbms)

- AKA **RDBMS**
- If lots of people are adding to the database and messing it up, now you probably need a relational database management system.
- This is a model that defines a set of relations (like tables) and the relationships between them in order to rule how data is stored between them.
- This makes the database more than just a 2D collection of tables into a more ocmplex and detailed collection of information.
- It also helps us to cut down on duplicated data and makes it more useful to interact with.

#### [SQL](https://launchschool.com/books/sql/read/introduction#sql)

- Uses simple English sentences to 'select', 'insert', 'update' and 'delete' a large amount of data.
- This book uses PostgresQL because it's widely applicable and open source. But after this book you will have the tools to use any RDBMS you choose.
- SQL is different to other programming languages encountered so far in that it is **declarative**. This means when you write a sentence in SQL you are writing what needs to be done, but not how to do it. The details are handled internally, out of sight.
- "relational algebra"

#### [Why learn SQL?](https://launchschool.com/books/sql/read/introduction#whylearnsql)

- You're using them unknowingly everyday, in:
  - browsers like Firefox, which uses SQLite to keep track of user history and data.
  - Banking, which might use an Oracle database to store daily transactions.
  - programming languages like Ruby, which generate code behind the scenes for you.
- Creating a well-designed database is like laying the foundations for a house. The foundation should be strong in order to last a long time.

#### [Summary](https://launchschool.com/books/sql/read/introduction#summary)

- ...

### 2. Preparations

#### [Vocabulary](https://launchschool.com/books/sql/read/preparations#vocabulary)

- Relational Database:
  - A structured collection of data that follows the relational model.
- RDBMS:
  - Relational DataBase Management System. A software application for managing relational databases, such as PostgreSQL.
- Relation:
  - A set of individual but related data entries; analogous to a database table.
- SQL:
  - Structured Query Language. The language used by RDBMSs.
- SQL statement:
  - A SQL command used to access/use the database or the data within that database via the SQL language.
- SQL query:
  - A subset of a "SQL statement". A query is a way to search, or lookup data within a database, as opposed to updating or changing data.

#### [Installing PostgreSQL](https://launchschool.com/books/sql/read/preparations#installpostgres)

- follow instructions on [this Medium article](https://launchschool.medium.com/how-to-install-postgresql-for-mac-os-x-61623df41f59)
- `brew install postgresql@16`
- `brew tap homebrew/services`
- `brew services start postgresql`

#### [Summary](https://launchschool.com/books/sql/read/preparations#summary)

- ...

### [3. Interacting With PostgreSQL](https://launchschool.com/books/sql/read/interacting_with_postgresql)

#### [Interacting with a database](https://launchschool.com/books/sql/read/interacting_with_postgresql#interactingwithadatabase)

- THere are many interfaces that ou can use to interact with a RDBMS, like PostgreSQL:
  - Through a programming language.
  - from a GUI application.
  - Through the CLI.
- but they all use the same architechture to interact with the database. They issue a request and receive a response.
- This is called "client-server" architecture.
- It's like a sushi chef being approached by clients to choose their sushi.

![Screenshot 2023-10-19 at 09 34 55](https://github.com/SandyRodger/launch_school_books/assets/78854926/6451e558-e4ae-482d-a4f5-6d70bebf4a4a)

- There may be different ways to order (via a waiter, via an app, directly with the chef). These are analogous to different layers of abstraction within the same model.
- Whichever type of PostgrSQL client you choose, that interface is just an abstraction atop the database, using SQL syntax.
- In this book we use the CLI to develop a stronger understanding of database fundamentals.

#### [PostgreSQL Client Applications](https://launchschool.com/books/sql/read/interacting_with_postgresql#postgresqlclientapps)

- PostgreSQL comes packaged with some 'clinet applications', which are used to interact with PostgreSQL via commands on the command-line. Client applications, like:
  - `createdb`
  - `dropdb`
  - `pg_pump`
  - `pg_restore`
  - `pg_bench`
- Some of these client-apps are really just wrappers around SQL commands. For example `createdb` isa wrapper around the SQL command `CREATE DATABASE` which creates a new PostgreSQL database.
- We'll be using `psql` a lot here. It's an interactive console. Like a termoinal based front-end to PostgreSQL. It's basically a REPL, like IRB.
- remember that commands like `createdb` and `dropdb` are called from the terminal, not from within `psql`.

#### [The psql console](https://launchschool.com/books/sql/read/interacting_with_postgresql#psqlconsole)

- `psql postgres`
- From this console you can issue 2 types of command:
  - meta-commands:
    - `\` followed by the command and optional arguments, like `\conninfo`, which tells you details of your connection to the database. For me it returns:
      - `You are connected to database "postgres" as user "sandyboy" via socket in "/tmp" at port "5432".`
    - These commands can be used to
      - connect to different databases
      - connect to different listing tables
      - to descrivbe the structure of a particular table
      - to set environment variables
    - for example `\q` which quits the psql console.
  - SQL staements:
    - Commands issued to the database using SQL syntax.
      - `SELECT name FROM people WHERE id = 1;`
      - SQL statements always terminate in a semi-colon. (so you can multi-line it)
      - A `SELECT` statement is used to retrieve data from a database and ther response would loook like this:
```
  name
---------
 Michael
(1 row)
```

#### [SQL Sub-languages](https://launchschool.com/books/sql/read/interacting_with_postgresql#sqlsublanguages)

- There are 3 sublanguages:
  - Data Definition Language (DDL: for defining the structure of a database and the tables/columns within.
  - Data Manipulation Language (DML): Used to retrieve or modify data stored in a database. `SELECT` queries for example.
  - Data Control Language (DCL): Used to deteremine what various users are allowed to do when interacting with a database.
- This book deals with only the first 2.

#### [Summary](https://launchschool.com/books/sql/read/interacting_with_postgresql#summary)

### [4. SQL Basics Tutorial](https://launchschool.com/books/sql/read/basics_tutorial)

#### [Set Up](https://launchschool.com/books/sql/read/basics_tutorial#setup)

- `createdb ls_burger`
- The instruction is then to download a file and save it as `ls_burger.sql`. The problem i encountered was that the command line did not recognise the file as SQL. I used chatGPT to translate the file into SQL and copied that into `ls_burger.sql` and it now works.
- `psql -d ls_burger < ls_burger.sql`

#### [Connect](https://launchschool.com/books/sql/read/basics_tutorial#connect)

- `psql -d ls_burger`

#### [Select all](https://launchschool.com/books/sql/read/basics_tutorial#selectall)

- The `SELECT` keyword is used to access data from a database. A basic example might look like this:
- `SELECT * FROM orders;`

<img width="829" alt="Screenshot 2023-10-19 at 11 06 34" src="https://github.com/SandyRodger/launch_school_books/assets/78854926/9a4e6d9f-759b-403a-aca7-96f6837328c1">

- `SELECT` - the keyword that identifies the type of statement being issued. this one is for retrieving data.
- `*` a wild card character
- `FROM` another keyword identifying the table from which to retrieve the data
- `orders` This is the nameof the table.

#### [Selecting columns](https://launchschool.com/books/sql/read/basics_tutorial#selectcolumns)

- like this `SELECT side FROM orders;`
- or multiple columns with `SELECT drink, side FROM orders;`
- you can choose a different order like this `SELECT side, drink FROM orders;`

#### [Selecting rows](https://launchschool.com/books/sql/read/basics_tutorial#selectrows)

- For example, to return the data from all of the columns for the row where `id` is `1`m we use `WHERE`:
  - `SELECT * FROM orders WHERE id = 1;`
- Note that in SQL `=` is an equality ioerator, not for assignment.

#### [Selecting columns and rows](https://launchschool.com/books/sql/read/basics_tutorial#selectcolumnsandrows)

- both together is like this:
  - 'SELECT customer_name FROM orders WHERE side = 'Fries';'
  - Notice `'Fries'` has quotes. Because it's a string. Before we were looking at `id`s which are ints.

#### [Data vs Schema](https://launchschool.com/books/sql/read/basics_tutorial#datavsschema)

- Schema is concerned with the structure of the database. Things like:
  - names
  - tables
  - table columns
  - data-types
- Data is concerned with the contents of the database. THese are the actual values in the rows and columns.
- Schema without data:

![Screenshot 2023-10-19 at 11 28 42](https://github.com/SandyRodger/launch_school_books/assets/78854926/93d8733f-deaa-481c-b5d6-b1118e8f4663)

- Data without schema:

![Screenshot 2023-10-19 at 11 29 12](https://github.com/SandyRodger/launch_school_books/assets/78854926/21bb05c9-c5a1-4d0d-98f9-9785ed51f58a)

#### [Summary](https://launchschool.com/books/sql/read/basics_tutorial#summary)

#### [Exercises](https://launchschool.com/books/sql/read/basics_tutorial#exercises)

1. Write a query that returns all of the customer names from the orders table. = 'SELECT customer_name FROM orders;'
2. Write a query that returns all of the orders that include a Chocolate Shake. = `SELECT * FROM orders WHERE drink = 'Chocolate Shake';`
3. Write a query that returns the burger, side, and drink for the order with an id of 2. = `SELECT burger, side, drink FROM orders WHERE id = 2;`
4. Write a query that returns the name of anyone who ordered Onion Rings. =  `SELECT customer_name FROM orders WHERE side = 'Onion Rings';`

## YOUR FIRST DATABASE: SCHEMA

### [5. Create and View Databases](https://launchschool.com/books/sql/read/create_database)

#### [Create a database](https://launchschool.com/books/sql/read/create_database)

 - `createdb sql_book`
 - `psql -d sql_book`

 ##### Using a SQL statement

- Instead of `createdb` you could use the SQL syntax `CREATE DATABASE`. Like this:
  - `CREATE DATABASE another_database;`
  - `DROP DATABASE another_database;`
- The convention of uppercase from SQL staements and lowercase for tables and databases is for clarity only.
- When creating databases the name parameter is mandatory and there are other, optional parameters for things like:
  - encoding
  - collation
  - connection limit
  - etc.

##### Database naming

- DB names should be self-descriptive. When you have many DBs this becomes important.
- Snake-case.
 
 
#### [Connecting to a Database](https://launchschool.com/books/sql/read/create_database#connnecttodb)

- We can open the psql console and connect to a database with the command `psql` + a `-d` option + database name.
- From within psql we can connect to different DBs with `\c` or `\connect` meta-commands.
- `\c another_database`

#### [Delete the Database](https://launchschool.com/books/sql/read/create_database#deletingdb)

- `DROP DATABASE another_database;`
- Be very careful with these commands, they are irreversable.

##### Using dropdb

- this has to be run from the command line because it is a PostgreSQL command wrapping up the `DROP DATABASE` SQL command, which would be run from teh psql console.

#### [Summary](https://launchschool.com/books/sql/read/create_database#summary)

- Something about the `\e` command that I'm failing to grasp.

- commands so far:
  - PSQL Meta-Commands
    - `\l` or `\list`
    - `\c sql_book` or `\connect sql_book`
  - Client/Application Command-Line Command
    - `psql -d sql_book`
    - `createdb sql_book` , which is a wrapper function for `CREATE DATABASE sql_book`
    - `dropdb my_database`, which is a wrapper function for `DROP DATABASE my_database`

#### [Exercises](https://launchschool.com/books/sql/read/create_database#exercises)

1. From the Terminal, create a database called database_one. = `createdb database_1`
2. From the Terminal, connect via the psql console to the database that you created in the previous question. = `psql -d database_1`
3. From the psql console, create a database called database_two. = `CREATE DATABASE database_2;`
4. From the psql console, connect to database_two. = `\c database_two`
5. Display all of the databases that currently exist. = `\list`
6. From the psql console, delete database_two. = `DROP DATABASE database_1;`
7. From the Terminal, delete the database_one and ls_burger databases.

```
\q
dropdb database_one
dropdb ls_burger
```

### [6.Create and View Tables](https://launchschool.com/books/sql/read/create_table)

- Now that we have created out `sql_book` database, we have the outer shell of our building.
- Now we need to add some rooms (tables in this analogy AKA 'relations`).
- 

#### [Table Creation Syntax](https://launchschool.com/books/sql/read/create_table#tablecreationsyntax)

- `CREATE TABLE some_table();`
- with columns:

```
CREATE TABLE table_name (
    column_1_name column_1_data_type [constraints, ...],  # the square brackets are for optional parts of the CREATE TABLE command.
    column_2_name column_2_data_type [constraints, ...],   # constrainst can be added at the column level or at the table level.
    .
    .
    .
    constraints
);
```

##### Creating a `users` table

```
CREATE TABLE users (
       id serial UNIQUE NOT NULL,
       username char(25),
       enabled boolean DEFAULT TRUE
);
```

- which means:
  - `CREATE TABLE users` is the primary command.
  - `users` The name of the table that will be created.
  - `():` The information in the parentheses is related to the columns in the table.
  - `id, username, enabled` These are the three columns of the table.
  - `serial, char(25), boolean` These are the data types of the columns.
  - `UNIQUE, NOT NULL` These are constraints.
  - `DEFAULT TRUE` Specifies a default value for the column. 
- This command is issued from the `psql` console while connected to `sql_book` database.
- `SELECT * FROM users;` to see the table so far (it's just headers)

# [Data Types](https://launchschool.com/books/sql/read/create_table#datatypes)
# Keys and Constraints
# View the Table
# Schema and DCL
# Summary
# Exercises
### 7. Alter a Table
# Alter Table Syntax
# Renaming a Table
# Renaming a Column
# Changing a Column's Datatype
# Adding a Constraint
# Removing a Constraint
# Adding a Column
# Removing a Column
# Dropping Tables
# Summary
# Exercises
## YOUR FIRST DATABASE: DATA
### 8. Add Data with INSERT
# Data and DML
# Setup
# Insertion Statement Syntax
# Adding Rows of Data
# Constraints and Adding Data
# Summary
# Exercises
### 9.Select Queries
# Select Query Syntax
# ORDER BY
# Operators
# Summary
# Exercises
### 10. More on Select
# LIMIT and OFFSET
# DISTINCT
# Functions
# GROUP BY
# Summary
# Exercises
### 11. Update Data in a Table
# Updating Data
# Deleting Data
# Update vs Delete
# Use Caution
# Summary
# Exercises
## WORKING WITH MULTIPLE TABLES
### 12. Create Multiple Tables
# Normalization
# Database Design
# Keys
# One-to-One
# Referential Integrity
# One-to-Many
# Many-to-Many
# Summary
# Exercises
### 13. SQL Joins
# Join Syntax
# Types of Joins
# Multiple Joins
# Aliasing
# Subqueries
# Summary
# Exercises
## CONCLUSION
### 14. Summary and Additional Resources
# Summary
# Next Steps
# Resources
