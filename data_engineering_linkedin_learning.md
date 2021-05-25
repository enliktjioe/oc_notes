## Data Engineering Foundations

https://www.linkedin.com/learning/data-engineering-foundations

Instructor: Harshit Tyagi

## Intro

- Challenges in Data-driven Organization
  ![image-20210525102617629](img/data_engineering_linkedin_learning/image-20210525102617629.png)
- Roles:
  ![image-20210525102643587](img/data_engineering_linkedin_learning/image-20210525102643587.png)
- Skills needed:
  ![image-20210525102658711](img/data_engineering_linkedin_learning/image-20210525102658711.png)
- Data Engineer vs Data Scientist
  ![image-20210525102322353](img/data_engineering_linkedin_learning/image-20210525102322353.png)
- Essential tools
  - Processing Frameworks
    - Data cleaning - aggregation - clustering - batch/stream processing
    - Tools: Spark - Hive - Kafka
  - Automation: Scheduling
    - Set up and manage workflows
    - Plan jobs with specific interval
    - Resolve dependency requirement of jobs
    - Tools: Airflow, Oozie, Luigi
  - A complete pipeline
    ![image-20210525102543780](img/data_engineering_linkedin_learning/image-20210525102543780.png)





## DB and Dataframes

- Type of data
  ![image-20210525102811373](img/data_engineering_linkedin_learning/image-20210525102811373.png)
- SQL vs NoSQL
  ![image-20210525102827654](img/data_engineering_linkedin_learning/image-20210525102827654.png)
- DB Schema
  - Schema describes the structure and relations of DB
    ![image-20210525102912961](img/data_engineering_linkedin_learning/image-20210525102912961.png)
  - Creating Schema
    ![image-20210525102927072](img/data_engineering_linkedin_learning/image-20210525102927072.png)
  - SQL: Star Schema
    - Consist of one or more fact tables referencing any number of dimension tables
      ![image-20210525102954332](img/data_engineering_linkedin_learning/image-20210525102954332.png)
- Distributive Computing
  - How it works
    ![image-20210525103038996](img/data_engineering_linkedin_learning/image-20210525103038996.png)
  - Benefits
    - More processing power
    - More scalable
    - Cost effective
    - Fault tolerance
  - Risks
    ![image-20210525103121739](img/data_engineering_linkedin_learning/image-20210525103121739.png)
  - Multiprocessing using Python
    ![image-20210525103144061](img/data_engineering_linkedin_learning/image-20210525103144061.png)
  - Using Dask
    ![image-20210525103203355](img/data_engineering_linkedin_learning/image-20210525103203355.png)



## Data Engineering Tools

- MapReduce and Hadoop
  ![image-20210525103311775](img/data_engineering_linkedin_learning/image-20210525103311775.png)

  ![image-20210525103257551](img/data_engineering_linkedin_learning/image-20210525103257551.png)

- Hadoop DFS
  ![image-20210525103326914](img/data_engineering_linkedin_learning/image-20210525103326914.png)

- Hadoop MapReduce
  ![image-20210525103345856](img/data_engineering_linkedin_learning/image-20210525103345856.png)

- Hive

  - Hive SQL, originally developed by Facebook, now maintained by Apache
    ![image-20210525103413328](img/data_engineering_linkedin_learning/image-20210525103413328.png)
  - How Hive works?
    ![image-20210525103438808](img/data_engineering_linkedin_learning/image-20210525103438808.png)

- Spark

  - Info
    ![image-20210525103458296](img/data_engineering_linkedin_learning/image-20210525103458296.png)
  - RDD
    ![image-20210525103507128](img/data_engineering_linkedin_learning/image-20210525103507128.png)
    ![image-20210525103529065](img/data_engineering_linkedin_learning/image-20210525103529065.png)
  - PySpark
    ![image-20210525103540008](img/data_engineering_linkedin_learning/image-20210525103540008.png)
    ![image-20210525103553312](img/data_engineering_linkedin_learning/image-20210525103553312.png)

- Airflow

  - Workflow
    ![image-20210525103632727](img/data_engineering_linkedin_learning/image-20210525103632727.png)
    - the reason why we need automation is to be able work for it while we on holiday (weekend / public holiday)
    - cron can do this, but only in Linux
  - DAG (Directed Acyclic Graph)
    ![image-20210525103737395](img/data_engineering_linkedin_learning/image-20210525103737395.png)
  - Scheduler Tools
    - Cron jobs
    - Spotify's Luigi
    - Apache Airflow
  - Airflow DAG example
    ![image-20210525103829684](img/data_engineering_linkedin_learning/image-20210525103829684.png)
  - Coding DAGs
    ![image-20210525103840629](img/data_engineering_linkedin_learning/image-20210525103840629.png)
  - 



## ETL Pipelines

- Extracting Data (E)

  - Sources
    - Most famout format: JSON
    - Data through APIs
      ![image-20210525104107959](img/data_engineering_linkedin_learning/image-20210525104107959.png)
    - Data from Databases
      ![image-20210525104124985](img/data_engineering_linkedin_learning/image-20210525104124985.png)
  - Extract from PostgreSQL DB
    - Using PySpark
      ![image-20210525104208001](img/data_engineering_linkedin_learning/image-20210525104208001.png)
      ![image-20210525104221024](img/data_engineering_linkedin_learning/image-20210525104221024.png)
  - Challenge: Data Extraction
    ![image-20210525104258436](img/data_engineering_linkedin_learning/image-20210525104258436.png)
    - driver = org.postgresql.Driver

- Transforming Data (T)

  - Example
    ![image-20210525104406251](img/data_engineering_linkedin_learning/image-20210525104406251.png)
    ![image-20210525104419082](img/data_engineering_linkedin_learning/image-20210525104419082.png)
  - Challenge: Transforming data
    ![image-20210525104452587](img/data_engineering_linkedin_learning/image-20210525104452587.png)
    - users_df.groupby('movie_id').mean('rating')
    - movies_df.id == avg_rating.movie_id
    - print(df.show())
       <img src="img/data_engineering_linkedin_learning/image-20210525104613276.png" alt="image-20210525104613276" style="zoom:80%;" />

- Loading Data into DB (L)

  - Example
    ![image-20210525104650503](img/data_engineering_linkedin_learning/image-20210525104650503.png)
    ![image-20210525104714077](img/data_engineering_linkedin_learning/image-20210525104714077.png)

  - Challenge

    ![image-20210525104749624](img/data_engineering_linkedin_learning/image-20210525104749624.png)

    - mode = "overwrite"
    - ratings_df = transform_avg_ratings(movies_df, users_df)
    - load_df_to_db(ratings_df)

- Scheduling ETL pipeline using Airflow

  - Setup
    ![image-20210525104959489](img/data_engineering_linkedin_learning/image-20210525104959489.png)

    ![image-20210525105042281](img/data_engineering_linkedin_learning/image-20210525105042281.png)

  - Transformation function (no processing happening here, it's all about configuration)
    ![image-20210525105112897](img/data_engineering_linkedin_learning/image-20210525105112897.png)

    ![image-20210525105213354](img/data_engineering_linkedin_learning/image-20210525105213354.png)

  -  Folder structure
    ![image-20210525105234410](img/data_engineering_linkedin_learning/image-20210525105234410.png)

  - Start server --> airflow webserver (get the URL)
     ![image-20210525105317979](img/data_engineering_linkedin_learning/image-20210525105317979.png)

    ![image-20210525105329090](img/data_engineering_linkedin_learning/image-20210525105329090.png)

    ![image-20210525105348652](img/data_engineering_linkedin_learning/image-20210525105348652.png)



