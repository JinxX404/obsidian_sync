An aggregate function operates on a set of values and returns a single value. In practice, you often use aggregate functions with the [GROUP BY](https://www.sqlservertutorial.net/sql-server-basics/sql-server-group-by/) clause and [HAVING](https://www.sqlservertutorial.net/sql-server-basics/sql-server-having/) clause to aggregate values within groups.

شويه فانكشنز بنسميهم summary functions بيشتغلو عالداتا ويدولنا منها معلومات 
من اشهرهم

| AVG             | Calculate the average of non-NULL values in a set of values.<br> بترجع المتوسط بتاع عمود معين                                                                                      |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| COUNT           | Return the number of rows in a group that satisfy a condition.    بترجع عدد الصفوف في عمود معين <br>-مش بترجع الnull values.                                                       |
| COUNT(*)        | Return the number of rows from a table, which meets a certain condition.<br>بترجع عدد الصفوف من ضمنهم الnull <br>ممكن احط *<br> او اي عمود بيقبل non-null <br>زي الprimary key<br> |
| COUNT(DISTINCT) | Return the number of unique values in a column that meets a certain condition.                                                                                                     |
| MAX             | Return the highest value (maximum) in a set of non-NULL values. اكبر قيمه فالعمود                                                                                                  |
| MIN             | Return the lowest value (minimum) in a set of non-NULL values.                                                                                                                     |
| SUM             | Return the summation of all non-NULL values in a set. بترجع مجموع القيم في العمود                                                                                                  |
Aggregate functions ignore null values (except for `COUNT()`).

general syntax of an aggregate function:

`aggregate_function_name( [DISTINCT | ALL] expression)`

لو عايزين نطبق الفانكشن علي القيم الفريده في الcolumn هنستخدم distinct 
COUNT(DISTINCT columnname)
كده هيطبق الفانكشن علي القيم الفريده في الcolumn ده
https://www.sqlservertutorial.net/sql-server-aggregate-functions/sql-server-count-distinct/


نقدر نستخدم بعدهم where ونفلتر حسب حاجه معينه


لو استخدمت count مع اسم الcolumn مش هيحسب الnull values 
لو استخدمت   count( * ) هيرجعلي العدد بالnull 

كل الagg fun مش بيحسبو الnull values 

لو هعمل Select statement فيها agg fun وجمبها column عادي
لازم اعمل group by بالcol ده
مينفعش ارجع agg مع col كامل
لان الagg بترجع Single value يعني one row
لاكن الcol هيرجع عمود كامل
وده ميعتبرش table ف علشان كده هتدي ايرور
![[Pasted image 20240827162226.png]]
الgroup by هتلم القيم المتشابهة مع بعض فالcol ده وهتحسب لكل قيمه فيهم agg مختلفه