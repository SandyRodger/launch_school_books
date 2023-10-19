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

- 

#### [Summary](https://launchschool.com/books/sql/read/interacting_with_postgresql#summary)


### 4. SQL Basics Tutorial
Set Up
Connect
Select all
Selecting columns
Selecting rows
Selecting columns and rows
Data vs Schema
Summary
Exercises

## YOUR FIRST DATABASE: SCHEMA
### 5. Create and View Databases
Create a database
 Connecting to a Database
- Delete the Database
- Summary
- Exercises
### 6.Create and View Tables
- Table Creation Syntax
- Data Types
- Keys and Constraints
- View the Table
- Schema and DCL
- Summary
- Exercises
### 7. Alter a Table
- Alter Table Syntax
- Renaming a Table
- Renaming a Column
- Changing a Column's Datatype
- Adding a Constraint
- Removing a Constraint
- Adding a Column
- Removing a Column
- Dropping Tables
- Summary
- Exercises
## YOUR FIRST DATABASE: DATA
### 8. Add Data with INSERT
- Data and DML
- Setup
- Insertion Statement Syntax
- Adding Rows of Data
- Constraints and Adding Data
- Summary
- Exercises
### 9.Select Queries
- Select Query Syntax
- ORDER BY
- Operators
- Summary
- Exercises
### 10. More on Select
- LIMIT and OFFSET
- DISTINCT
- Functions
- GROUP BY
- Summary
- Exercises
### 11. Update Data in a Table
- Updating Data
- Deleting Data
- Update vs Delete
- Use Caution
- Summary
- Exercises
## WORKING WITH MULTIPLE TABLES
### 12. Create Multiple Tables
- Normalization
- Database Design
- Keys
- One-to-One
- Referential Integrity
- One-to-Many
- Many-to-Many
- Summary
- Exercises
### 13. SQL Joins
- Join Syntax
- Types of Joins
- Multiple Joins
- Aliasing
- Subqueries
- Summary
- Exercises
## CONCLUSION
### 14. Summary and Additional Resources
- Summary
- Next Steps
- Resources
