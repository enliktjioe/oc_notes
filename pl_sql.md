# **Learning Oracle Database 19c - PL/SQL**



https://www.linkedin.com/learning/learning-oracle-database-19c/pl-sql?u=26110466

## What is it?

- Programming Language/SQL
- Extens Oracle SQL
- Based on the Ada language
- SQL is declarative: “here’s what I want to do"
- PL/SQL is procedureal: “I know exactly how to do this and here’s how I’m going to do it"

## PL/SQL Language Elements

- Loops
- IF ELSE
- Exception Handling
- Storing functions and procedures
- Think it like programming language instead SQL

![pl1](img/pl_sql/pl1.png)

![pl2](img/pl_sql/pl2.png)

![pl3](img/pl_sql/pl3.png)

![pl4](img/pl_sql/pl4.png)

Remember:

- SQL: report writing needing simple joins, ad hoc queries
- PL/SQL
  - Complex business logic
  - Stored procedures or functions

## The ANSI SQL language standard

https://www.linkedin.com/learning/learning-oracle-database-19c/the-ansi-sql-language-standard?u=26110466

![pl5](img/pl_sql/pl5.png)

## Creating Functions

- Syntax for CREATE function

  - name the function
  - what will it return?

  ![function](img/pl_sql/function.png)

## Creating Procedures

- Encapsulated section of PL/SQL or Java code
- Can be anonymous
- Zero or more arguments, but don't return values
  - 
- Can be stored in a package with other stored functions, procedures, and types

## Declaring Variable

![var_declare](img/pl_sql/var_declare.png)

![var_declare](img/pl_sql/var_declare2.png)

## Declare Cursor

### What is Cursor?

- a pointer to a private SQL are with metadata for running a SELECT or other DML statement
- two types: explicit and implicit

### Explicit Cursor

![explicit_cursor](img/pl_sql/explicit_cursor.png)

### Implicit Cursor

![implicit_cursor](img/pl_sql/implicit_cursor.png)

### Built-In  Cursor

![builtin](img/pl_sql/built-in_cursor.png)

## Using SQL SELECT Statement

### Static SQL Statement

![static](img/pl_sql/static_sql.png)

## Error Handling

![](img/pl_sql/error_handling.png)