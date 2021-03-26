

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
- DDL = Data Definition Language
  - CREATE
  - ALTER
  - DROP
  - TRUNCATE
- DML = Data Manipulation Language
  - SELECT
  - INSERT
  - UPDATE
  - DELETE



## TODO

- WITH clause
- Sequence
  - default, primary key
  - as an input in sequence
- Table casino.dailystats
  - Sum of player bets
  - Sum of player winnings
  - CasinoCode

