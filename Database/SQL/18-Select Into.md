السينتاكس ده DDL 
بستخدمه علشان اخد داتا من جدول واحطها فجدول تاني (يكون نفس الاستراكشر) بيعمل create لtable بدلالة table تاني (كوبي بيست للداتا)
The `SELECT INTO` statement [creates a new table](https://www.sqlservertutorial.net/sql-server-basics/sql-server-create-table/) and [inserts rows](https://www.sqlservertutorial.net/sql-server-basics/sql-server-insert/) from the query into it.


```sql
select * into table2 
from Student
```
بقوله خد الداتا من student واعمل بيها table2 
ممكن اخد columns معينه 
ممكن احط كونديشنز علي الداتا الي عايز انقلها لجدول جديد


ممكن اعمل بيها جدول جديد بنفس الاستراكشر بدون ما ينقل الداتا 
هحطله كونديشن مستحيل يتحقق ف مش هيلاقي داتا ينقلها
لاكن هيعمل الجدول الجديد بنفس الاستراكشر وهيسيبه فاضي 
```sql
select * into table2 
from Student
where 1 = 2
```
الكونديشن ده مش هيتحقق ف مش هيلاقي داتا ينسخها
لاكن هيعمل الجدول (بنفس اسماء الcol والداتاتايب)


https://www.sqlservertutorial.net/sql-server-basics/sql-server-select-into/
