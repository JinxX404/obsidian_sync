![[Pasted image 20240707210547.png]]
SQL Server consists of two main components:

- Database Engine
- SQLOS
-بيتكون من عنصرين رئيسيين
الاول database engine الي هو النص الي فوق من الصوره 
والتاني SQLOS النص التاني من الصوره


### Database Engine
اول عنصر بيتكون منه ال SQL Server
The core component of the SQL Server is the Database Engine, **which comprises**  
1- a relational engine that processes queries 
2- a storage engine that manages database files, pages, indexes, etc.
الdatabase engine بيتكون من عنصرين
الاول هو relational engine or query processor
التاني هو storage engine


Additionally, the database engine creates database objects such as [stored procedures](https://www.sqlservertutorial.net/sql-server-stored-procedures/basic-sql-server-stored-procedures/), [views](https://www.sqlservertutorial.net/sql-server-views/), and [triggers](https://www.sqlservertutorial.net/sql-server-triggers/).

#### Relational Engine: 
هو اول عنصر فالdatabase engine

The Relational Engine contains the components that determine the optimal method for executing a query. It is also known as the **query processor**.  بينفذ الكويريز الي بنكتبها

The relational engine requests data from the storage engine based on the input query and processes the results.
وبعد ما بيبروسيس الquery بيطلب الداتا من ال storage engine

Some tasks of the relational engine include querying processing, memory management, thread and task management, buffer management, and distributed query processing.


#### Storage Engine
تاني عنصر في ال database engine 
The storage engine is responsible for storing and retrieving data from the storage systems such as disks and SAN.
مسئول عن تخزين واسترجاع الداتا من الstorage system






### SQLOS
تاني عنصر بيتكون منه ال SQL Server
Under the relational engine and storage engine lies the SQL Server Operating System, or SQLOS.

SQLOS provides various operating system services such as memory and I/O management, as well as exception handling and synchronization services.






---------
SQL Server = database engine; SQL Server Management Studio = GUI Administration Tool for working against the SQL Server engine
