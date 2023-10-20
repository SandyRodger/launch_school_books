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
- Video of Hans Rosling interpreting life-expectancy data in 20th century.


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

#### [Data Types](https://launchschool.com/books/sql/read/create_table#datatypes)

- serial: used to create id columns for a PostgrSQL database. They are integers and autoincrementing. Can't be null.
  - 'serial' is no longer recommended for new apps. As of PostgreSQL v.10 there's 'IDENTITY' syntax for this. Don't worry about this, v9 and lower are still widespread and used in this book.
- char(n): String of up to n chars. Anything less than n is filled with whitespace.
- varchar(n): as above, but remaining char-spaces are not used.
- boolean(n): often represented as t or f.
- INT or integer: just an int
- decimal(precision, scale): 'precision' is total digits in the entire number, both sides of the decimal. 'scale' is total of digits to the right of the decimal.
- timestamp: contains date and time like this YYYY-MM-DD HH:MM:SS
- data: as above, but without the time.

#### [Keys and Constraints](https://launchschool.com/books/sql/read/create_table#keysandconstraints)

- constraints are optional, but super-useful.
- Databases really have to maintain the integrity/quality of the data they're storing.
- Keys and constraints sre rules that define what values are allowed in each column. It's part of the schema.
- Constraints can apply to one column, a whole, table, mamy tables or the whole schema.
- Looking at the previous example:

```
CREATE TABLE users (
       id serial UNIQUE NOT NULL,
       username char(25),
       enabled boolean DEFAULT TRUE
);
```

- UNIQUE: the `id` column can't have any duplicates.
- NOT NULL: This entry can't be left empty.
- DEFAULT TRUE: `enabled` defaults to true.

- We look at keys later on in the book. 

#### [View the Table](https://launchschool.com/books/sql/read/create_table#viewtable)

- `\dt` shows us a list of the tables and their relations in the database.
- If we want more detail we use `\d` which lets us describe a table. ie. `\d users`

#### [Schema and DCL](https://launchschool.com/books/sql/read/create_table#schemadcl)

- DCL manages who has permission to do what, ie. security.
- We don't cover it in this book, but DCL is part of a database's schema.

#### [Summary](https://launchschool.com/books/sql/read/create_table#summary)

- 

#### [Exercises](https://launchschool.com/books/sql/read/create_table#exercises)

1. From the Terminal, create a database called encyclopedia and connect to it via the psql console.

Solution: 

`createdb encyclopedia`
`psql -d encyclopedia`

2. Create a table called `countries`. It should have the following columns:

- An `id` column of type `serial`
- A `name` column of type `varchar(50)`
- A `capital` column of type `varchar(50)`
- A `population` column of type `integer`
- The `name` column should have a `UNIQUE` constraint. The `name` and `capital` columns should both have `NOT NULL` constraints.

Solution:

```
CREATE TABLE countries (
       id serial,
       name varchar(50) UNIQUE NOT NULL,
       capital varchar(50) NOT NULL,
       population integer
);
```

3. Create a table called `famous_people`. It should have the following columns:

- An `id` column that contains auto-incrementing values
- A `name` column. This should contain a string up to 100 characters in length
- An `occupation` column. This should contain a string up to 150 characters in length
- A `date_of_birth` column that should contain each person's date of birth in a string of up to 50 characters
- A `deceased` column that contains either `true` or `false`

The table should prevent NULL values being added to the name column. If the value of the deceased column is absent or unknown then false should be used.

Solution:

```
CREATE TABLE famous_people (
       id serial,
       name varchar(100) NOT NULL,
       occupation varchar(150),
       date_of_birth varchar(50),
       deceased boolean DEFAULT FALSE
);
```

4. Create a table called `animals` that could contain the sample data below:

| Name |	Binomial Name |	Max Weight (kg)|	Max Age (years)|	Conservation Status|
| :---: | :---: | :---: | :---: |:---: |
| Lion |	Pantera| leo|	250|	20|	VU|
|Killer Whale|	Orcinus orca|	6,000|	60|	DD|
|Golden Eagle|	Aquila chrysaetos|	6.35|	24|	LC|

- The database table should also contain an auto-incrementing 'id' column.
- Each animal should always have a name and a binomial name.
- Names and binomial names vary in length but never exceed 100 characters.
- The max weight column should be able to hold data in the range 0.001kg to 40,000kg
- Conservation Status is denoted by a combination of two letters (CR, EN, VU, etc).
  
Please note that this exercise, and others in this book, use the English numerical format in the exercise description.

- Thousands are separated by a comma, so one thousand is displayed as 1,000.
- Decimals are separated by a period, so one and a half is displayed as 1.5.
  
Solution:

```
CREATE TABLE animals (
       id serial,
       name varchar(100) NOT NULL,
       binomial_name varchar(100) NOT NULL,
       max_weight_kg decimal(8,3),
       max_age_years integer,
       conservation_status char(2)     # often char is used when the length will always be the same.
);
```

5. List all of the tables in the encyclopedia database.

Solution:

`\dt`

6. Display the schema for the animals table.

Solution:

` \d animals`

7. Create a database called `ls_burger and connect to it.

Solution:

`CREATE DATABASE ls_burgers;`
`\c ls_burgers`

8. Create a table in the ls_burger database called orders. The table should have the following columns:

- An `id` column, that should contain an auto-incrementing integer value.
- A `customer_name` column, that should contain a string of up to 100 characters.
- A `burger` column, that should hold a string of up to 50 characters.
- A `side` column, that should hold a string of up to 50 characters.
- A `drink` column, that should hold a string of up to 50 characters.
- An `order_total` column, that should hold a numeric value in dollars and cents. Assume that all orders will be less than $100.
- The `customer_name` and `order_total` columns should always contain a value.

Solution:

```
CREATE TABLE orders (
       id serial,
       customer_name varchar(100) NOT NULL,
       burger varchar(50),
       side varchar(50),
       drink varchar(50),
       order_total decimal(4,2) NOT NULL
);
```

### [7. Alter a Table](https://launchschool.com/books/sql/read/alter_table)

- Databases and the needs of those using them change.
- DDL: Data definition Language, is how we make these changes.
- Be considerate when making changes to a database. It can have unintended and far-reaching consequences.

#### [Alter Table Syntax](https://launchschool.com/books/sql/read/alter_table#altertablesyntax)

- `ALTER TABLE` is only for the schema, not data.
```
ALTER TABLE table_to_change
    stuff_to_change_goes_here
    additional_arguments
```

#### [Renaming a Table](https://launchschool.com/books/sql/read/alter_table#renamingatable)

```ALTER TABLE users
      RENAME TO all_users;
```

#### [Renaming a Column](https://launchschool.com/books/sql/read/alter_table#renamingacolumn)

```
ALTER TABLE all_users
      RENAME COLUMN username TO full_name;
```

#### [Changing a Column's Datatype](https://launchschool.com/books/sql/read/alter_table#changedatatype)

```
ALTER TABLE all_users
      ALTER COLUMN full_name TYPE varchar(25);
```

#### [Adding a Constraint](https://launchschool.com/books/sql/read/alter_table#addingaconstraint)

- You can't change constraints, you can only remove or add them.
- Syntax is complicated by the fact that some constraints are considered tables constraints, and some column constraints.
  - `NOT NULL` is always column.
    - If you want to use it for tables there's a special command:

```
ALTER TABLE table_name
      ALTER COLUMN column_name
      SET NOT NULL;
```

  - `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE` and `CHECK` are either.
  - `CREATE TABLE` takes both types.
  - `ALTER TABLE` only take table or `NOT NULL`.
  - For any other constraint-change to an existing table, it's:

```
ALTER TABLE table_name
      ADD [ CONSTRAINT constraint_name ]
      constraint_clause;
```

- For our exercise we now do this:

```
ALTER TABLE all_users
      ALTER COLUMN full_name
      SET NOT NULL;
```

#### [Removing a Constraint](https://launchschool.com/books/sql/read/alter_table#removingaconstraint)

- For most constraints we can use the same syntax for table and column.

```
ALTER TABLE table_name
      DROP CONSTRAINT constraint_name;
```

- When we use `serial` data-type it automatically adds a `DEFAULT` of `nextval`. So dropping that isn't technically a constraint. Therefore it looks like this:

```
ALTER TABLE all_users
      ALTER COLUMN id
      DROP DEFAULT;
```

#### [Adding a Column](https://launchschool.com/books/sql/read/alter_table#addingacolumn)

- you can use a `ADD COLUMN` clause in an `ALTER TABLE` statement.

```
ALTER TABLE all_users
      ADD COLUMN last_login timestamp
                 NOT NULL
                 DEFAULT NOW();
```

- `NOW()` is an SQL function which returns the current data and time when called.

#### [Removing a Column](https://launchschool.com/books/sql/read/alter_table#removingacolumn)

- As above, but with `DROP COLUMN`

```
ALTER TABLE all_users DROP COLUMN enabled;
```

# [Dropping Tables](https://launchschool.com/books/sql/read/alter_table#droptables)

```
 DROP TABLE all_users;
```

- Be careful! This is irreversible and deletes all data and schema.

#### [Summary](https://launchschool.com/books/sql/read/alter_table#summary)


#### [Exercises](https://launchschool.com/books/sql/read/alter_table#exercises)


1. Make sure you are connected to the `encyclopedia` database. Rename the `famous_people` table to celebrities.

Solution: `ALTER TABLE famous_people RENAME TO celebrities;

2. Change the name of the name column in the celebrities table to first_name, and change its data type to varchar(80).

Solution: 

```
ALTER TABLE celebrities RENAME COLUMN name TO first_name;
ALTER TABLE celebrities ALTER COLUMN first_name TYPE varchar(80;
```

3. Create a new column in the `celebrities` table called `last_name`. It should be able to hold strings of lengths up to 100 characters. This column should always hold a value.

Solution: `ALTER TABLE celebrities ADD COLUMN last_name varchar(100) NOT NULL;`

4. Change the celebrities table so that the date_of_birth column uses a data type that holds an actual date value rather than a string. Also ensure that this column must hold a value.

Solution: `ALTER TABLE celebrities ALTER COLUMN date_of_birth TYPE date USING date_of_birth::date, ALTER COLUMN date_of_birth SET NOT NULL;`

5. Change the max_weight_kg column in the animals table so that it can hold values in the range 0.0001kg to 200,000kg

Solution:

```
ALTER TABLE animals ALTER COLUMN max_weight_kg TYPE decimal(10,4);
```

6. Change the `animals` table so that the `binomial_name` column cannot contain duplicate values.

Solution: `ALTER TABLE animals ADD CONSTRAINT unique_binomial_name UNIQUE (binomial_name);`

7. Connect to the `ls_burger` database. Add the following columns to the `orders` table:

- A column called `customer_email`; it should hold strings of up to 50 characters.
- A column called `customer_loyalty_points` that should hold integer values. If no value is specified for this column, then a value of `0` should be applied.

Solution:

```
\c ls_burgers
ALTER TABLE orders
      ADD COLUMN customer_email varchar(50),
      ADD COLUMN customer_loyalty_points integer DEFAULT 0;
```

8. Add three columns to the `orders` table called `burger_cost`, `side_cost`, and `drink_cost` to hold monetary values in dollars and cents (assume that all values will be less than $100). If no value is entered for these columns, a value of `0` dollars should be used.

Solution:

```
ALTER TABLE orders
      ADD COLUMN burger_cost decimal(4,2) DEFAULT 0,
      ADD COLUMN side_cost decimal(4,2) DEFAULT 0,
      ADD COLUMN drink_cost decimal(4,2) DEFAULT 0;
```

9. Remove the order_total column from the orders table.

Solution: `ALTER TABLE orders DROP COLUMN order_total;`


## YOUR FIRST DATABASE: DATA

### [8. Add Data with INSERT](https://launchschool.com/books/sql/read/add_data)

- We've looked at schema, now time for data.
- DML Data Manipulation Language

#### [Data and DML](https://launchschool.com/books/sql/read/add_data#dmldata)

- Data manipulation statements have 4 types:
  - `INSERT` to add new data into a database.
  - `SELECT` AKA queries, to retrieve data.
  - `UPDATE` to update data.
  - `DELETE` tot delete data.
- AKA CRUD

##### A bit about CRUD

- Create, Read, Update, Delete.
- Web apps whose main function is to provide an interface for these 4 functions are called 'crud apps'.

#### [Setup](https://launchschool.com/books/sql/read/add_data#setup)

```
CREATE TABLE users (
    id serial UNIQUE NOT NULL,
    full_name character varying(25) NOT NULL,
    enabled boolean DEFAULT true,
    last_login timestamp without time zone DEFAULT now()
);
```

#### [Insertion Statement Syntax](https://launchschool.com/books/sql/read/add_data#insertionstatementsyntax)

```
INSERT INTO table_name
            (column1_name, column2_name,...)
     VALUES (data_for_column1, data_for_column2, ...);
```

- The `INSERT` statement requires 3 pieces of info:
  - the table name we want to store data in.
  - The names of the columns we're adding data to.
  - The values we want to store in these columns.
- When inserting data you can specify exactly which columns you want. It's better to specify columns as not doing so can lead to errors/bugs.
  - For example `INSERT INTO users VALUES ('John Smith', false);` causes an error.
- Each column has to have a value in `VALUES` or itwill return an error.
- If you don't specify which column you're targeting then null/default value will be added.

#### [Adding Rows of Data](https://launchschool.com/books/sql/read/add_data#addingrows)

##### Rows

- AKA 'tuples'
- columns give structure, rows contain the data.

##### Adding a single row

`INSERT INTO users (full_name, enabled) VALUES ('John Smith', false);`

##### Adding multiple rows

`INSERT INTO users (full_name) VALUES ('Jane Smith'), ('Harry Potter');`

- but it's good practice to do each new value on a new line so you can clearly see how many rows you are adding (although with only 2 it's probably not too important):

```
INSERT INTO users (full_name)
           VALUES ('Jane Smith'),
                  ('Harry Potter');
```

- they will be added in that order.

#### [Constraints and Adding Data](https://launchschool.com/books/sql/read/add_data#constraintsdata)

- constraints are set at schema level (so part of DDL), but are concerned with data primarily.

##### Default values

- All obvious.

##### NOT NULL constraints

- 'full_name' for example can't have a default value, but shouldn't be left empty.

##### Unique constraints

##### CHECK constraints

- We may not need the value to be unique, but it should be somethng else, like more than 5, or included in an array of permitted strings.
- At the moment `full_name` can't be NULL. but it could be an empty string. TO prevent this we can use the following:
  - `ALTER TABLE users ADD CHECK (full_name <> '');`
- In SQL `<>` is like `!=`

##### Quote marks

- need to be escaped with a second quote mark: `'O''Leary'`

#### [Summary](https://launchschool.com/books/sql/read/add_data#summary)



#### [Exercises](https://launchschool.com/books/sql/read/add_data#exercises)

1. Make sure you are connected to the `encyclopedia` database. Add the following data to the `countries` table:

|Name|	Capital|	Population|
| :---: | :---| :---:|
|France|	Paris|	67,158,000|

Solution: 

```
\c encyclopedia
INSERT INTO countries (name, capital, population)
             VALUES ('France', 'Paris', 67158000);
```


2. Now add the following additional data to the countries table:

|Name|	Capital|	Population|
| :---: | :---| :---:|
|USA|	Washington D.C.|	325,365,189|
|Germany|	Berlin|	82,349,400|
|Japan|	Tokyo|	126,672,000|

Solution:

```
INSERT INTO countries (name, capital, population)
              VALUES ('USA', 'Washington D.C', 325365189),
                     ('Germany', 'Berlin', 82349400),
                     ('Japan', 'Tokyo', 126672000);
```

3. Add an entry to the `celebrities` table for the singer and songwriter Bruce Springsteen, who was born on September 23rd 1949 and is still alive.

Solution:

```
INSERT INTO celebrities (first_name, occupation, date_of_birth, deceased, last_name)
              VALUES ('Bruce', 'singer/song-writer', '1949-09-23', false, 'Springsteen');
```

4. Add an entry for the actress Scarlett Johansson, who was born on November 22nd 1984. Use the default value for the `deceased` column.

Solution:

```
INSERT INTO celebrities (first_name, occupation, date_of_birth, last_name)
                   VALUES ('Scarlett', 'actor', '1984-11-22', 'Johansson');
```

5. Add the following two entries to the `celebrities` table with a single INSERT statement. For Frank Sinatra set `true` as the value for the `deceased` column. For Tom Cruise, don't set an explicit value for the `deceased` column, but use the default value.

|First Name|Last Name|Occupation|	D.O.B.|
| :---: | :---: | :---: | :---: 
| Frank	Sinatra	|Singer| Actor|	December 12, 1915|
|Tom	Cruise|	Actor|	July 03, 1962|

Solution:

```
INSERT INTO celebrities (first_name, last_name, occupation, date_of_birth, deceased)
                VALUES ('Frank', 'Sinatra', 'Singer, Actor', '1915-12-12', true),
                       ('Tom', 'Cruise', 'Actor', '1962-07-03', DEFAULT);
```

6. Look at the schema of the celebrities table. What do you think will happen if we try to insert the following data?

Solution: An error, because `last_name` cannot be null.

7. Update the `last_name` column of the `celebrities` table so that the data in the previous question can be entered, and then add the data to the table.

Solution:

```
INSERT INTO celebrities (first_name, last_name, occupation, date_of_birth, deceased)
                VALUES ('Madonna', '', 'Singer, Actress', '1968-08-16', false),
                       ('Prince', '', 'singer-songwriter-actor-musician', '1958-07-06', true);
```


8. Check the schema of the celebrities table. What would happen if we specify a NULL value for deceased column, such as with the data below?

Solution: If you specify NULL, it overrides the default.

(but you shouldn't have anything other than true or false in a boolean field.

9. Check the schema of the `animals` table. What would happen if we tried to insert the following data to the table?

Solution: The problem is some of the max_weights are ints rather than decimals. The correct entry is the following: 
WRONG - decimals can be whole numbers. The problem is pidgeons and doves share the same binomial name, but that field has to be unique.

LS Solution:
```
ALTER TABLE animals 
  DROP CONSTRAINT unique_binomial_name;

INSERT INTO animals (name, binomial_name, max_weight_kg, max_age_years, conservation_status)
             VALUES ('Dove', 'Columbidae Columbiformes', 2, 15, 'LC'),
                    ('Golden Eagle', 'Aquila Chrysaetos', 6.35, 24, 'LC'),
                    ('Peregrine Falcon', 'Falco Peregrinus', 1.5, 15, 'LC'),
                    ('Pigeon', 'Columbidae Columbiformes', 2, 15, 'LC'),
                    ('Kakapo', 'Strigops habroptila', 4, 60,'CR');
```

10. Connect to the `ls_burger` database and examine the schema for the `orders` table.

Based on the table schema and following information, write and execute an INSERT statement to add the appropriate data to the orders table.

There are three customers -- James Bergman, Natasha O'Shea, Aaron Muller. James' email address is james1998@email.com. Natasha's email address is natasha@osheafamily.com. Aaron doesn't supply an email address.

James orders a LS Chicken Burger, Fries and a Cola. Natasha has two orders -- an LS Cheeseburger with Fries but no drink, and an LS Double Deluxe Burger with Onion Rings and a Chocolate Shake. Aaron orders an LS Burger with no side or drink.

The item costs and loyalty points are listed below:

Item	Cost ($)	Loyalty Points
LS Burger	3.00	10
LS Cheeseburger	3.50	15
LS Chicken Burger	4.50	20
LS Double Deluxe Burger	6.00	30
Fries	0.99	3
Onion Rings	1.50	5
Cola	1.50	5
Lemonade	1.50	5
Vanilla Shake	2.00	7
Chocolate Shake	2.00	7
Strawberry Shake	2.00	7

Solution:

```
INSERT INTO orders (customer_name,  burger, side, drink, customer_email, customer_loyalty_points, burger_cost, side_cost, drink_cost)
             VALUES ('James Bergman', 'LS Chicken Burger', 'Fries', 'Cola', 'james1998@email.com', 28, 4.50, 0.99, 1.50),
                    ('Natasha O''Shea', 'LS Cheeseburger', 'Fries', NULL, 'natasha@osheafamily.com', 18, 3.50, 0.99, DEFAULT),
                    ('Natasha O''Shea', 'LS Double Deluxe Burger', 'Onion Rings', 'Chocolate Shake', 'natasha@osheafamily.com', 42, 6.00, 1.50, 2.00),
                    ('Aaron Muller', 'LS Burger', NULL, NULL, NULL, 10, 3.00, DEFAULT, DEFAULT);
```


### [9.Select Queries](https://launchschool.com/books/sql/read/select_queries)

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
