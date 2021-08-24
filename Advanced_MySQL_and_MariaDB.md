# Advanced MySQL and MariaDB

https://www.linkedin.com/learning/advanced-mysql-and-mariadb/welcome?u=26110466



Environment

![image-20210824114509172](img/Advanced_MySQL_and_MariaDB/image-20210824114509172.png)



## How MariaDB is Different

- Overview

  - Is a fork of MySQL
  - Based on MySQL 5.1
  - Added XtraDB, PBXT, FederatedX storage engines
  - Added Aria storage engine
  - Newer version after MariaDB v5.x is v10.0
    - GTID
    - Multisource replication
    - Cassandra storage engine
    - CONNECT storage engine

- Exploring server thread pooling

  - Thread Pooling
    ![image-20210824115040330](img/Advanced_MySQL_and_MariaDB/image-20210824115040330.png)
    ![image-20210824115111497](img/Advanced_MySQL_and_MariaDB/image-20210824115111497.png)
  - Thread Pool Size
    ![image-20210824115133902](img/Advanced_MySQL_and_MariaDB/image-20210824115133902.png)
  - Viewing user statistics
    ![image-20210824115220294](img/Advanced_MySQL_and_MariaDB/image-20210824115220294.png)
    ![image-20210824115338197](img/Advanced_MySQL_and_MariaDB/image-20210824115338197.png)
  - Creating and using virtual columns
    ![image-20210824115559397](img/Advanced_MySQL_and_MariaDB/image-20210824115559397.png)
    - Example:
      ![image-20210824115655359](img/Advanced_MySQL_and_MariaDB/image-20210824115655359.png)
      ![image-20210824115712337](img/Advanced_MySQL_and_MariaDB/image-20210824115712337.png)

  - Using persistent virtual columns

    - it's opposite of virtual

      ![image-20210824115801066](img/Advanced_MySQL_and_MariaDB/image-20210824115801066.png)

    - Virtual column limitations
      ![image-20210824120021249](img/Advanced_MySQL_and_MariaDB/image-20210824120021249.png)

    - Example:
      ![image-20210824115910737](img/Advanced_MySQL_and_MariaDB/image-20210824115910737.png)
      ![image-20210824115955572](img/Advanced_MySQL_and_MariaDB/image-20210824115955572.png)

  - Progress reporting and millisecond resolution
    - Aria Progress Reporting
      - Check Table, Repair Table, Analyze Table, Optimize Table



## The Sphinx Storage Engine

![image-20210824120307168](img/Advanced_MySQL_and_MariaDB/image-20210824120307168.png)

![image-20210824120439656](img/Advanced_MySQL_and_MariaDB/image-20210824120439656.png)

![image-20210824120457543](img/Advanced_MySQL_and_MariaDB/image-20210824120457543.png)



## NoSQL Integration

Install handler socket

![image-20210824120542591](img/Advanced_MySQL_and_MariaDB/image-20210824120542591.png)

![image-20210824120555583](img/Advanced_MySQL_and_MariaDB/image-20210824120555583.png)



Configuring HandlerSocket

![image-20210824120623015](img/Advanced_MySQL_and_MariaDB/image-20210824120623015.png)



sudo vi /etc/my.cnf

![image-20210824120659056](img/Advanced_MySQL_and_MariaDB/image-20210824120659056.png)



HandlerSocket Client Libraries:

Ruby, JavaScript, Scala, Haskell



Handler Socket Authentication:

Plain text. handlersocket_plain_secret, handlersocket_plain_secret_wr



Handler Socket Threads:

handlersocket_threads, handlersocket_threads_wr



Other Variables:

Timeouts, Logging Verbosity, Advanced Features, Knowledgebase at mariadb.org





## Global Transaction Identifiers and Multisource Replication

Benefit of GTIDs:

- Easily CHANGE MASTER
- Just change host and port
- Failover easier

![image-20210824121042328](img/Advanced_MySQL_and_MariaDB/image-20210824121042328.png)



## Conclusion

- Advanced Features
  - Sphinx
  - Audit plugin
  - Authentication plugin
  - Server thread pooling (optimize db connection)
- Difference with mySQL:
  - Virtual Columns
  - Progress Reporting
  - Subsecond time resolution
  - Additional user statistics

