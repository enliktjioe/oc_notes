# How to Recover Data (Without a Backup!)

https://blogs.oracle.com/sql/how-to-recover-data-without-a-backup



## Salvaging the Deleted Rows

Insert

```sql
insert into table
  select * from <table> as of timestamp sysdate – interval '1' hour
  where <conditions to find the rows>;
```

Finding deleted rows

```sql
select * from <table> as of timestamp sysdate – interval '1' hour
minus 
select * from <table>;
```

Recover

```sql
insert into <table> 
  select * from <table> as of timestamp sysdate – interval '1' hour
  minus 
  select * from <table>;
```



# Recovering deleted rows from oracle table

https://stackoverflow.com/questions/23334495/recovering-deleted-rows-from-oracle-table/23334728

You can recover the details using Oracle Flashback Query.  You could query the contents of the table as of a time before the  deletion to find out what data had been lost, and, if appropriate,  re-insert the lost data in the database. Here's the sample query: 

```sql
select * from MANUAL_TRANSACTION as of timestamp to_timestamp('28-APR-2014 12:30:00', 'DD-MON-YYYY HH:MI:SS') where ' clause based on your deleted data';
```

