happytruncator
==============

Helpful ways to truncate your datastores.



#### SQL Server
truncate table [tablename];  

_For logged truncation:_  
delete from table [tablename];  
  
  
#### Postgres
truncate table "tablename";  
  
_For logged truncation:_  
delete from table "tablename";  
  
  
#### Redis
flushdb  
  
_For absolution:_  
flushall  

#### MongoDB

From a mongo shell: `db.collection.drop()`, where "collection" ~= "tablename"

Usually unnecessary, as it defaults storage to /dev/null, and auto-shards across all nodes in the cluster.

MongoDB is Web Scale.  
  
#### RethinkDB
When you are serious:  
r.table('tablename').delete({durability: 'hard'}).run()  
When you are less serious:  
r.table('tablename').delete({durability: 'soft'}).run()  
When you are in a hurry:  
r.db('dbname').tableDrop('tablename').run()  
When you are OCD  (to be run before the hurry code):  
r.table('tablename').indexDrop('indexname').run()  
  
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

1. Build swimming pool
- Fill it with cash money
- Use the pool of cash to buy Oracle software
- Load purchased software and supply data
- delete from table "tablename";
- flashback table "tablename"; -- just kidding
- truncate table "tablename"; -- no kidding

#### Access

Fire
