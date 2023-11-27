# [Introduction to SQL](https://launchschool.com/books/sql)

## GETTING STARTED

### [1. Introduction](https://launchschool.com/books/sql/read/introduction)
#### [The importance of data](https://launchschool.com/books/sql/read/introduction#data)

- When it comes to the human ability to understand and remember large amounts of information there are hard limits. We can surpass these with our ability to handle large amounts of information on databases.
  - collecting data.
  - organizing it.
  - studying it.
  - looking for patterns and meaning.
- In order to do this we need to store it in a structured way that lends itself to studying.
- Video of Hans Rosling interpreting life-expectancy data in 20th century.

#### [Structured Data](https://launchschool.com/books/sql/read/introduction#structureddata)

- Structured data aims to solve the problem of unstructured data. Unstructured data is like a notice-board.
- In small amounts, unstructured data is fine. The larger the data, the more unwieldy it becomes. Think about searching through a notebook for a single quote.
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
    - `CREATE`
    - `ALTER`
    - `DROP
    - `RENAME`
  - Data Manipulation Language (DML): Used to retrieve or modify data stored in a database.
    - `SELECT`
    - `INSERT`
    - `UPDATE`
    - `DELETE`
  - Data Control Language (DCL): Used to deteremine what various users are allowed to do when interacting with a database.
    - `GRANT`
    - `REVOKE`
    - `DENY`
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
  - Acceptable forms of booleans:
    - 't' and 'f'
    - true and false
    - 'true' and 'false'
    - 'y' and 'n'
    - 'yes' and 'no'
    - 'on' and 'off'
    - '1' and '0'
  - So basically only true and false can be valid without quote-marks.
- INT or integer: just an int
- decimal(precision, scale): 'precision' is total digits in the entire number, both sides of the decimal. 'scale' is total of digits to the right of the decimal.
- timestamp: contains date and time like this YYYY-MM-DD HH:MM:SS
- data: as above, but without the time.
- Real: stores single-precision floating point numbers.

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


- THIS SECTION IS REALLY VAGUE AND INCOMPLETE, SO HERE ARE SOME EXAMPLES THAT WORK:

- `ALTER TABLE films ADD CONSTRAINT title_unique UNIQUE (title);`
- `ALTER TABLE films ALTER COLUMN year SET NOT NULL;`
- `ALTER TABLE films DROP CONSTRAINT title_unique;`
- `ALTER TABLE films ADD CONSTRAINT title_length CHECK (length(title) >= 1);`
- `ALTER TABLE films ADD CONSTRAINT year_range CHECK (year BETWEEN 1900 AND 2100);`
- `ALTER TABLE films DROP CONSTRAINT films_pkey;`

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

#### [Select Query Syntax](https://launchschool.com/books/sql/read/select_queries#selectquerysyntax)

```
SELECT column_name, ...
  FROM table_name
  WHERE condition;
```

```
SELECT enabled, full_name FROM users
WHERE id < 2;
```
##### Identifiers and key words

- SQL is case-sensitive
- SQL assumes anything that is not a keyword/operator/function is an identifier. (sort of like a ruby variable?)
- For example, `year` is a reserved word in SQL, so to name a column that we would need to write `"year"`, but it's generally a bad idea to use reserved names as identifiers.

#### [ORDER BY](https://launchschool.com/books/sql/read/select_queries#ordering)

```
SELECT column_name, ...
       FROM table_name
       WHERE condition
       ORDER BY column_name;
```

- has to come after `FROM` and if there's a `WHERE`, after that too.

```
SELECT full_name, enabled FROM users
ORDER BY enabled;
```

- for booleans, false comes before true. Within the `true`s order is arbitrary.
- `ASC` and `DESC` for ascending and descending orders. Default is ascending.

```
SELECT full_name, enabled FROM users
ORDER BY enabled DESC;
```

- We can have a second level of ordering, for values that are the same when sorted by the first value. ie. if `enabled` is the same, then order by `id`:

```
SELECT full_name, enabled FROM users
ORDER BY enabled DESC, id DESC;
```

- You can order by a column even if it's not included in the output.
- You can set a different sort order for different columns.

#### [Operators](https://launchschool.com/books/sql/read/select_queries#operators)

- usually part of a `WHERE` clause.
- Here we'll be putting them in a `select` query in three categories:

1. Comparison.
2. Logical.
3. String Matching.

##### Comparison operators

- `<`
- `>`
- `<=`
- `>=`
- `=` for comparison, not assignment
- `<>` or `!=`

```
SELECT full_name, enabled, last_login
       FROM users
       WHERE id >= 2;
```

- There are also comparison predicates (not discussed in this book, except the last 2):
  - `BETWEEN`
  - `NOT BETWEEN`
  - `IS DISTINCT FROM`
  - `IS NOT DISTINCT FROM`
  - `IS NULL`
  - `IS NOT NULL`

- `NULL` is special. You can't say `WHERE column_name = NULL`, you have to say `IS NULL`

```
SELECT * FROM my_table WHERE my_column IS NULL;
```

##### Logical operators

- `AND`
- `OR`
- `NOT` (seldom used)

```
SELECT * FROM users
         WHERE full_name = 'Harry Potter'
            OR enabled = 'false';
```

```
SELECT * FROM users
         WHERE full_name = 'Harry Potter'
           AND enabled = 'false';
```

##### String matching operators

- `LIKE` (case-sensitive)
- 'ILIKE` (case sensitive)

```
SELECT * FROM users WHERE full_name LIKE '%Smith';
```

- `%` is any number of characters followed by [string]. It will need a `%` at the end as well if you need it to scan before the matched-string!
- `_` is a single character followed by [string]
- `SIMILAR TO` is also available but compares to a Regex.

#### [Summary](https://launchschool.com/books/sql/read/select_queries#summary)

#### [Exercises](https://launchschool.com/books/sql/read/select_queries#exercises)


1. Make sure you are connected to the `encyclopedia` database. Write a query to retrieve the population of the USA.

Solution:

```
SELECT population FROM countries WHERE name = 'USA';
```

2. Write a query to return the population and the capital (with the columns in that order) of all the countries in the table.

Solution:

```
SELECT population, capital FROM countries;
```

3. Write a query to return the names of all the countries ordered alphabetically.

Solution:

```
SELECT name FROM countries ORDER BY name;
```

4. Write a query to return the names and the capitals of all the countries in order of population, from lowest to highest.

Solution:

```
SELECT name, capital FROM countries ORDER BY population;
```

5. Write a query to return the same information as the previous query, but ordered from highest to lowest.

Solution:

```
SELECT name, capital FROM countries ORDER BY population DESC;
```

6. Write a query on the `animals` table, using `ORDER BY`, that will return the following output:


       name       |      binomial_name       | max_weight_kg | max_age_years
------------------+--------------------------+---------------+---------------
 Peregrine Falcon | Falco Peregrinus         |        1.5000 |            15
 Pigeon           | Columbidae Columbiformes |        2.0000 |            15
 Dove             | Columbidae Columbiformes |        2.0000 |            15
 Golden Eagle     | Aquila Chrysaetos        |        6.3500 |            24
 Kakapo           | Strigops habroptila      |        4.0000 |            60
(5 rows)

Use only the columns that can be seen in the above output for ordering purposes.

Solution:

```
SELECT name, binomial_name, max_weight_kg, max_age_years FROM animals ORDER BY max_age_years, max_weight_kg, name DESC;
```

7. Write a query that returns the names of all the countries with a population greater than 70 million.

Solution:

```
SELECT name FROM countries WHERE population > 70000000;
```

8. Write a query that returns the names of all the countries with a population greater than 70 million but less than 200 million.

Solution:

```
SELECT name FROM countries WHERE population > 70000000 AND population < 200000000;
```

9. Write a query that will return the first name and last name of all entries in the celebrities table where the value of the deceased column is not true.

Solution:

```
SELECT first_name, last_name FROM celebrities WHERE deceased = false OR deceased IS NULL;
```

10. Write a query that will return the first and last names of all the celebrities who sing.

Solution:

```
SELECT first_name, last_name FROM celebrities WHERE occupation ILIKE '%sing%';
```

11. Write a query that will return the first and last names of all the celebrities who act.

Solution:

```
SELECT first_name, last_name FROM celebrities WHERE occupation ILIKE '%act%';
```

LS prefers, the following because when scanning for strings it's best to be as specific as possible, to exclude any wrong matches:

```
SELECT first_name, last_name
FROM celebrities
WHERE occupation LIKE '%Actor%'
OR occupation LIKE '%Actress%';
```

12. Write a query that will return the first and last names of all the celebrities who both sing and act.

Solution:

```
SELECT first_name, last_name
FROM celebrities
WHERE (occupation LIKE '%Actor%'
OR occupation LIKE '%Actress%')
AND occupation ILIKE '%sing%';
```


13. Connect to the `ls_burger` database. Write a query that lists all of the burgers that have been ordered, from cheapest to most expensive, where the cost of the burger is less than $5.00.

Solution:

```
SELECT burger FROM orders WHERE burger_cost <= 5.00 ORDER BY burger_cost;
```

14. Write a query to return the customer name and email address and loyalty points from any order worth 20 or more loyalty points. List the results from the highest number of points to the lowest.

Solution:

```
SELECT customer_name, customer_email, customer_loyalty_points
FROM orders
WHERE customer_loyalty_points >= 20
ORDER BY customer_loyalty_points DESC;
```

15. Write a query that returns all the burgers ordered by Natasha O'Shea.

Solution:

```
SELECT burger FROM orders WHERE customer_name = 'Natasha O''Shea';
```

16. Write a query that returns the customer name from any order which does not include a drink item.

Solution:

```
SELECT customer_name FROM orders WHERE drink IS NULL;
```

17. Write a query that returns the three meal items for any order which does not include fries.

Solution:

```
SELECT burger, side, drink
FROM orders
WHERE side <> 'Fries'
OR side IS NULL;
```

18. Write a query that returns the three meal items for any order that includes both a side and a drink.

Solution:

```
SELECT burger, side, drink
FROM orders
WHERE side IS NOT NULL
AND drink IS NOT NULL;
```

### [10. More on Select](https://launchschool.com/books/sql/read/more_on_select)

- here we further filter our data by usinf `LIMIT`, `OFFSET` and `DISTINCT`.

#### [LIMIT and OFFSET](https://launchschool.com/books/sql/read/more_on_select#limitoffset)

- for limiting the data returned beyond the conditions already stated.
- For example displaying portions of the data as separate pages. ("pagination")

##### Pagination

- `SELECT * FROM users LIMIT 1;` limits by `id`.
- We skip the first fow with `OFFSET`: `SELECT * FROM users LIMIT 1 OFFSET 1;`
- An example:

```
SELECT topic, author, publish_date, category,
       replies_count, likes_count, last_activity_date
    FROM posts
    LIMIT 12
    OFFSET 12;
```

- `LIMIT` can also be useful during development for preview a little bit of the data.

#### [DISTINCT](https://launchschool.com/books/sql/read/more_on_select#distinct)

- For the problem of duplicate data. Often happens when working with multiple tables.
- Like this `SELECT DISTINCT full_name FROM users;`
- We can use it together with SQL functions, like this: `SELECT count(DISTINCT full_name) FROM users;`

#### [Functions](https://launchschool.com/books/sql/read/more_on_select#functions)

- like Ruby methods.
- Three types:
  - String
  - Date/time
  - Aggregate

##### String Functions

- `length`
- `trim` - removes leading whitespace

##### Data/time functions

- `date_part`
- `age`

##### Aggregate functions

- `count`
- `sum`
- `min`
- `max`
- `avg`
- These become really useful when grouping table-rows together

#### [GROUP BY](https://launchschool.com/books/sql/read/more_on_select#groupby)

- `SELECT enabled, count(id) FROM users GROUP BY enabled;`
- The columns included in the column list, have to be included in teh `GROUP BY`clause. SO the following would return an error:

```
SELECT enabled, full_name, count(id)
       FROM users
       GROUP BY enabled;   -- full_name is not grouped
```
##### [Ian Austin article](https://medium.com/@iandaustin/grokking-group-by-bd0bfd7082ea)

#### [Summary](https://launchschool.com/books/sql/read/more_on_select#summary)

#### [Exercises](https://launchschool.com/books/sql/read/more_on_select#exercises)


1. Make sure you are connected to the `encyclopedia` database. Write a query to retrieve the first row of data from the `countries` table.

Solution:

```
SELECT * FROM countries LIMIT 1;
```

2. Write a query to retrieve the name of the country with the largest population.

Solution:

```
SELECT name FROM countries
ORDER BY population DESC
LIMIT 1;
```

3. Write a query to retrieve the name of the country with the second largest population.

Solution:

```
SELECT name FROM countries
ORDER BY population DESC
LIMIT 1 OFFSET 1;
```

4. Write a query to retrieve all of the unique values from the `binomial_name` column of the `animals` table.

Solution:

```
SELECT DISTINCT binomial_name FROM animals;
```

5. Write a query to return the longest binomial name from the `animals` table.

Solution:

```
SELECT binomial_name
FROM animals
ORDER BY length(binomial_name) DESC
LIMIT 1;
```

6. Write a query to return the first name of any celebrity born in 1958.

Solution:

```
SELECT first_name
FROM celebrities
WHERE date_part('year', date_of_birth) = 1958
;
```

7. Write a query to return the highest maximum age from the animals table.

Solution:

```
SELECT max_age_years
FROM animals
ORDER BY max_age_years DESC
LIMIT 1
;
```

LS solution: `SELECT max(max_age_years) FROM animals;`

8. Write a query to return the average maximum weight from the `animals` table.

Solution: `SELECT avg(max_weight_kg) FROM animals;`

9. Write a query to return the number of rows in the `countries` table.

Solution:

```
SELECT count(id) FROM countries;
```

10. Write a query to return the total population of all the countries in the `countries` table.

Solution:

```
SELECT sum(population) FROM countries;
```

11. Write a query to return each unique conservation status code alongside the number of animals that have that code.

Solution:

```
SELECT conservation_status, count(conservation_status)
FROM animals
GROUP BY conservation_status;
```

- LS solution was to use `count(id)`, but i don't think it makes a difference.

12. Connect to the `ls_burger` database. Write a query that returns the average burger cost for all orders that include fries.

Solution:

```
SELECT avg(burger_cost)
FROM orders
WHERE side = 'Fries'
;
```

13. Write a query that returns the cost of the cheapest side ordered.

Solution:

```
SELECT min(side_cost) FROM orders
WHERE side_cost > 0
;
```

LS did `IS NOT NULL` at the end.

14. Write a query that returns the number of orders that include Fries and the number of orders that include Onion Rings.

Solution:

```
SELECT side, count(id)
FROM orders
WHERE side = 'Fries'
OR side = 'Onion Rings'
GROUP BY side;
```

### [11. Update Data in a Table](https://launchschool.com/books/sql/read/update_and_delete_data)

#### [Updating Data](https://launchschool.com/books/sql/read/update_and_delete_data#updatingdata)

```
UPDATE table_name
SET column_name = value, ...
WHERE expression;
```

- Without the `WHERE` clause it'll update every row.
- This can be bad, so maybe check with a `SELECT` query first.

##### Update all rows

- we might disable users' ability to change things in response to a security issue. Like this: `UPDATE users SET enabled = false;`

##### Update specific rows

- More often you'll specify which rows with a `WHERE` clause.

```
UPDATE users SET enabled = true
             WHERE full_name = 'Harry Potter'
                OR full_name = 'Jane Smith';
```

```
UPDATE users SET full_name='Alice Walker' WHERE id=2;
```

#### [Deleting Data](https://launchschool.com/books/sql/read/update_and_delete_data#deletingdata)

- `DELETE FROM table_name WHERE expression;`

##### Delete specific rows

```
DELETE FROM users
WHERE full_name='Harry Potter' AND id > 3;
```

- Here using the name column as well as the id column gives the command extra protection.

#### Delete all rows

- Be careful! `DELETE FROM users;`

#### [Update vs Delete](https://launchschool.com/books/sql/read/update_and_delete_data#updatevsdelete)

- `DELETE` if fow whole rows. `UPDATE` can be more precise.
- The closest you can do for deleting specific values is update them to NULL. Like this:

```
UPDATE table_name SET column_name1 = NULL
WHERE expression;
```

- Here `=` is assignment, but in a `WHERE` clause it would be comparison.
- If a column has a `NOT NULL` constraint then it's not possible to change it to `NULL`.

#### [Use Caution](https://launchschool.com/books/sql/read/update_and_delete_data#usecaution)

- You almost never want to update/delete ALL the values. So if the statement doesn't have a `WHERE` clause, be really sure.
- Even with a `WHERE` clause, excercise caution.
- It's normal to use a `SELECT` clause to test first.

#### [Summary](https://launchschool.com/books/sql/read/update_and_delete_data#summary)

#### [Exercises](Exercises)


1. Make sure you are connected to the `encyclopedia` database. Add a column to the `animals` table called `class` to hold strings of up to 100 characters.

Update all the rows in the table so that this column holds the value `Aves`.

Solution:

```
ALTER TABLE animals
ADD COLUMN class
varchar(100);

UPDATE
animals
SET class = 'Aves';
```

2. Add two more columns to the `animals` table called `phylum` and `kingdom`. Both should hold strings of up to 100 characters.

Update all the rows in the table so that `phylum` holds the value `Chordata` and `kingdom` holds `Animalia` for all the rows in the table.

Solution:

```
ALTER TABLE animals
ADD COLUMN phylum varchar(100),
ADD COLUMN kingdom varchar(100);

UPDATE animals
SET phylum = 'Chordata', kingdom = 'Animalia';
```

3. Add a column to the `countries` table called `continent` to hold strings of up to 50 characters.

Update all the rows in the table so France and Germany have a value of `Europe` for this column, Japan has a value of `Asia` and the USA has a value of `North America`.

Solution:

```
ALTER TABLE countries
ADD COLUMN continent varchar(50);

UPDATE countries SET continent = 'Europe' WHERE name = 'France' OR name = 'Germany';
UPDATE countries SET continent = 'Asia' WHERE name = 'Japan';
UPDATE countries SET continent = 'North America' WHERE name = 'USA';
```

4. In the `celebrities` table, update the Elvis row so that the value in the `deceased` column is true. Then change the column so that it no longer allows `NULL` values.

Solution:

```
UPDATE celebrities SET deceased = true WHERE first_name = 'Elvis';
ALTER TABLE celebrities ALTER COLUMN deceased SET NOT NULL;
```

5. Remove Tom Cruise from the `celebrities` table.

Solution:

```
DELETE FROM celebrities WHERE first_name = 'Tom' AND last_name = 'Cruise';
```

6. Change the name of the `celebrities` table to `singers`, and remove anyone who isn't a singer.

Solution:

```
ALTER TABLE celebrities RENAME TO singers;
DELETE FROM singers WHERE occupation NOT ILIKE '%sing%';
```

7. Remove all the rows from the `countries` table.

Solution:

```
DELETE FROM countries;
```

8. Connect to the `ls_burger` database. Change the drink on James Bergman's order from a Cola to a Lemonade.

Solution:

```
UPDATE orders SET drink = 'Lemonade' WHERE customer_name ILIKE '%James%';
```

9.Add Fries to Aaron Muller's order. Make sure to add the cost ($0.99) to the appropriate field and add 3 loyalty points to the current total.

Solution:

```
UPDATE orders SET side = 'Fries', side_cost = '0.99', customer_loyalty_points = 13 WHERE customer_name ILIKE '%James%';
```

10. The cost of Fries has increased to $1.20. Update the data in the table to reflect this.

Solution:

```
UPDATE orders SET side_cost = '1.20' WHERE side = 'Fries';
```

## WORKING WITH MULTIPLE TABLES

### [12. Create Multiple Tables](https://launchschool.com/books/sql/read/table_relationships)

#### [Normalization](https://launchschool.com/books/sql/read/table_relationships#normalization)

- This topic goes deep. Here we cover the basics.
  - We normalize to reduce data redundancy and improve data integrity.
    - This means ensure that there are fewer chances for mis-entering data and less need for repetition.
  - We normalize by arranging data in multiple tables and defining relationships between them.

#### [Database Design](https://launchschool.com/books/sql/read/table_relationships#databasedesign)

- defining 'entities'.
- designing 'relationships'.

##### Entitites

- A real world object that we want to model within our data-base.
- major nouns.
- In the real-world data from an entity would probably exist over many databases. Here we will have 1 entity to 1 table of data.
- Our sql_books entities:
  - a user.
  - a book.
  - checkouts. This is a third entity that exists between users and books.
  - reviews
  - addresses. This could be part of the 'users' entity.


![Screenshot 2023-10-22 at 10 35 03](https://github.com/SandyRodger/launch_school_books/assets/78854926/87afe16c-8470-4a72-9af3-65a8bbb2c379)

##### Relationships

![Screenshot 2023-10-22 at 10 41 21](https://github.com/SandyRodger/launch_school_books/assets/78854926/3852a50a-50c8-464b-a37f-869d90ae8658)

- ERD: Entity relationship diagram

#### [Keys](https://launchschool.com/books/sql/read/table_relationships#keys)

- Keys are a type of constraint.
- Primary Keys
- Foreign Keys

##### Primary keys

- A primary key is a unique identifier for a row of data.
- In order for it to be unique it has to be `NOT NULL` and `UNIQUE`. Making a column `PRIMARY KEY` automatically adds these constraints.

```
ALTER TABLE users ADD PRIMARY KEY (id);
```

- Each table can only have 1 primary key.
- It's usually a column called `id`.

##### Foreign keys

- Allows us to associate a row in one table with a row in another table.
- We do this by setting the column in one table as primary key, and a column in another table as foreign key and having the foreign reference the primary.
- We do this with `REFERENCES`.

```
FOREIGN KEY (fk_col_name)
REFERENCES target_table_name (pk_col_name);
```

- Think of this as creating a linear relationship between the tables.

![Screenshot 2023-10-22 at 11 02 46](https://github.com/SandyRodger/launch_school_books/assets/78854926/5b04e86a-9627-492a-b005-17a66f722f96)

- referencial integrity: the ensuring that a column within a record must reference an existing value. If it doesn't an error is thrown.
- In order to implement our schema properly we should explicitly describe the types of relationships we want:
  - A user can have 1 address. An address can have 1 user.
  - A review is for 1 book. A book can have many reviews.
  - A user can have many books checked out/returned. A book can be/have been checked-out by many users.
- These are 3 relationship types:
  - one-to-one.
  - one-to-many.
  - many-to-many.

#### [One-to-One](https://launchschool.com/books/sql/read/table_relationships#onetoone)

- Example: a user can have one address, a single address could apply to several users.
- Implementation: the `PRIMARY KEY` is used as both `PRIMARY KEY` and `FOREIGN KEY` of the addresses table.

```
/*
one-to-one: User has one address
*/

CREATE TABLE addresses (
  user_id int, -- Both a primary and foreign key
  street varchar(30) NOT NULL,
  city varchar(30) NOT NULL,
  state varchar(30) NOT NULL,
  PRIMARY KEY (user_id),
  FOREIGN KEY (user_id)
      REFERENCES users (id)
      ON DELETE CASCADE
);
```

```
INSERT INTO addresses
         (user_id, street, city, state)
  VALUES (1, '1 Market Street', 'San Francisco', 'CA'),
         (2, '2 Elm Street', 'San Francisco', 'CA'),
         (3, '3 Main Street', 'Boston', 'MA');
```

#### [Referential Integrity](https://launchschool.com/books/sql/read/table_relationships#referentialintegrity)

- Example: the constraints we've added to our addresses table enforce a 1 to 1 relationship between it and `users`.
- Entering another user into `addresses` with an existing `id` will throw an error.
- Entering a new address with an `id` that doesn't exist in `users` will throw an error.
- This is due to the "modality" of the relationship between the two entitites. You can not understand that word for the moment. It's an aspect of entity relationships.

##### The ON DELETE clause

- `ON DELTETE CASCADE` means if the row being referenced is deleted then delete the row it references also.
- Alternatives to `CASCADE` are `SET NULL` and `SET DEFAULT`.
- Determining what to do when references are deleted is an important part of design.

#### [One-to-Many](https://launchschool.com/books/sql/read/table_relationships#onetomany)

- Can't be the other way around.
- Example: a review belongs to one book. A book has many reviews.

```
CREATE TABLE books (
  id serial,
  title varchar(100) NOT NULL,
  author varchar(100) NOT NULL,
  published_date timestamp NOT NULL,
  isbn char(12),
  PRIMARY KEY (id),
  UNIQUE (isbn)
);

/*
 one-to-many: Book has many reviews
*/

CREATE TABLE reviews (
  id serial,
  book_id integer NOT NULL,
  reviewer_name varchar(255),
  content varchar(255),
  rating integer,
  published_date timestamp DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (id),
  FOREIGN KEY (book_id)
      REFERENCES books(id)
      ON DELETE CASCADE
);

INSERT INTO books
  (id, title, author, published_date, isbn)
  VALUES
      (1, 'My First SQL Book', 'Mary Parker',
          '2012-02-22 12:08:17.320053-03',
          '981483029127'),
      (2, 'My Second SQL Book', 'John Mayer',
          '1972-07-03 09:22:45.050088-07',
          '857300923713'),
      (3, 'My First SQL Book', 'Cary Flint',
          '2015-10-18 14:05:44.547516-07',
          '523120967812');

INSERT INTO reviews
  (id, book_id, reviewer_name, content, rating,
       published_date)
  VALUES
      (1, 1, 'John Smith', 'My first review', 4,
          '2017-12-10 05:50:11.127281-02'),
      (2, 2, 'John Smith', 'My second review', 5,
          '2017-10-13 15:05:12.673382-05'),
      (3, 2, 'Alice Walker', 'Another review', 1,
          '2017-10-22 23:47:10.407569-07');
```

- The order in which we add data is important. The data has to exist in order to be referenced.

#### [Many-to-Many](https://launchschool.com/books/sql/read/table_relationships#manytomany)

- Example: a user can check out many books and a book can be checked out by many users.
- We do this with two one-to-many relationships, using a third cross-reference table (AKA a join table).
- It can be helpful to think of them as 2 one-to-many relationships combined.
- The join table holds the relationship between the two entities by having two `FOREIGN KEY`s each of which references the `PRIMARY KEY` of one table.

![Screenshot 2023-10-22 at 12 20 51](https://github.com/SandyRodger/launch_school_books/assets/78854926/58ca4649-771e-4960-81e5-729267b09797)

```
CREATE TABLE checkouts (
  id serial,
  user_id int NOT NULL,
  book_id int NOT NULL,
  checkout_date timestamp,
  return_date timestamp,
  PRIMARY KEY (id),
  FOREIGN KEY (user_id) REFERENCES users(id)
                        ON DELETE CASCADE,
  FOREIGN KEY (book_id) REFERENCES books(id)
                        ON DELETE CASCADE
);
```

- the `FOREIGN KEY`` in many-to-many relationships should never alow `NULL`, because it makes no sense to have a check-out entry if the book hasn't been checked out by a specific user.

```
INSERT INTO checkouts
  (id, user_id, book_id, checkout_date, return_date)
  VALUES
    (1, 1, 1, '2017-10-15 14:43:18.095143-07',
              NULL),
    (2, 1, 2, '2017-10-05 16:22:44.593188-07',
              '2017-10-13 13:0:12.673382-05'),
    (3, 2, 2, '2017-10-15 11:11:24.994973-07',
              '2017-10-22 17:47:10.407569-07'),
    (4, 5, 3, '2017-10-15 09:27:07.215217-07',
              NULL);
```

#### [Summary](https://launchschool.com/books/sql/read/table_relationships#summary)

#### [Exercises](https://launchschool.com/books/sql/read/joins#exercises)

1. Solution:

```
CREATE TABLE continents (
  id serial PRIMARY KEY,
  continent_name varchar(50)
);

ALTER TABLE countries DROP COLUMN continent;

ALTER TABLE countries
      ADD COLUMN continent_id integer;

ALTER TABLE countries
      ADD FOREIGN KEY (continent_id)
      REFERENCES continents(id);
```

2. Solution:

```
INSERT INTO countries (name, capital, population, continent)
                 VALUES ('France', 'Paris', 67158000, 'Europe'),
                        ('USA', 'Washington D.C.', 325365189, 'North America'),
                        ('Germany', 'Berlin', 82349400, 'Europe'),
                        ('Japan', 'Tokyo', 126672000, 'Asia'),
                        ('Egypt', 'Cairo', 96308900, 'Africa'),
                        ('Brazil', 'Brasilia', 208385000, 'South America')
                       ;
```

LS solution:

```
INSERT INTO continents (continent_name) VALUES
('Africa'),
('Asia'),
('Europe'),
('North America'),
('South America');

INSERT INTO countries (name, capital, population, continent_id)
VALUES ('Brazil', 'Brasilia', 208385000, 5),
('Egypt', 'Cairo', 96308900, 1),
('France', 'Paris', 67158000, 3),
('Germany', 'Berlin', 82349400, 3),
('Japan', 'Tokyo', 126672000, 2),
('USA', 'Washington D.C.', 325365189, 4);
```

3. Solution:

WRONG:

```
CREATE TABLE albums (
  id serial PRIMARY KEY,
  album_name varchar(100),
  released date,
  genre varchar(100),
  label varchar(100),
  singer_id int,                   # => one to one needs no PRIMARY KEY here
  FOREIGN KEY (singer_id)
    REFERENCES singers (id)
);
 
ALTER TABLE singers      # = > this is wrong, but why? Is UNIQUE not a constraint that one can apply to a column?
      ALTER COLUMN id
      SET UNIQUE;

INSERT INTO albums ...
```

LS SOLUTION:

```
ALTER TABLE singers
ADD CONSTRAINT unique_id UNIQUE (id);

CREATE TABLE albums (
id serial PRIMARY KEY,
album_name varchar(100),
released date,
genre varchar(100),
label varchar(100),
singer_id int,
FOREIGN KEY (singer_id) REFERENCES singers(id)
);

INSERT INTO albums (album_name, released, genre, label, singer_id)
VALUES ('Born to Run', '1975-08-25', 'Rock and roll', 'Columbia', 1),
('Purple Rain', '1984-06-25', 'Pop, R&B, Rock', 'Warner Bros', 6),
('Born in the USA', '1984-06-04', 'Rock and roll, pop', 'Columbia', 1),
('Madonna', '1983-07-27', 'Dance-pop, post-disco', 'Warner Bros', 5),
('True Blue', '1986-06-30', 'Dance-pop, Pop', 'Warner Bros', 5),
('Elvis', '1956-10-19', 'Rock and roll, Rhythm and Blues', 'RCA Victor', 7),
('Sign o'' the Times', '1987-03-30', 'Pop, R&B, Rock, Funk', 'Paisley Park, Warner Bros', 6),
('G.I. Blues', '1960-10-01', 'Rock and roll, Pop', 'RCA Victor', 7);
```

4. Solution:

```
ALTER TABLE users               # => not necessary. How is this different from problem 3?
ADD CONSTRAINT unique_id UNIQUE (id);

CREATE TABLE customers (        # => WRONG
  id int,
  customer_name varchar(100),
  PRIMARY KEY (id),      
  FOREIGN KEY (order_id)
    REFERENCES orders (id)
    ON DELETE CASCADE
);

CREATE TABLE email_addresses (         
  id int,                             # => only missing the PRIMARY KEY key
  customer_email varchar(100),      
  FOREIGN KEY (customer_id)
    REFERENCES customers (id)
    ON DELETE CASCADE
);
```

LS Solution:

```
CREATE TABLE customers (      # => so, we don't need to set a foreign key, because this is the table that other tables reference. It does not look at other tables, it is looked at.
id serial PRIMARY KEY,
customer_name varchar(100)
);

CREATE TABLE email_addresses (                  # => this is looking at the 'customers' table.
customer_id integer PRIMARY KEY,         # If another table is referencing this table, this SETS the key.
customer_email varchar(50),
FOREIGN KEY (customer_id)           # This table is BROADCASTING the key, which is 'customer_id')
REFERENCES customers (id)           # It is found at 'customers' and within that, at  'id'
ON DELETE CASCADE
);

INSERT INTO customers (customer_name)
VALUES ('James Bergman'),
('Natasha O''Shea'),
('Aaron Muller');

INSERT INTO email_addresses (customer_id, customer_email)
VALUES (1, 'james1998@email.com'),
(2, 'natasha@osheafamily.com');
```

5. Solution:

```
CREATE TABLE products (     # => correct, just missing the default 0
id serial PRIMARY KEY,
product_name varchar(50),
product_cost decimal(4,2) DEFAULT 0,
product_type varchar(20),
product_loyalty_points int
);

INSERT INTO products (product_name, product_cost, product_type, product_loyalty_points)
VALUES ('LS Burger', 3.00, 'Burger', 10 ),
('LS Cheeseburger', 3.50, 'Burger', 15 ),
('LS Chicken Burger', 4.50, 'Burger', 20 ),
('LS Double Deluxe Burger', 6.00, 'Burger', 30 ),
('Fries', 1.20, 'Side', 3 ),
('Onion Rings', 1.50, 'Side', 5 ),
('Cola', 1.50, 'Drink', 5 ),
('Lemonade', 1.50, 'Drink', 5 ),
('Vanilla Shake', 2.00, 'Drink', 7 ),
('Chocolate Shake', 2.00, 'Drink', 7 ),
('Strawberry Shake', 2.00, 'Drink', 7);

```

6. Solutiom:

```

# Create an order_items table so that an order can have one or more products associated with it.

CREATE TABLE order_items (
id serial PRIMARY KEY,

);

# Alter the orders table so that we can associate a customer with one or more orders (

ALTER TABLE orders
      ADD FOREGIN KEY (customer_id)
           REFERENCES customers(id)

# we also want to record an order status in this table). Assume that the order_status field of the orders table can hold strings of up to 20 characters.

ALTER TABLE orders
      ADD COLUMN order_status varchar(20)
                 NOT NULL
                 DEFAULT false;

ALTER TABLE orders DROP COLUMN customer_name;

# James has one order, consisting of a Chicken Burger, Fries, Onion Rings, and a Lemonade. It has a status of 'In Progress'.

INSERT INTO orders VALUES (Chicken Burger, Fries, Onion Rings, Lemonade, 'In Progress'); # how to do 2 sides in one order?
INSERT INTO orders VALUES (Fries);
INSERT INTO orders VALUES (Chicken Burger, Fries, Onion Rings, Lemonade, 'In Progress');

# Natasha has two orders. The first consists of a Cheeseburger, Fries, and a Cola, and has a status of 'Placed'; the second consists of a Double Deluxe Burger, a Cheeseburger, two sets of Fries, Onion Rings, a Chocolate Shake and a Vanilla Shake, and has a status of 'Complete'.

# Aaron has one order, consisting of an LS Burger and Fries. It has a status of 'Placed'.

[ OK, i'm peaking]
```

LS solution:

```
DROP TABLE orders;

CREATE TABLE orders (
id serial PRIMARY KEY,
customer_id integer,
order_status varchar(20),
FOREIGN KEY (customer_id)
REFERENCES customers (id)
ON DELETE CASCADE
);

CREATE TABLE order_items (   # is this a join table? It exists to facilitatea many to many relationship between 'orders' and 'products', so yes(?)
id serial PRIMARY KEY,
order_id integer NOT NULL,
product_id integer NOT NULL,
FOREIGN KEY (order_id)
REFERENCES orders (id)
ON DELETE CASCADE,
FOREIGN KEY (product_id)
REFERENCES products (id)
ON DELETE CASCADE
);

INSERT INTO orders (customer_id, order_status)
VALUES (1, 'In Progress'),
(2, 'Placed'),
(2, 'Complete'),
(3, 'Placed');

INSERT INTO order_items (order_id, product_id)
VALUES (1, 3),
(1, 5),
(1, 6),
(1, 8),
(2, 2),
(2, 5),
(2, 7),
(3, 4),
(3, 2),
(3, 5),
(3, 5),
(3, 6),
(3, 10),
(3, 9),
(4, 1),
(4, 5);
```

- Not sure how completely I've understood/internalised/grokked this
  
### [13. SQL Joins](https://launchschool.com/books/sql/read/joins)

- SQL handles queries across many tables like this with JOINs
- These are clausesin SQL statements taht link 2 tables, usually based on the keys that define their relationship.
- Types:
  - INNER
  - LEFT OUTER
  - RIGHT OUTER
  - FULL OUTER
  - CROSS

#### [Join Syntax](https://launchschool.com/books/sql/read/joins#joinsyntax)

```
SELECT table_nameN.column_name, ...
       FROM table_name1
       join_type JOIN table_name2
                 ON join_condition;
```

![Screenshot 2023-10-23 at 11 12 12](https://github.com/SandyRodger/launch_school_books/assets/78854926/a631ff60-5cfb-411e-a05a-ba69b2d0ec3c)

- For this relationship we could run the following command to get a list of colours and their shapes.

```
SELECT colors.color, shapes.shape
       FROM colors
       JOIN shapes
            ON colors.id = shapes.color_id;
```

##### transient tables

- Imagine them as containing all the columns of both tables for the brief momeny they exist.

#### [Types of Joins](https://launchschool.com/books/sql/read/joins#typesofjoins)

- INNER
- LEFT OUTER
- RIGHT OUTER
- FULL OUTER
- CROSS

##### INNER JOIN

- the default

```
SELECT users.*, addresses.*
       FROM users
       INNER JOIN addresses
             ON users.id = addresses.user_id;
```

- I am not concentrating right now.

##### LEFT JOIN 

- AKA `LEFT JOIN OUTER`.

```
SELECT users.*, addresses.*
       FROM users
       LEFT JOIN addresses
            ON users.id = addresses.user_id;
```

##### RIGHT JOIN

- Just like `LEFT JOIN` but the other way around.

```
 SELECT reviews.book_id, reviews.content,
       reviews.rating, reviews.published_date,
       books.id, books.title, books.author
    FROM reviews
    RIGHT JOIN books
          ON reviews.book_id = books.id;
```

##### FULL JOIN

- combination of the two above.

##### CROSS JOIN

- AKA a Cartesian join.
- doesn't need/have an ON clause.
- Rarely used.
- Merges the tables?

```
SELECT * FROM users CROSS JOIN addresses;
```

![Screenshot 2023-10-23 at 12 20 48](https://github.com/SandyRodger/launch_school_books/assets/78854926/ebcf7577-7876-4354-9590-5a5ade3976c7)

#### [Multiple Joins](https://launchschool.com/books/sql/read/joins#multiplejoins)

- It is common to join more than 2 tables.

```
SELECT users.full_name, books.title,
       checkouts.checkout_date
    FROM users
    INNER JOIN checkouts
          ON users.id = checkouts.user_id
    INNER JOIN books
          ON books.id = checkouts.book_id;
```

#### [Aliasing](https://launchschool.com/books/sql/read/joins#aliasing)

- because the query lists can get rather long.
- The above example using aliasing looks like this:

```
SELECT u.full_name, b.title, c.checkout_date
       FROM users AS u
       INNER JOIN checkouts AS c
           ON u.id = c.user_id
       INNER JOIN books AS b
           ON b.id = c.book_id;
```

- You can go one step further by removing the `AS`.

##### Column aliasing

```
SELECT count(id) AS "Number of Books Checked Out"
       FROM checkouts;
```

returns

```
Number of Books Checked Out
-----------------------------
                          4
(1 row)
```

Which makes it easier to read and understand.

#### [Subqueries](https://launchschool.com/books/sql/read/joins#subqueries)

- An alternative to `JOIN`s

```
SELECT u.full_name FROM users u
       WHERE u.id NOT IN (
           SELECT c.user_id FROM checkouts c
       );
```

- This will be returned to in LS180 (oh whoops, that's where i am)

##### Subquery expressions

- `IN`
- `NOT IN`
- `ANY`
- `SOME`
- `ALL`
  
#### [Summary](https://launchschool.com/books/sql/read/joins#summary)


#### [Exercises](https://launchschool.com/books/sql/read/joins#exercises)


1. Connect to the encyclopedia database. Write a query to return all of the country names along with their appropriate continent names.

```
SELECT countries.name, continents.continent_name
FROM countries JOIN continents
ON countries.id = continents.id;  # here is where I made my mistake
```

LS solution:

```
SELECT countries.name, continents.continent_name
FROM countries JOIN continents
ON countries.continent_id = continents.id;
```

2. Write a query to return all of the names and capitals of the European countries.

```
SELECT countries.name, countries.capital
FROM countries JOIN continents
ON continents.continent_name = 'Europe';     #=> Wrong. This just returns all 6 countries and capitals.
``` 

LS solution:

```
SELECT countries.name, countries.capital
FROM countries JOIN continents
ON countries.continent_id = continents.id
WHERE continents.continent_name = 'Europe';
```

3. Write a query to return the first name of any singer who had an album released under the Warner Bros label.

```
SELECT singers.first_name    #=> LS used 'SELECT DISTINCT singers.first_name'
FROM singers JOIN albums
ON singers.id = albums.singer_id
WHERE albums.label = 'Warner Bros';    #=> LS used 'WHERE albums.label LIKE '%Warner Bros%';'
```

4. Write a query to return the first name and last name of any singer who released an album in the 80s and who is still living, along with the names of the album that was released and the release date. Order the results by the singer's age (youngest first).

```
SELECT singers.first_name, singers.last_name 
FROM singers JOIN albums
ON singers.id = albums.singer_id
WHERE albums.released = CAST(1975 AS date);
WHERE (singers.deceased = 'f');                  # => fail
```

LS solution:

```
SELECT singers.first_name, singers.last_name, albums.album_name, albums.released
FROM singers JOIN albums
ON singers.id = albums.singer_id
WHERE albums.released >= '1980-01-01'
AND albums.released < '1990-01-01'
AND singers.deceased = false
ORDER BY singers.date_of_birth DESC;
```

5. Write a query to return the first name and last name of any singer without an associated album entry.

```
SELECT singers.first_name, singers.last_name
FROM singers JOIN albums
ON singers.id = albums.singer_id
WHERE singers.id NOT IN albums.singer_id;          # => give up.
```

```
SELECT singers.first_name, singers.last_name
FROM singers LEFT JOIN albums
ON singers.id = albums.singer_id
WHERE albums.id IS NULL;
```

6. Rewrite the query for the last question as a sub-query.

```
SELECT singers.first_name, singers.last_name      # => not necessary to specify 'singers'
FROM singers
WHERE singers.id NOT IN (SELECT a.singer_id FROM albums a);
```

LS:

```
SELECT first_name, last_name
FROM singers
WHERE id NOT IN (SELECT singer_id FROM albums);
```
7. Connect to the ls_burger database. Return a list of all orders and their associated product items.

```
SELECT *
FROM orders LEFT JOIN products
ON orders.id = products.id;
```

LS:

```
SELECT orders.*, products.*
FROM orders JOIN order_items
ON orders.id = order_items.order_id
JOIN products
ON order_items.product_id = products.id;
```

8. Return the id of any order that includes Fries. Use table aliasing in your query.

```
SELECT o.id
FROM orders AS o JOIN order_items AS oi
ON o.id = oi.order_id

JOIN products AS P
ON oi.product_id = p.id

WHERE p.product_name LIKE 'Fries';
```
- LS solution same as mine.

9. Build on the query from the previous question to return the name of any customer who ordered fries. Return this in a column called 'Customers who like Fries'. Don't repeat the same customer name more than once in the results.

```
SELECT DISTINCT c.customer_name AS "Customers who like Fries"
FROM customers c WHERE c.id IN 

(SELECT o.id
FROM orders AS o JOIN order_items AS oi ON o.id = oi.order_id
                 JOIN products AS p ON oi.product_id = p.id
WHERE p.product_name LIKE 'Fries');
```

10. Write a query to return the total cost of Natasha O'Shea's orders.

```
SELECT o.id, p.product_name, c.customer_name    # => fail
FROM orders AS o JOIN products AS p ON o.id = p.id
FROM customers AS c JOIN oi.product_id
;
```


LS solution:

```
SELECT sum(p.product_cost)
FROM customers AS c JOIN orders as o
ON c.id = o.customer_id
JOIN order_items AS oi
ON o.id = oi.order_id
JOIN products AS p
ON oi.product_id = p.id
WHERE c.customer_name = 'Natasha O''Shea';
```

- Boy, I do not understand this.

11. Write a query to return the name of every product included in an order alongside the number of times it has been ordered. Sort the results by product name, ascending.

LS solution

```
SELECT p.product_name, COUNT(oi.id)
FROM products AS p JOIN order_items AS oi
ON p.id = oi.product_id
GROUP BY p.product_name
ORDER BY p.product_name ASC;
```

## CONCLUSION

- I need to re-do this book. Especially the last 2 pages.

### 14. Summary and Additional Resources

#### [Summary](https://launchschool.com/books/sql/read/resources#summary)

#### [Next Steps](https://launchschool.com/books/sql/read/resources#nextsteps)

#### [Resources](https://launchschool.com/books/sql/read/resources#resources)
