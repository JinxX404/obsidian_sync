SQL Server uses schemas to logically group tables and other database objects.

هي logical organization لبعض الجداول الي مرتبطة ببعض 
مثلا عندي مجموعة جداول مرتبطين ببعض
انا بقسم كل مجموعه منهم ده تبع كذا وده تبع كذا 

- A database schema is a ****logical representation of data**** that shows how the data in a database should be stored logically. It shows how the data is organized and the relationship between the tables.
- Database schema contains table, field, views and relation between different keys like [primary key](https://www.geeksforgeeks.org/primary-key-in-dbms/), [foreign key](https://www.geeksforgeeks.org/foreign-key-constraint-in-sql/).
- Data are stored in the form of files which is unstructured in nature which makes accessing the data difficult. Thus to resolve the issue the data are organized in structured way with the help of database schema.
- Database schema provides the organization of data and the relationship between the stored data.
- Database schema defines a set of guidelines that control the database along with that it provides information about the way of accessing and modifying the data.
[Database Schemas - GeeksforGeeks](https://www.geeksforgeeks.org/database-schemas/)


علشان نعمل سكيما بنستخدم الامر 
```
CREATE SCHEMA schema_name
```
الاسكيما بتفيدنا لو عندنا اكتر من ادمن هيستخدمو الداتابيز وكل واحد خاص بجزء معين
ف ممكن نقسم الداتابيز لاكتر من سكيما تخص جزء معين
وكل سكيما يكون ليها ادمن يقدر يتعامل معاها 
سواء يضيف او يحذف او يعدل جداول 

بنستخدمها لغرض تنظيمي 


---
