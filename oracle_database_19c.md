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



## Next Steps

- education.oracle.com
- youtube.com/orcale
- asktom.oracle.com
- docs.oracle.com


