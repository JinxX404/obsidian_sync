SQL (Structured Query Language) is a language to operate databases; it includes Database Creation, Database Deletion, Fetching Data Rows, Modifying & Deleting Data rows, etc.
[SQL - Overview (tutorialspoint.com)](https://www.tutorialspoint.com/sql/sql-overview.htm)
[SQL - RDBMS Concepts (tutorialspoint.com)](https://www.tutorialspoint.com/sql/sql-rdbms-concepts.htm)
[SQL Databases (tutorialspoint.com)](https://www.tutorialspoint.com/sql/sql-databases.htm)


SQL is a standardized language used to interact with RDBMSs. It allows you to perform various operations like querying data, updating records, and managing database structures.



## What are SQL commands?

Structured query language (SQL) commands are specific keywords or SQL statements that developers use to manipulate the data stored in a relational database. You can categorize SQL commands as follows.

### **Data definition language** 

Data definition language (DDL) refers to SQL commands that design the database structure. Database engineers use DDL to create and modify database objects based on the business requirements. For example, the database engineer uses the CREATE command to create database objects such as tables, views, and indexes.
بتعدل علي الاستراكشر بتاعت الداتابيز 
يعني هنمسح او نعدل او نضيف اوبجكت فالداتابيز زي الفيو او الSP او جدول او اندكس 

![](https://img.brainkart.com/imagebk38/rVFCPrd.jpg)




### **Data query language**

Data query language (DQL) consists of instructions for retrieving data stored in relational databases. Software applications use the SELECT command to filter and return specific results from a SQL table. 
بنعمل بيها استعلام query علي الجداول 

### **Data manipulation language**

Data manipulation language (DML) statements write new information or modify existing records in a relational database. For example, an application uses the INSERT command to store a new record in the database.
بنضيف او نمسح او نعدل فالداتا الي فالجداول
### **Data control language**

Database administrators use data control language (DCL) to manage or authorize database access for other users. For example, they can use the GRANT command to permit certain applications to manipulate one or more tables. 
تخص جزء ال administration 
### **Transaction control language**

The relational engine uses transaction control language (TCL) to automatically make database changes. For example, the database uses the ROLLBACK command to undo an erroneous transaction.


## What are SQL standards?

SQL standards are a set of formally defined guidelines of the structured query language (SQL). The American National Standards Institute (ANSI) and International Organization for Standardization (ISO) adopted the SQL standards in 1986. Software vendors use the ANSI SQL standards to build SQL database software for developers.
عندنا ANSI SQL هو الاستاندرد للsql وكل شركة بتعمل نسخة الsql الخاصه بيها علشان تشتغل بيها علي منتجاتها 
لاكن معظمهم متشابهين بسبب انهم واخدين الqueries من ال ANSI SQL 
والفروقات ما بينهم بتكون هي اضافات كل شركة للنسخة بتاعتها

