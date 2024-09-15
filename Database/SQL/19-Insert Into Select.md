هعمل ايه لو عايز انقل الداتا من جدول لجدول تاني 
معايا الجدول جاهز وعايز انسخ الداتا فقط 

هستخدم insert into وبعدها values علشان اضيف قيم معينه 
لاكن لو عايز اخد الداتا دي من جدول تاني هاخدها ب Select
يعني كده :
```sql
insert into table1 
select * from student
```
هاخد داتا من الكويري التانيه وهعملها insert فالاولي
لازم يكونو نفس الاستراكشر
الطريقه اسمها insert based in select 

https://www.sqlservertutorial.net/sql-server-basics/sql-server-insert-into-select/

