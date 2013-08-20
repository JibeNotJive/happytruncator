happytruncator
==============

Helpful ways to truncate your datastores.



#### SQL Server
truncate table <tablename>;
For logged truncation:
delete from table <tablename>;


#### Postgres
truncate table <tablename>;
For logged truncation:
delete from table <tablename>;


#### Redis
flushdb
For absolution:
flushall
