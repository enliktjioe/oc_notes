# Oracle SQL

## Unlocking user account

https://www.oracletutorial.com/oracle-administration/how-to-unlock-a-user-in-oracle/

## Dual

In Oracle 10g release 1 and above, Oracle treats the use of `DUAL` the same as calling a function which simply evaluates the expression  used in the select list. This optimization provides even better  performance than directly accessing the physical `DUAL` table

https://www.oracletutorial.com/oracle-basics/oracle-dual-table/.

## Manipulating Data

https://www.linkedin.com/learning/oracle-database-12c-basic-sql/introduction-to-transactions?u=26110466

Terms

- Transaction = every SQL command in Oracle, must be DML command
- Commit = submit the SQL command into Oracle DB, must be DML command
- Rollback = cancel the SQL command, so it will not be executed in the table, must be DML command
- Queries = retrieving data from database tables
- DDL = Data Definition Language, creating new database objects
  - CREATE
  - ALTER
  - DROP
  - TRUNCATE
- DML = Data Manipulation Language, modifying existing data in your database
  - SELECT
  - INSERT
  - UPDATE
  - DELETE

## Basic SQL clause

- String inside quotation mark 'E%'

  - case sensitive, means 'E%' and 'e%' are different
  - happened in LIKE, IN

- LIKE only for string values

- IN can be used for numeric values

  - also can use NOT IN

- `to_date()` function

  - for example:

    ```sql
    select * from employee
    where hire_date > to_date('01-JAN-2000', 'DD-MON-YYYY')
    ```

- Using `DISTINCT` to eliminate duplicates

  - Example:

    ```sql
    select distinct department_id, salary
    from employees
    ```

- Performing basic numeric calculation inside the SELECT is possible

- Describe the structure of a table using `DESCRIBE <table_name>`



## String, Number, and Date Functions

- LENGTH = get the length of the string value

- SUBSTR = get the character from string values

  - SUBSTR(<col_name>, starting_pos, length)

- CONCAT = combine multiple string values

  - alternative using ||

- LOWER  / UPPER = change the string value to lower/upper case

- INSTR = get the position of the first character inside string values

  - phone_number: 011.44.1344.345268
  - INSTR(phone_number, '5')
  - result = 15 (start with 1, dot(.) character counted)

- RPAD and LPAD = padding from right/left side of string values

  ![](img/oracle_SQL_notes/rpad_lpad.jpg)

- TO_CHAR

  - to convert number into a string and give it specific format
    ![](img/oracle_SQL_notes/to_char.jpg)
  - to format DATE values
    ![](img/oracle_SQL_notes/to_char_date.jpg)
  - to filter DATE values
    ![](img/oracle_SQL_notes/to_char_filter_date.jpg)

- The Special Oracle DUAL table

  - created during the installation of Oracle DB
  - used to select any value without create/specifying database/table

- ROUND = round the number value into certain decimal points, with round up/down values

- TRUNC = truncate the number value from defined position, without rounding the values

- SYSDATE = displaying current date and time

  - combine with TO_CHAR
    ![](img/oracle_SQL_notes/sysdate.jpg)

- SYSTIMESTAMP = get the current timestamp with highest precision

- MONTHS_BETWEEN = calculate how many months have been passed between two distinct dates

  - Example case: get the number of years employed
    ![months_between](img/oracle_SQL_notes/months_between.jpg)

- ADD_MONTHS = add a specified number of months to specific date

  - Example case:

    ```sql
    add_months(sysdate, 2)
    ```





## Joining Table Data

- All types of join
  ![joins](img/oracle_SQL_notes/joins.jpg)

- Oracle join syntax vs ANSI syntax
  ![oracle_vs_ANSI](img/oracle_SQL_notes/oracle_vs_ANSI.jpg)
  - Oracle has different syntax that give same result
  - For compatiblity, it's recommended to use the ANSI syntax



# **Learning Oracle Database 19c - PL/SQL**

https://www.linkedin.com/learning/learning-oracle-database-19c/pl-sql?u=26110466

Instructor: Bob Bryla, Senior Oracle DBA
https://www.linkedin.com/in/bobbryla/

## What is it?

- Programming Language/SQL
- Extens Oracle SQL
- Based on the Ada language
- SQL is declarative: ???here???s what I want to do"
- PL/SQL is procedureal: ???I know exactly how to do this and here???s how I???m going to do it"

## PL/SQL Language Elements

- Loops
- IF ELSE
- Exception Handling
- Storing functions and procedures
- Think it like programming language instead SQL

![pl1](img/oracle_SQL_notes/pl1.png)

![pl2](img/oracle_SQL_notes/pl2.png)

![pl3](img/oracle_SQL_notes/pl3.png)

![pl4](img/oracle_SQL_notes/pl4.png)

Remember:

- SQL: report writing needing simple joins, ad hoc queries
- PL/SQL
  - Complex business logic
  - Stored procedures or functions

## The ANSI SQL language standard

https://www.linkedin.com/learning/learning-oracle-database-19c/the-ansi-sql-language-standard?u=26110466

![pl5](img/oracle_SQL_notes/pl5.png)

## Creating Functions

- Syntax for CREATE function

  - name the function
  - what will it return?

  ![function](img/oracle_SQL_notes/function.png)

## Creating Procedures

- Encapsulated section of PL/SQL or Java code
- Can be anonymous
- Zero or more arguments, but don't return values
  - 
- Can be stored in a package with other stored functions, procedures, and types

## Declaring Variable

![var_declare](img/oracle_SQL_notes/var_declare.png)

![var_declare](img/oracle_SQL_notes/var_declare2.png)

## Declare Cursor

- What is Cursor?
  - a pointer to a private SQL are with metadata for running a SELECT or other DML statement
  - two types: explicit and implicit

- Explicit Cursor

![explicit_cursor](img/oracle_SQL_notes/explicit_cursor.png)

- Implicit Cursor

![implicit_cursor](img/oracle_SQL_notes/implicit_cursor.png)

- Built-In  Cursor

![builtin](img/oracle_SQL_notes/built-in_cursor.png)



## Using SQL SELECT Statement

- Static SQL Statement

![static](img/oracle_SQL_notes/static_sql.png)

## Error Handling

![](img/oracle_SQL_notes/error_handling.png)

## Extra learning resources for Oracle

- Oracle Education
- Oracle on YouTube
- Oracle Experts
- Oracle Documentation
- LinkedIn Learning



# Oracle Database 19c

https://www.linkedin.com/learning/oracle-database-19c-basic-sql/



## Client Tools

- SQL Plus
- SQL cl
- SQL Developer



## String Manipulation

- Literals

  - Most common used literals:
    - string, numeric, date, interval

- Concatenation

  - using `||`

    - example: 

      ```sql
      select employee_id, last_name || ', ' || first_name fullname from employees
      ```

  - Why use `||` vs `concat`? --> it's more readable

- Alternative quoting

  - Use a single quotes plus embedded extra quotes
  - Use a quote delimiter



## DML / DDL

- Insert multiple rows using `INSERT ALL`
- Most commons data types are VARCHAR2, NUMBER, and DATE
- Creating indexes
  -  index, provides fast access to rows in table



## Dropping Objects

- Dropping tables
  - By default tables are kepts indefinitely in the recycle bin and are available for recovery unless
    - The DBA has turned off recycle bin functionality
    - The PURGE option was used when dropping the table
    - The space occupied by the dropped table needed to be re-used
  - Restore a table from the recycle bin with `FLASHBACK TABLE`
- Dropping indexes
  -  Drop an index on your own schema or another schema with the DROP INDEX statement
  - When you restore a table and its indexes, the index and its constraints won't have the same name it had originally

## SET DEFINE OFF / ON

- Why do we need `SET DEFINE OFF;` or `SET DEFINE ON;`

  this is used when script contains special characters that may break the execution (in our case it's "&" in the categories part) 

  so whenever a string contains "&", please use SET DEFINE OFF and then SET DEFINE ON in the end of the script 

## Next Steps

- education.oracle.com
- youtube.com/orcale
- asktom.oracle.com
- docs.oracle.com



# Oracle Database 12c: Advanced SQL

https://www.linkedin.com/learning/oracle-database-12c-advanced-sql

## Multi-column Subquery

![image-20210430130558173](img/oracle_sql_notes/image-20210430130558173.png)



## Indexes

- What is Index in Oracle?
  - Schema objects created in the database on one or more columns in the table
  - Can greatly improve query performance and access to data
  
- Sample use case: we have a sales table with millions of rows, and we want to look for sales on certain date
  ![image-20210430134319034](img/oracle_SQL_notes/image-20210430134319034.png)

  - Without indexing, Oracle SQL will scan entire table

- Indexes automatically used by the Oracle DB to improve performance for certain queries

- In this course, we will focused only on **B-Tree Index** type, as the most common one
  ![image-20210430134536863](img/oracle_SQL_notes/image-20210430134536863.png)

-  Sample index creation script

  ```sql
  create index emp_sal_idx on employees(salary) -- single index
  create index emp_idx2 on employees(salary,hire_date) -- composite index
  
  -- drop index
  drop index <index_name>
  ```

  - when you drop index, it doesn't affect the data in DB, because index is separate object in DB



## Oracle Data Dictionary

- What is it?
  ![image-20210430150831743](img/oracle_SQL_notes/image-20210430150831743.png)
  ![image-20210430150906959](img/oracle_SQL_notes/image-20210430150906959.png)
  - `V$ Views` also can be described as `DICT`
- Using the DICT view
  ![image-20210430151528860](img/oracle_SQL_notes/image-20210430151528860.png)
- Querying data dictionary views
  - most of `v$` symbol were used by Oracle DBA



## Transactions

![image-20210430152223865](img/oracle_SQL_notes/image-20210430152223865.png)



## Advanced Oracle Schema Objects

- Using identity columns

  ![image-20210430154459117](img/oracle_SQL_notes/image-20210430154459117.png)

- Table Triggers

  - Used for specific cases, for example: "only permit DML between 9am to 5pm"

  - Trigger Types
    ![image-20210430155637973](img/oracle_SQL_notes/image-20210430155637973.png)

  - Creating triggers ![image-20210430155910814](img/oracle_SQL_notes/image-20210430155910814.png)


    ![image-20210430155755302](img/oracle_SQL_notes/image-20210430155755302.png)

- PL/SQL
  ![image-20210430160040517](img/oracle_SQL_notes/image-20210430160040517.png)

  - Procedures
    ![image-20210430160224584](img/oracle_SQL_notes/image-20210430160224584.png)

    - to execute the procedures use:

      ```sql
      EXEC hr.update_emp_sal()
      ```

  - Functions
    Very similar to `Procedures`
    ![image-20210430160340143](img/oracle_SQL_notes/image-20210430160340143.png)

    - Execute as part of SQL statements, for example:

      ```sql
      select employee_id, first_name, period_of_service_year(employee_id) from employees;
      -- inside schema hr.period_of_service_year
      ```

  - Packages
    Groups multiple procedures, functions, types, variables, etc that share a business purpose
    ![image-20210430160626096](img/oracle_SQL_notes/image-20210430160626096.png)

    - two mandatory parts: package specification and package body
      ![image-20210430160744791](img/oracle_SQL_notes/image-20210430160744791.png)

  - Example of Procedure and Function:
    ![image-20210430161153640](img/oracle_SQL_notes/image-20210430161153640.png)

    

    ![image-20210430161045071](img/oracle_SQL_notes/image-20210430161045071.png)

    ![image-20210430161117950](img/oracle_SQL_notes/image-20210430161117950.png)

- Synonyms

  - It's like ALIAS in UNIX system

  - Example:

    ```sql
    create or replace synonym emp for hr.employees;
    -- using public synonym to be accessible by all users, it needs higher DB privilege
    create or replace public synonym emp for hr.employees;
    
    -- using synonym alias instead of full table name
  select * from emp where employee_id=100;
    
    -- drop synonym
    drop synonym emp;
    ```
    

- Simple Views

  - View acts like table, similar to synonym (alias)

  - Example:

    ```sql
    create or replace view emp_sales
    as
    select * from employees where job_id = 'SA_MAN';
    
    select * from emp_sales;
    
    -- DROP
    drop view emp_sales;
    ```

- Complex Views

  - Can be used to join multiple tables without using JOIN clause

  - Example:

    ```sql
    CREATE OR REPLACE VIEW location_view AS
    SELECT d.department_id, d.department_name, l.location_id, l.city
    FROM departments d, locations l
    WHERE d.location_id = l.location_id;
    
    SELECT * FROM location_view;
    ```



## Table Partitioning

- In Oracle, we did table partitioning, by divide it per columns, not rows
  ![image-20210430172956643](img/oracle_SQL_notes/image-20210430172956643.png)

- Benefits

  - Partition Pruning
    ![image-20210430173202738](img/oracle_SQL_notes/image-20210430173202738.png)
  - Database Administration Benefit
    - Able to independently running some specific queries

- Table Partitioning Methods

  - List
    Example partition based on state location

    ![image-20210430173446524](img/oracle_SQL_notes/image-20210430173446524.png)

  - Range
    ![image-20210430173726809](img/oracle_SQL_notes/image-20210430173726809.png)

  - Hash
    ![image-20210430173751064](img/oracle_SQL_notes/image-20210430173751064.png)

  - Interval

  - Composite

  - Automatic list

- Using LIST partitions

  - Example:

    ```sql
    CREATE TABLE sales_list
    (
        salesrep_id NUMBER(5),
        salesrep_name VARCHAR2(40),
        sales_state VARCHAR2(30),
        sales_value NUMBER(10),
        sales_date DATE
    )
    PARTITION BY LIST(sales_state)
    (
      PARTITION sales_CA VALUES('CA'),
      PARTITION sales_NY VALUES('NY'),
      PARTITION sales_central VALUES('TX','IL'),
      PARTITION sales_other VALUES(DEFAULT)  
    );
    
    -- sample insert to partition table
    INSERT INTO sales_list VALUES (100,'Enlik','CA',100,'01-JAN-2017');
    INSERT INTO sales_list VALUES (200,'Danny','NY',500,'02-JAN-2017');
    INSERT INTO sales_list VALUES (300,'Nanako','TX',1000,'03-JAN-2017');
    INSERT INTO sales_list VALUES (100,'Alise','IL',500,'04-JAN-2017');
    
    -- check how many rows per partition table
    SELECT COUNT(*) FROM sales_list partition (sales_ca);
    SELECT COUNT(*) FROM sales_list partition (sales_ny);
    SELECT COUNT(*) FROM sales_list partition (sales_central);
    SELECT COUNT(*) FROM sales_list partition (sales_other);
    
    ```

- Splitting LIST partitions
  ![image-20210430174731260](img/oracle_SQL_notes/image-20210430174731260.png)

- Using RANGE partitions
  ![image-20210430174844047](img/oracle_SQL_notes/image-20210430174844047.png)

- Using HASH partitions

  Hash type used when you don't have specific column that suitable for partitioning such as date or state from previous examples
  ![image-20210430174929532](img/oracle_SQL_notes/image-20210430174929532.png)

  ![image-20210430175004790](img/oracle_SQL_notes/image-20210430175004790.png)



# How to Recover Data (Without a Backup!)

https://blogs.oracle.com/sql/how-to-recover-data-without-a-backup



## Salvaging the Deleted Rows

Insert

```sql
insert into table
  select * from <table> as of timestamp sysdate ??? interval '1' hour
  where <conditions to find the rows>;
```

Finding deleted rows

```sql
select * from <table> as of timestamp sysdate ??? interval '1' hour
minus 
select * from <table>;
```

Recover

```sql
insert into <table> 
  select * from <table> as of timestamp sysdate ??? interval '1' hour
  minus 
  select * from <table>;
```



## Recovering deleted rows from oracle table

https://stackoverflow.com/questions/23334495/recovering-deleted-rows-from-oracle-table/23334728

You can recover the details using Oracle Flashback Query.  You could query the contents of the table as of a time before the  deletion to find out what data had been lost, and, if appropriate,  re-insert the lost data in the database. Here's the sample query: 

```sql
select * from MANUAL_TRANSACTION as of timestamp to_timestamp('28-APR-2014 12:30:00', 'DD-MON-YYYY HH:MI:SS') where ' clause based on your deleted data';
```





# PostgreSQL vs Oracle SQL

## Jan Karremans - Comparing PostgreSQL to Oracle. The best kept secrets to success

https://www.youtube.com/watch?v=NHUVJBrpF64

- Speaker: Jan Karremans, EDB Postgres
- Oracle = Oracle Enterprise Edition
- Postgres = Enterprise Postgres DB
- High Availability
  ![high_availability](img/oracle_SQL_notes/high_availability.jpg)
- Performance and Scalability
  ![performance_and_scalability](img/oracle_SQL_notes/performance_and_scalability.jpg)
- Security
  ![security](img/oracle_SQL_notes/security.jpg)
- Integration
  ![integration](img/oracle_SQL_notes/integration-1618394141364.jpg)
- Application Development
  ![application_development](img/oracle_SQL_notes/application_development.jpg)
- Big and Unstructured Data
  ![big_and_unstructured_data](img/oracle_SQL_notes/big_and_unstructured_data.jpg)
- Management
  ![management](img/oracle_SQL_notes/management.jpg)



## Oracle Vs PostgreSQL [#Database](https://www.youtube.com/hashtag/database) [#Which](https://www.youtube.com/hashtag/which) is most [#Powerful](https://www.youtube.com/hashtag/powerful) database?

https://www.youtube.com/watch?v=Uo_jnAKLqAg

- Oracle
  - developed in 1977
  - Editions
    - Enterprise
    - Standard
    - Express
    - Oracle Lite
  - Run on the major platforms like Windows, UNIX, Linux, and macOS
  - It build around a relational database in which data can be accessed by users through an application or query language called SQL
- PostgreSQL
  - Support all features of RDBMS along with that other features which are not available in RDBMS such as views, stored procedures, indexes, and triggers
  - Has open database connectivity
  - Run on the major platforms
  - It support unstructured data such as video, text,a udio, images
  - API for different languages such as C/C++, Java, Python, Perl, etc
- Oracle vs PostgreSQL
  ![oracle_vs_postgres](img/oracle_SQL_notes/oracle_vs_postgres.jpg)
- Conclusion
  - Postgres is more powerful than Oracle in many aspects
  - Compatibility with other RDBMS and ease use with large community of developers



# Datacamp - Introduction to Oracle SQL

## SQL Basics

- SQL DB popularity until 2019
  ![sql_db_popularity_2019](img/oracle_SQL_notes/sql_db_popularity_2019.jpg)

- Add *'s'* string inside the query

  ```sql
  SELECT FirstName || q'['s home country is ]' || Country FROM Employee;
  
  SELECT FirstName || '''s' || ' home country is ' || Country FROM Employee;
  
  --OUTPUT: "Peacock's home country is Canada"
  ```

  

## Aggregating Data

- Select country with total customer more than 4

```sql
-- Adapt the query below to show the correct results
SELECT Country, COUNT(*) as Customers
FROM Customer
GROUP BY Country
HAVING COUNT(*) > 4
```



## Combining Data

- SQL Joins
  - Inner, Outer, Cross, Self
- ![join](img/oracle_SQL_notes/join.jpg)

- Cross Join
  ![cross_join](img/oracle_SQL_notes/cross_join.jpg)
- Self Join
  ![self_join](img/oracle_SQL_notes/self_join.jpg)

- Types of Set operators
  ![set_operators](img/oracle_SQL_notes/set_operators.jpg)



## Taking it to the Next Level

- Query Processing Order

  - What can go wrong?
    ![query_processing_order](img/oracle_SQL_notes/query_processing_order.jpg)
  - Order
    ![the_order](img/oracle_SQL_notes/the_order.jpg)

- Aggregated values can't be filtered out in the `WHERE` clause, this needs to be done in the `HAVING` clause.
  ![having_clause](img/oracle_SQL_notes/having_clause.jpg)

- Working with NULL values

  - NVL

    - `NVL(x, y)` : convert x, which may contain a null value, to `y`, a non-null value

  - NULLIF

    - NULLIF(x, y) : compares x and y, returns
      - NULL if x = y
      - x if they are not equal
    - Example
      ![nullif](img/oracle_SQL_notes/nullif.jpg)

  - COALESCE

    - returns first non-null value in a list
    - example
      ![coalesce](img/oracle_SQL_notes/coalesce.jpg)

  - Practice:

    ```sql
    -- Replace NULL values in the Company field
    SELECT NVL(Company, 'No affiliation') AS Affiliation, COUNT(*)
    FROM Customer
    -- Filter on the country USA
    WHERE Country = 'USA'
    -- Group by affiliation
    GROUP BY Company
    ```

    ```sql
    -- Replace NULL values in the Company field
    SELECT COALESCE(Company, 'No affiliation') AS Affiliation, COUNT(*)
    FROM Customer
    -- Filter on the country USA
    WHERE Country = 'USA'
    -- Group by affiliation
    GROUP BY Company
    ```

- Using Conversion Functions

  - Explicit data type conversion
    ![explicit_data_type_conversion](img/oracle_SQL_notes/explicit_data_type_conversion.jpg)
  - Implicit data type conversion
    ![implicit_data_type_conversion](img/oracle_SQL_notes/implicit_data_type_conversion.jpg)

- Group by YearMonth
  ![groupby_year_month](img/oracle_SQL_notes/groupby_year_month.jpg)







# SQL Optimization

## Optimizing SQL Performance

https://www.youtube.com/watch?v=VCJTVk4xZIs



## Oracle SQL Optimizer Overview | Query Optimizer Concepts

https://youtu.be/PPJ6EdB7V-o



## Oracle Performance Tuning - EXPLAIN PLAN

https://youtu.be/kYUrS8iAiJc





# Indexing in Oracle DB

### How Indexing Works?

https://dataschool.com/sql-optimization/how-indexing-works/

- Why?
  - We want to find a piece of information in a large DB
  - Rather than let computer look through every rows to find it, using indexes it will help create sorted list without having to create all new sorted tables
- When to use?
  - As your DB becomes larger and larger
- When not to use?
  - If DB is constantly receiving writes then the indexes will never be usable
  - This is why indexes are typically applied to DBs in data warehouses that get a new data updated on a scheduled basis (off-peak hours) and not production DBs which might be receiving new writes all the time
- Summary
  - Indexing can vastly reduce the time of queries
  - Not every DB will benefit from indexing
  - Not every index will increase the query speed for the DB



# Oracle Create Index - OracleTutorials

https://www.oracletutorial.com/oracle-index/oracle-create-index

![image-20210607170301560](img/oracle_SQL_notes/image-20210607170301560.png)



## How to Create and Use Indexes in Oracle DB - blogs.oracle.com

https://blogs.oracle.com/sql/how-to-create-and-use-indexes-in-oracle-database



## Oracle SYS_REFCURSOR

- Use case: in **gamingreporting.SpainJackpotBot_Proc**

  ![sys_refcursor_spainjackpot](img/oracle_SQL_notes/sys_refcursor_spainjackpot.png)

- References

  - https://oracle-base.com/articles/misc/using-ref-cursors-to-return-recordsets
  - https://oracle-base.com/articles/12c/implicit-statement-results-12cr1
  - https://oracle-base.com/articles/misc/check-the-contents-of-ref-cursors
  - https://www.youtube.com/watch?v=TXtxZi2i9lg



## To check if column existed

https://gist.github.com/davidwaterston/3755420

```sql
select column_name as found
from user_tab_cols
where table_name = '__TABLE_NAME__'
and column_name = '__COLUMN_NAME__'
```



# Using Cursor

https://www.guru99.com/pl-sql-cursor.html#:~:text=A%20Cursor%20is%20a%20pointer,returned%20by%20the%20SQL%20statement.