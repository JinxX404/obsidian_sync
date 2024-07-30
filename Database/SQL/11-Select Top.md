
The `SELECT TOP` clause allows you to limit the number of rows or percentage of rows returned in a query result set.

Because the order of rows stored in a table is unspecified, the `SELECT TOP` statement is always used in conjunction with the ORDER BY  clause. Therefore, the result set is limited to the first `N` number of ordered rows. 

```sql
SELECT TOP (expression) [PERCENT] [WITH TIES] FROM table_name ORDER BY column_name;
```

الselect statement الديفولت بتاعها انه بيجيب كل الrows 
لاكن لو عايز اجيب عدد معين من كل الrows دي بستخدم top
بقوله select top وبعدها رقم او نسبة مئوية 

بتستخدم مع order by
مثلا رتبت المرتبات تنازليا وعايز اجيب اكبر 10 مرتبات فيهم 
هعمل select top 10 salaries from employee order by salaries desc 

لو استخدمت percent وطلع رقم كسر 
يعني قال ان النسبه 5% يعني 5.5 row 
بيعمل round up ويرجع 6


----
### With Ties
الكيوورد دي بستخدمها مع top 
بتبص علي اخر قيمه فالتوب سيليكت بتاعتنا 
ولو لقيت قيم تاني ليها نفس قيمه اخر Row فالselect top 
هترجع الباقيين 

يعني لو عندي 
10  
10
5
5
5
5
5 
20

واستخدمت select  top 3
هترجعلي 10 10 5

لو استخدمت select top with ties
هتشوف اخر قيمه الي هي 5 
لو فيه تحتها خمسات تاني هترجعهم 
10
10
5
5
5
5
5

The `WITH TIES` allows you to return additional rows with values that match those of the last row in the limited result set. Note that `WITH TIES` may result in more rows being returned than specified in the expression.

For example, if you want to return the most expensive products, you can use the `TOP 1`. However, if two or more products have the same prices as the most expensive product, then you may miss the other most expensive products in the result set.

To avoid this, you can use `TOP 1 WITH TIES`. It will include not only the first expensive product but also the second one, and so forth.

![[Pasted image 20240728122422.png]]