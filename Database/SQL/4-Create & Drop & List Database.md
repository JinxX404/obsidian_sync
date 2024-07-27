
Database tables are objects that store all the data in a database. In a table, data is logically organized in a row-and-column format, similar to a spreadsheet.

Each row represents a unique record in a table, and each column represents a field in the record.

---

The **CREATE DATABASE** statement is a DDL (Data Definition Language) statement used to create a new database in SQL. If you are creating your database on Linux or Unix, then **database names are case-sensitive**, even though SQL keywords are case-insensitive. If you are working on Windows then this restriction does not apply.
فالاول خالص بنكتب في فايل الكويري 

```sql
USE master;
```


عندي طريقتين 
اما من ال wizard window بعمل نيو داتابيز وبحدد 
او من الكوماند 
في الكوماند بعمله بطريقتين 
اما simple  
```sql
CREATE DATABASE databasename 
```
وبتاخد الخواص بتاعتها من ال model database 

او بنعمل الكوماند تفصيلي شويه ونحدد فيه السايز والماكس والجروث بتوع فايلات الداتا واللوج 

```sql
USE master;
GO
CREATE DATABASE Sales 
ON
(NAME = Sales_dat,
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\DATA\saledat.mdf',
    SIZE = 10,
    MAXSIZE = 50,
    FILEGROWTH = 5)
LOG ON
(NAME = Sales_log,
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\DATA\salelog.ldf',
    SIZE = 5 MB,
    MAXSIZE = 25 MB,
    FILEGROWTH = 5 MB);
GO
```
الname الي فالكوماند هو اسم الفايل سواء اللوج او الداتا 
وبعدهم اللوكيشن والسايز والماكس والجروث
اسم الطريقة Transact-SQL

[Create a database - SQL Server | Microsoft Learn](https://learn.microsoft.com/en-us/sql/relational-databases/databases/create-a-database?view=sql-server-ver16)
[SQL CREATE DATABASE Statement (geeksforgeeks.org)](https://www.geeksforgeeks.org/sql-create-database/)
[SQL - DROP Database (tutorialspoint.com)](https://www.tutorialspoint.com/sql/sql-drop-database.htm)
---
علشان نمسح الداتابيز الي عملناها بنستخدم الدروب كوماند 
The SQL **DROP DATABASE** statement is used to delete an existing database along with all the data such as tables, views, indexes, stored procedures, and constraints.

```sql
DROP DATABASE DatabaseName;
```
## SQL DROP DATABASE IF EXISTS Statement

The SQL **DROP DATABASE IF EXISTS** statement includes a condition to check whether the database exists before trying to delete it. If the database does not exist in the database system, the "DROP DATABASE IF EXISTS" statement does not raise an error, but it simply terminates without taking any action.

### Syntax

```sql
DROP DATABASE IF EXISTS DatabaseName;
```


لو عندي اكتر من داتابيز بفصلهم ب , 

---

## List Databases in SQL

Now we will verify whether the new database that we have just created has been successfully added to our system or not. 

We use the ****SHOW DATABASES**** command and it will return a list of databases that exist in our system. Now we will look for the name of the database that we have just created.


```sql
SHOW DATABASES
```

