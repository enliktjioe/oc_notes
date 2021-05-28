# Datacamp - Database Design

https://campus.datacamp.com/courses/database-design



## Processing, Storing, and Organizing Data

### OLTP and OLAP

- It works together
  ![image-20210528105845277](img/datacamp_db_design/image-20210528105845277.png)
- OLTP vs OLAP
  ![image-20210528105905750](img/datacamp_db_design/image-20210528105905750.png)
- Takeaways
  - Step back and figure out business requirements
  - Difference between OLAP and OLTP
- Quiz
  ![image-20210528110150419](img/datacamp_db_design/image-20210528110150419.png)





### Storing Data

- Data Structure
  ![image-20210528110241939](img/datacamp_db_design/image-20210528110241939.png)

  ![image-20210528112017241](img/datacamp_db_design/image-20210528112017241.png)

- Storing data beyond traditional databases
  ![image-20210528110329306](img/datacamp_db_design/image-20210528110329306.png)

- Data warehouses
  ![image-20210528110352577](img/datacamp_db_design/image-20210528110352577.png)

  - Why choose Data Warehouse over Data Lakes?

    Analysts will appreciate working in a data warehouse more because of its organization of structured data that make analysis easier.

- Data lakes
  ![image-20210528110504097](img/datacamp_db_design/image-20210528110504097.png)

- ETL and ELT
  ![image-20210528110548686](img/datacamp_db_design/image-20210528110548686.png)

- ETL example
  ![image-20210528112118658](img/datacamp_db_design/image-20210528112118658.png)





### Database Design

- What is it?
  ![image-20210528112331490](img/datacamp_db_design/image-20210528112331490.png)

- Data Modeling

  ![image-20210528112355787](img/datacamp_db_design/image-20210528112355787.png)

- Conceptual, Logical and Physical
  ![image-20210528112429957](img/datacamp_db_design/image-20210528112429957.png)

  ![image-20210528112600240](img/datacamp_db_design/image-20210528112600240.png)





## Database Schemas and Normalization

### Star and Snowflake Schema

- Star schema
  ![image-20210528114834334](img/datacamp_db_design/image-20210528114834334.png)

  ![image-20210528114851903](img/datacamp_db_design/image-20210528114851903.png)

- Normalization
  ![image-20210528114911599](img/datacamp_db_design/image-20210528114911599.png)





### Normalized and Denormalized Databases

- Star and snowflake schema
  ![image-20210528115129830](img/datacamp_db_design/image-20210528115129830.png)

- Why normalization?

  - saves space
    ![image-20210528115227437](img/datacamp_db_design/image-20210528115227437.png)

    ![image-20210528115246096](img/datacamp_db_design/image-20210528115246096.png)

  - ensures better data integrity
    ![image-20210528115355838](img/datacamp_db_design/image-20210528115355838.png)

- Pros and Cons of Normalization
  ![image-20210528115424999](img/datacamp_db_design/image-20210528115424999.png)

- OLTP requires more normalization compare to OLAP
  ![image-20210528115458922](img/datacamp_db_design/image-20210528115458922.png)



### Normal Forms

- Normal Forms
  ![image-20210528120034508](img/datacamp_db_design/image-20210528120034508.png)

- 1NF rules
  ![image-20210528120103460](img/datacamp_db_design/image-20210528120103460.png)

- 1NF form
  ![image-20210528120109840](img/datacamp_db_design/image-20210528120109840.png)

- 2NF
  ![image-20210528120136804](img/datacamp_db_design/image-20210528120136804.png)

- 3NF

  ![image-20210528120152284](img/datacamp_db_design/image-20210528120152284.png)

- Data anomalies
  What is risked if we don't normalize enough?
  ![image-20210528120230003](img/datacamp_db_design/image-20210528120230003.png)

  - Update anomaly
    ![image-20210528120248462](img/datacamp_db_design/image-20210528120248462.png)
  - Insertion anomaly
    ![image-20210528120320220](img/datacamp_db_design/image-20210528120320220.png)
  - Deletion anomaly
    ![image-20210528120336330](img/datacamp_db_design/image-20210528120336330.png)



## Database Views

### Intro

- What is it?
  ![image-20210528125547410](img/datacamp_db_design/image-20210528125547410.png)

- Creating VIEW
  ![image-20210528125603616](img/datacamp_db_design/image-20210528125603616.png)

- Benefits of views
  ![image-20210528125629569](img/datacamp_db_design/image-20210528125629569.png)

- Tables vs Views

  ![image-20210528125747489](img/datacamp_db_design/image-20210528125747489.png)



### Managing Views

- Creating more complex views
  ![image-20210528130515638](img/datacamp_db_design/image-20210528130515638.png)

- Granting and revoking access to a view
  ![image-20210528130534640](img/datacamp_db_design/image-20210528130534640.png)

  ![image-20210528130544240](img/datacamp_db_design/image-20210528130544240.png)

- Updating a view
  ![image-20210528130600331](img/datacamp_db_design/image-20210528130600331.png)

  - Check if it's updatable or not

    ```sql
    select * from information_schema.views where table_schema not in ('pg_catalog','information_schema');
    ```

    ![image-20210528131617889](img/datacamp_db_design/image-20210528131617889.png)

- Inserting into a view
  ![image-20210528130641781](img/datacamp_db_design/image-20210528130641781.png)

- Dropping a view
  ![image-20210528130700565](img/datacamp_db_design/image-20210528130700565.png)

  - Dropping with CASCADE

  ![image-20210528131204085](img/datacamp_db_design/image-20210528131204085.png)

- Redefining a view
  ![image-20210528130713329](img/datacamp_db_design/image-20210528130713329.png)

- Altering a view
  ![image-20210528130732246](img/datacamp_db_design/image-20210528130732246.png)





### Materalized Views

- Two types of views
  - Views
    - also known as non-materialized views
  - Materialized Views
    - physically materialized
- What is Materialized Views?
  ![image-20210528132612735](img/datacamp_db_design/image-20210528132612735.png)
- When to use it?
  ![image-20210528132643642](img/datacamp_db_design/image-20210528132643642.png)
- Implementing materialized views in PostgreSQL
  ![image-20210528132701045](img/datacamp_db_design/image-20210528132701045.png)
- Managing dependencies
  - Materialized views often depend on other materialized views
  - Example
    ![image-20210528132737386](img/datacamp_db_design/image-20210528132737386.png)
  - Create a dependency chain when refreshing views
  - Not the most efficient to refresh all views at the same time
- Tools for managing dependencies
   ![image-20210528132838267](img/datacamp_db_design/image-20210528132838267.png)
- Differences
  ![image-20210528133053668](img/datacamp_db_design/image-20210528133053668.png)

- Why do companies use pipeline schedulers, such as Airflow and Luigi, to manage materialized views?
  **To refresh materialized views with consideration to dependences between views**
  *Exactly! These pipeline schedulers help visualize dependencies and create a logical order for refreshing views.*





## Database Management

### Database Roles and Access Controls

- DB Roles
  ![image-20210528133437312](img/datacamp_db_design/image-20210528133437312.png)

- Create a role

  ![image-20210528133531341](img/datacamp_db_design/image-20210528133531341.png)

- GRANT and REVOKE privileges from roles

  ![image-20210528133557298](img/datacamp_db_design/image-20210528133557298.png)

- Users and groups (are both roles)
  ![image-20210528133619307](img/datacamp_db_design/image-20210528133619307.png)

  ![image-20210528133633457](img/datacamp_db_design/image-20210528133633457.png)

- Common PostgreSQL roles

  ![image-20210528133652877](img/datacamp_db_design/image-20210528133652877.png)

- Benefits of pitfalls of Roles
  ![image-20210528133712247](img/datacamp_db_design/image-20210528133712247.png)



### Table Partitioning

- Why?
  ![image-20210528134144130](img/datacamp_db_design/image-20210528134144130.png)

- Data modeling refresher
  ![image-20210528134156143](img/datacamp_db_design/image-20210528134156143.png)

- Vertical Partitioning
  ![image-20210528134216903](img/datacamp_db_design/image-20210528134216903.png)

- Horizontal Partitioning
  ![image-20210528134252684](img/datacamp_db_design/image-20210528134252684.png)

  - Example:
    ![image-20210528134309140](img/datacamp_db_design/image-20210528134309140.png)
  - Pros/Cons
    ![image-20210528134330150](img/datacamp_db_design/image-20210528134330150.png)

- Relation to sharding

  Useful in parallel computing
  ![image-20210528134347804](img/datacamp_db_design/image-20210528134347804.png)

- Normalization vs Vertical Partitioning vs Horizontal Partitioning
  ![image-20210528134525005](img/datacamp_db_design/image-20210528134525005.png)

- Practice - creating partition table by year
  ![image-20210528135553194](img/datacamp_db_design/image-20210528135553194.png)





### Data Integration

- Data integration combines data from different sources, formats, technologies to provide users with a translated and unified view of that data
- Business case examples
  - 360-degree customer view
  - Acquisition
  - Legacy systems
- Unified data model, data sources format, update cadence, transformations
  - Example: Datacamp
    ![image-20210528135858169](img/datacamp_db_design/image-20210528135858169.png)
- Choosing a data integration tool
  - flexible
  - reliable
  - scalable
- Automated testing and proactive alerts
- Security
  - example: credit card or phone number anonymization
- True or False
  ![image-20210528140223386](img/datacamp_db_design/image-20210528140223386.png)





### Picking a DBMS

- Two types: SQL and NoSQL
- SQL = Relational DBMS
  - SQL Server
  - PostgreSQL
  - Oracle
  - Best option when:
    - data is structured and unchanging
    - data must be consistent
- NoSQL DBMS
  - Less structured
  - Document-centered rather than table-centered
  - Data doesn't have to fit into well-defined rows and columns
  - Best option when:
    - Rapid growth
    - No clear schema definitions
    - Large quantities of data
  - Type: key-value store, document store. columnar database, graph database
  - Key-Value Store
    ![image-20210528140623365](img/datacamp_db_design/image-20210528140623365.png)
  - Document Store
    ![image-20210528140651685](img/datacamp_db_design/image-20210528140651685.png)
  - Columnar Database
    ![image-20210528140709318](img/datacamp_db_design/image-20210528140709318.png)
  - Graph Database
    ![image-20210528140732528](img/datacamp_db_design/image-20210528140732528.png)
- Choosing DBMS
  ![image-20210528140757276](img/datacamp_db_design/image-20210528140757276.png)
  - If the data changing rapidly, NoSQL is the option for you









