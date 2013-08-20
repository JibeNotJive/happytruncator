happytruncator
==============

Helpful ways to truncate your datastores.



#### SQL Server
truncate table <tablename>;  

_For logged truncation:_  
delete from table <tablename>;  
  
  
#### Postgres
truncate table <tablename>;  
_For logged truncation:_  
delete from table <tablename>;  
  
  
#### Redis
flushdb  
_For absolution:_  
flushall  
