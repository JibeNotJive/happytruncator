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


#### RavenDB

var collectionsToEradicate = new List<string>
	{
		"SomeDocument",
		"AnotherDocument"
	};

foreach (var collection in collectionsToEradicate)
{
	store.DatabaseCommands.DeleteByIndex(
		"Raven/DocumentsByEntityName",
		new IndexQuery { Query = "Tag:" + collection },
		allowStale: true
		);
}
  
    
#### MySQL
sudo apt-get install -y libpq-dev postgresql-9.2 && sudo apt-get remove --purge mysql-server mysql-client mysql-common


  
#### Oracle
<ul>
<li>Build swimming pool</li>
<li>Fill it with cash money</li>
<li>Use the pool of cash to buy Oracle software</li>
<li>Load purchased software and supply data</li>
<li>delete from table <tablename>;</li>
<dl><dd>flashback table <tablename>; -- just kidding</dd></dl>
<li>truncate table <tablename>; -- no kidding</li>
</ul>
