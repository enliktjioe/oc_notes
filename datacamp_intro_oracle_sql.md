# Datacamp - Introduction to Oracle SQL

## SQL Basics

- SQL DB popularity until 2019
  ![sql_db_popularity_2019](img/datacamp_intro_oracle_sql/sql_db_popularity_2019.jpg)

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
- ![join](img/datacamp_intro_oracle_sql/join.jpg)

- Cross Join
  ![cross_join](img/datacamp_intro_oracle_sql/cross_join.jpg)
- Self Join
  ![self_join](img/datacamp_intro_oracle_sql/self_join.jpg)

- Types of Set operators
  ![set_operators](img/datacamp_intro_oracle_sql/set_operators.jpg)



## Taking it to the Next Level

- Query Processing Order

  - What can go wrong?
    ![query_processing_order](img/datacamp_intro_oracle_sql/query_processing_order.jpg)
  - Order
    ![the_order](img/datacamp_intro_oracle_sql/the_order.jpg)

- Aggregated values can't be filtered out in the `WHERE` clause, this needs to be done in the `HAVING` clause.
  ![having_clause](img/datacamp_intro_oracle_sql/having_clause.jpg)

- Working with NULL values

  - NVL

    - `NVL(x, y)` : convert x, which may contain a null value, to `y`, a non-null value

  - NULLIF

    - NULLIF(x, y) : compares x and y, returns
      - NULL if x = y
      - x if they are not equal
    - Example
      ![nullif](img/datacamp_intro_oracle_sql/nullif.jpg)

  - COALESCE

    - returns first non-null value in a list
    - example
      ![coalesce](img/datacamp_intro_oracle_sql/coalesce.jpg)

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
    ![explicit_data_type_conversion](img/datacamp_intro_oracle_sql/explicit_data_type_conversion.jpg)
  - Implicit data type conversion
    ![implicit_data_type_conversion](img/datacamp_intro_oracle_sql/implicit_data_type_conversion.jpg)

- Group by YearMonth
  ![groupby_year_month](img/datacamp_intro_oracle_sql/groupby_year_month.jpg)



