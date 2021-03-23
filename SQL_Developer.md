# Programming Foundation: Database

https://www.linkedin.com/learning/programming-foundations-databases-2/

## SQL

- The language that we used to communicate with database

## Schema

- The database's **schema** includes the information about the layout of tables and other information about the database itself. 

## Database Foundations

- ACID and transactions
  - Atomic
    - Atomicity means that the transaction behaves as one single action.        
  - Consistent
  - Isolated
    - The "isolated" requirement actually refers to the data that is altered by other actions.          
  - Durable
    - Durability requires that data changed by the transaction is written to the database.        
- CRUD
  - Create - Read - Update - Delete
- Transactions
  - All of the steps for an action must be completed
- **Unique values, only occurs once in given column**
- SELECT * FROM table_name
  - has 2 clauses, **select** and **from**
- Relationship
  - a set of attributes (columns) that describe information about specific instances (rows) of an entity
  - Example: a customer with their favorite table in the restaurant
    - This would be a one-to-many relationship. For every one table, there could be many customers who prefer to sit at it. But one customer cannot have many favorite tables.        
- A **composite key** combines two or more fields to act as a unique identifier.

## Tables

- Prepare the schema
- Naming tables
  - should be pluralized
- Columns and data types
- Number and other types
- Primary and foreign keys

## Database Optimization

- 1NF (First Normal Form)
 - Values in each cell should be atomic and tables should have no repeating groups
- 2NF
 - No value in a table should depend on only part of a key that can be used to uniquely identify a row
- 3NF
 - Values should not be stored if they can be calculated from another non-key field
- Denormalization
 - The process of intentionally duplicating information in a table, in violation of normalization rules
 - Used to denormalize the normalized database
 - 






