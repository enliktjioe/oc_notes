# dbt Fundamentals

https://courses.getdbt.com/courses/take/fundamentals



## Who is an Analytics Engineer?

- Traditional Data Teams
  - Contains only 2 = data analyst (DA) and data engineer (DE)
  - Data Engineer = ETL, orchestration, Python, Java, etc
  - Data Analyst = Dashboards, Reporting, Excel, SQL
  - Analyst know what to build
  - Engineers know how to build it
- ETL and ELT
  - ETL usually handled by Data Engineer
  - ETL needs to be automated through orchestration such as Airflow
  - Cloud-based data warehouses
    - combine a DB and super computer to computing data
    - Offers:
      - Scalable compute
      - Scalable storage
      - Reduction of transfer time
  - ELT
    - shift focus to:
      - get the data in the warehouse
      - transform the data from there
- Analytics Engineer (AE)
  - owns the Transformation of the raw data to BI layer
  - Modern Data Team, including DE, DA, and AE
- Data build tool (dbt)
  - build for analysts to gain more leverage in their work
  - comes from applying SE principles to analytic works
    - including testing, docs, version control, and CI
  - provides tools to implement those SE principles
- 