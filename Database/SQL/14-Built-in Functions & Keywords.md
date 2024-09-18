

##### isnull()
لما يكون فيه null في Column بعرضه ف بيتعرض null 
ولو استخدمت where name is not null هيشيل الnull ويعرض الي فيهم قيمه فقط
طب لو عايز اعرض ال rows الي فيهم null بس اكتب مكان null اي قيمه تاني؟
بستخدم فانكشن isnull ببعتله اول ارجومنت اسم الcol الي هيعرضه
وتاني أرجومنت هو الي هيعرضه مكانه 
ممكن يكون اسم column تاني (مثلا ملقيش الاسم الاول يعرض التاني)
او ممكن يكون سترينج يعرضه مكانه 

The SQL Server `ISNULL()` function replaces `NULL` with a specified value. The following shows the syntax of the `ISNULL()` function:

`ISNULL(expression, replacement)`
Code language: SQL (Structured Query Language) (sql)

The `ISNULL()` function accepts two arguments:

- `expression` is an expression of any type that is checked for `NULL`.
- `replacement` is the value to be returned if the expression is `NULL`. The `replacement` must be convertible to a value of the type of the `expression`.

The `ISNULL()` function returns the `replacement` if the `expression` evaluates to `NULL`. Before returning a value, it implicitly converts the type of `replacement` to the type of the `expression` if the types of the two arguments are different.

In case the `expression` is not `NULL`, the `ISNULL()` function returns the value of the `expression`.
لو الreplacment نفسه null هيرجع null

##### coalesce()
شبه isnull لاكن بتاخد array من القيم وبتعرض اول قيمه not null فيهم
يعني هبدل الfirstname ب last 
لو ملقتش last هخليه يروح لcoulmn تالت وهكذا
اول not null هيلاقيه هيعرضه
`COALESCE(e1,[e2,...,en])`
Code language: SQL (Structured Query Language) (sql)

In this syntax, e1, e2, … en are scalar expressions that evaluate to scalar values. The `COALESCE` expression returns the first non-null expression. If all expressions evaluate to NULL, then the `COALESCE` expression return NULL;

Because the `COALESCE` is an expression, you can use it in any clause that accepts an expression such as SELECT, WHERE, GROUP BY, and HAVING

```sql
SELECT first_name,
last_name,
COALESCE(phone,'N/A') phone,
email
FROM sales.customers
ORDER BY first_name, last_name;
```
بقوله لو لقيت الphone ب null اعرض مكانه N/A علشان تكون user friendly

COALESCE vs. CASE expression

The `COALESCE` expression is a syntactic sugar of the [`CASE`](https://www.sqlservertutorial.net/sql-server-basics/sql-server-case/) expression.

The following expressions return the same result:

```sql
COALESCE(e1,e2,e3)  
VS.
CASE     
	WHEN e1 IS NOT NULL THEN e1
	WHEN e2 IS NOT NULL THEN e2
	ELSE e3 END
```

Note that the query optimizer may use the `CASE` expression to rewrite the `COALESCE` expression.



##### newid()
بترجع global universal id (GUID)
بتحط unique number and ranomaized لكل اوبجكت علي مستوي نفس السيرفر
بستخدمها في اني اجيب random rows كل مره 
بقوله order by newid() وكل مره هتعمل id مختلف وترتب بيه ف كده الاوتبوت مختلف فكل رن 


##### CASE 
بنستخدمها علشان نحط كونديشن علي حاجه 
نقدر نعمل بيها select او في الupdate للداتا

في ال select ممكن اقوله لو الsalary مثلا اكبر من كذا اعرض كذا 

```sql
select * , 
CASE 
	when Salary >=1500 then 'High'
	when Salary <1500 then 'Low'
	else 'No Data'
	end as Salary
from Employee
```
هنا هيشوف كل سالري ويحط مكانه ناتج الكونديشن
لازم الcase تنتهي ب end 
الكونديشن when then


والupdate ممكن اكون محتاج ازود السالري بنسبه معينه للناس الي اقل من رقم 
وبنسبة معينة للناس الي اكبر من رقم 
```sql
update Employee
	set Salary = 
	Case 
	when Salary >= 1500 then Salary * 1.25
	when Salary < 1500 then Salary * 1.50
	end 
```
كده هيشوف الكونديشن ويرجع رقم يتحط جوه السالري
ومش كلهم هيتغيرو بنفس النسبة



##### iif()
ميثود بستخدمها لو عندي اتنين كونديشن فقط 
زي ال ternary operator

```sql
select * , iif(Salary > 1500 , 'High' , 'Low')
from Employee
```
فالاول بتاخد اي كونديشن وبعده حالة الترو وبعدين الفولس
أقدر استخدمها فالابديت او السيليكت 



