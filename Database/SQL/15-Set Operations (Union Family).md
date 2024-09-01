combine the results of two or more queries into a single result set.
بنستخدم الset operations علشان ندمج الناتج بتاع جدولين مع بعض 

يعني كاني بعمل select وتحتها select وعايز ادمج الاتنين تحت بعض فجدول واحد يعني يجيب ناتج الاول ويلزق تحته ناتح الجدول التاني 

لازم يكون الselect فالاتنين واخدين نفس عدد الColumns ونفس Data types

#### Union All
بتدمج الجدولين تحت بعض بدون اي عمليه زياده (اسرع من union) وبيكون فيها تكرار (لو حاجه موجوده فالجدولين هترجع زي ما هي)
```
query_1 
UNION ALL
query_2
```
- The number and the order of the columns must be the same in both queries.
- The data types of the corresponding columns must be the same or compatible.


#### Union
بتعمل عمليات قبل ما ترجع الناتج 
بترتب وتشيل المتكرر علي عكس union all

الناتج الي بيرجع بيكون واخد اسم اول جدول
لو عايز اغير اسمه هغير الاسم في اول Select



#### UNION vs. JOIN

The join such as INNER JOIN or LEFT JOIN combines **columns** from two tables while the `UNION` combines **rows** from two queries.

In other words, join appends the result sets horizontally while union appends the result set vertically.

The following picture illustrates the main difference between `UNION` and `JOIN`:

![SQL Server UNION vs JOIN](https://www.sqlservertutorial.net/wp-content/uploads/SQL-Server-UNION-vs-JOIN.png)



#### Intersect
combines result sets of two or more queries and returns distinct rows that are output by both queries.

```
query_1
INTERSECT
query_2
```

Similar to the UNION operator, the queries in the syntax above must conform to the following rules:

- Both queries must have the same number and order of columns.
- The data type of the corresponding columns must be the same or compatible.

![SQL Server INTERSECT Illustration](https://www.sqlservertutorial.net/wp-content/uploads/SQL-Server-INTERSECT-Illustration.png)

بتجيب المتشابه ما بين الاتنين select 
وبترتبهم وبتشيل التكرار



#### Except
بقوله هات الي موجود فالاولي ومش موجود فالتانيه
compares the result sets of two queries and returns the [distinct](https://www.sqlservertutorial.net/sql-server-basics/sql-server-select-distinct/) rows from the first query that are not output by the second query. In other words, the `EXCEPT` subtracts the result set of a query from another.
بطرح اول select من التانيه وبرجع الاوتبوت 

يعني الاول لو فيه 1 2 3 4 والتاني  2 3
وطرحتهم من بعض هيديلي 1 4 وده الناتج الي موجود فالاول ومش موجود فالتاني
بترتبهم وتشيل المتكرر 
![[Pasted image 20240828113727.png]]
In this illustration:

- T1 result set includes 1, 2, and 3.
- T2 result set includes 2, 3, and 4.

The `except` of the T1 and T2 returns 1 which is the distinct row from the T1 result set that does not appear in the T2 result set.