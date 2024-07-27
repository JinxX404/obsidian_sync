```sql
SELECT select_list FROM  schema_name.table_name;
```

In this syntax:

- First, specify a list of comma-separated columns from which you want to query data in the `SELECT` clause.
- Second, specify the table name and its schema in the `FROM` clause.

لما بيشتغل علي الselect
فالاول بيتنفذ الfrom وبعدين الselect
When processing the `SELECT` statement, SQL Server first processes the `FROM` clause, followed by the `SELECT` clause, even though the `SELECT` clause appears first in the query:

![SQL Server SELECT - clause order evaluation](https://www.sqlservertutorial.net/wp-content/uploads/SQL-Server-SELECT-clause-order-evaluation.png)



---
### WHERE clause
بنستخدمه علشان نعمل بيه فلتر 
To filter rows based on one or more conditions

  ```sql
   SELECT * FROM sales.customers WHERE state = 'CA';
  ```  

When the WHERE clause is present, SQL Server processes the clauses of the query in the following sequence: `FROM`, `WHERE`, and `SELECT`.

![SQL Server SELECT - from where select](https://www.sqlservertutorial.net/wp-content/uploads/SQL-Server-SELECT-from-where-select.png)


فيه operators بتيجي بعد الwhere علشان تحدد حاجه معينه 
زي >,< , <= , >= , != , <>
ال <> هي هي != لا يساوي

عندنا حاجات تاني زي is null
لما احتاج اجيب الnull values مقدرش اقول = null 
بستخدم معاها is null 
```sql
select * from customers
where phone is null
```
مكنش ينفع اقول where phone = null 

عكسها is not null هترجعلي الfields الي فيها قيم (مش فاضيه)


عندنا operator تاني اسمه in operator 
نقدر نستخدم الin في subquery (كويري جوه كويري ,الي جوه بترجع حاجه بيستخدمها الي بره)
بيوفر عليا استخدام الor في الكونديشن 
مثلا بدلا من 
```sql
select * from customers 
where state = 'CA' or state = 'NY' or state = 'TX' or state = 'XY' or state = 'XZ'
```
كده الor هتكبر عندي الشرط 
اقدر استخدم مكانه in operator
```sql
select * from customrs 
where state in ('CA','NY','TX','XY','XZ')
```


نقدر نستخدم عكس in ب not in operator

```sql
select * from customrs 
where state not in ('CA','NY','TX','XY','XZ')
```


عندنا operator تاني اسمه between وعكسه not between
بيدور علي القيم في رينج معين او بره رينج معين 
لو عايز ارجع سعر بين 300 و 600 (ال300و600 محسوبين)
هقدر اعملها ب and

```sql
select * from customrs 
where price >= 300 and price <= 600
```

الحل التاني اني هستخدم between
```sql
select * from customrs 
where price between 300 and 600
```

وعكسها not between لو عايز حاجه اكبر واقل من الرقمين دول



---
### NULL

In the database world, `NULL` is used to indicate the absenceغياب  of any data value. For example, when recording the customer information, the email may be unknown, so you record it as `NULL` in the database.

الاكسبريشن بيكون اما ترو او فولس لاكن الnull بتجيبلي حاجه تالته وهي unknown 
Typically, the result of a logical expression is `TRUE` or `FALSE`. However, when `NULL` is involved in the logical evaluation, the result can be `UNKNOWN`. Therefore, a logical expression may return one of three-valued logic: `TRUE`, `FALSE`, and `UNKNOWN`.

The results of the following comparisons are `UNKNOWN`:


```
NULL = 0 
NULL <> 0 
NULL > 0
NULL = NULL
```
الnull مش بيساوي حاجه ولا حتي نفسه 
الاكسبريشنز الي فوق هيدولنا unknown

The `NULL` does not equal anything, not even itself. It means that `NULL` is not equal to `NULL` because each `NULL` could be different.

لما نحتاج نتشيك علي الnull بنستخدم اما is null او is not null


---
### AND Operator
The `AND` is a logical operator that allows you to combine two Boolean expressions. It returns `TRUE` only when both expressions evaluate to `TRUE`.

The `boolean_expression` is any valid Boolean expression that evaluates to `TRUE`, `FALSE`, and `UNKNOWN`.

![[Pasted image 20240710115820.png]]


```sql
WHERE brand_id = 1 OR brand_id = 2 AND list_price > 1000
```
الsql بينفذ الand الاول 
يعني هيجيب الي ليهم brand_id = 2 و list_price > 1000 وبعدين هيرجع اي brand_id = 1

لو عايز الor يتنفذ فالاول هحطه بين قوسين



---
### OR Operator
  is a logical operator that allows you to combine two Boolean expressions. It returns `TRUE` when either of the conditions evaluates to `TRUE`.
![[Pasted image 20240710121227.png]]



بينفذ الAND فالاول
لو لقي and مع or هياخد الاند فالاول وبعدين or


- By default, SQL Server evaluates the `OR` operators after the `AND` operators within the same expression. But you can use parentheses `()` to change the order of evaluation.

---

### Distinct keyword 
ديستينكت يعني فريد او مميز 
بستخدمه علشان ارجع القيم المميزه الي ظهرت بدون تكرار 
مثلا جدول فيه عدد مدن وفيهم مدن مكرره 
انا عايز ارجع اسماء المدن بدون تكرار (لو فيه اكتر من قيمه لنفس المدينه هيرجعلي واحده فقط)

```sql
select DISTINCT city from CITIES
```
بنكتبها قبل اسم الcolumn 

لو عندي اكتر من column هيدور علي الcombination دي ويجيبها مره واحده 
مثلا 
```sql
select DISTINCT city , population from CITIES
```
هيرجع الcombinations الفريده ما بينهم 
مثلا 
ny 100
ny 200 
xy 100 
xy 101 
لو عملت الكويري الي فوق هترجعلي كل القيم دي 
لانهم كده مش مكررين (الاتنين column مختلفين)

لو فيه row اتكرر مرتين بنفس القيم ونفذنا الكويري هيرجع واحده بس منهم


---
### Like Operator
بستخدمه لو بدور علي حاجه مش مكتمله بالنسبالي 
(لو المعلومة مش عارف احدد مواصفاتها بالظبط)

ممكن مثلا بدور علي اسم شخص انا عارف اسمه الاول بس مش عارف اسمه التاني

مثلا عايز الاسماء الي بتبدا بحرف كذا او بتنتهي بكذا
او الي اسمهم بيحتوي علي مقطع معين 

بدور علي باترن معين 

عندي characters (wildcards) بستخدمهم مع الlike 

ال% بيعبر عن any string of zero or more characters
لو ناقصني مقطع من الاسم ومش عارف طوله قد ايه (ممكن واحد او اتنين او تلاته ....)

ال __ بتعوض عن حرف واحد فقط 
لو ناقصني حرفين هحط مكانهم اتنين underscore وهكذا

فيه wildcard تاني زي  [ ] لو عايز اختار ما بين حرفين مثلا A او B بحطهم جوه ال  [AB]  هنا اي حاجه بتبدا ب A او B هيرجعها
لو محتار ما بين رينج معين بستخدم ال- بين الحرفين [A - C] كده اي حد ما بين A و C

فيه الcaret (^) معناها not 
لو بدور في رينج اقدر اقوله مش فالرينج ده **[A-B^]** يعني مش بين A و B

نقدر نعمل not like 

نقدر نستخدمها مع الارقام مش سترينج فقط

```sql
last_name LIKE 'z%'
```
هترجعلي اي حد بيبدا ب z (حطيت % بعدها لانها بتعبر عن اي عدد من الحروف) يعني اي حد بيبدا بz ومش مهم الي بعده كام حرف

```sql
last_name LIKE '%er'
```
هنا هترجعلي اي عدد من الحروف فالاول وبيكونو بينتهو ب er


```sql
last_name LIKE 't%s' 
```
اي سترينج بيبدا بt وينتهي ب s وبينهم اي عدد من الحروف



```sql
last_name LIKE '_u'
```
الاندرسكور بتعبر عن عدد محدد من الحروف يعني هنا بدور علي سترينج من حرفين وانا عارف تاني حرف فقط 
لاكن هيعوض عن اي حرف يلاقيه فاول اندكس
يعني اي سترينج زي كده هيرجع au , bu , cu وهكذا


```sql
last_name LIKE '_u%'
```
بتعبر عن اي سترينج فيه تاني حرف u وبينتهي باي عدد من الحروف
يعني لازم يكون تاني حرف u مع اي حرف فالاول واي عدد من الحروف فالاخر



```sql
last_name LIKE '[YZ]%'
```
اي Y او Z فالاول مع اي عدد من الحروف بعدهم



```sql
last_name LIKE '[A-C]%' 
```
اي حاجه بتبدا بحروف من A ل C وبعدهم اي عدد من الحروف


```sql
last_name LIKE '[^A-X]%'
```
ال^ معناها انه مش في رينج A ل X



```sql
first_name NOT LIKE 'A%'
```

معناها مش بتبدا ب A 




كنا بنستخدم ال% كspecial character من ضمن الlike 
لو عايزين ندور علي حاجه فيها % نعمل ايه؟
عايزين clause جديده تقولنا انه ال% دي حرف عادل 
محتاجين نعمل escape 

مثلا عايزين نسيرش عن 30% جوه سترينج معين 
هنقوله
```sql
   `comment LIKE '%30!%%' ESCAPE '!';'
```
اول % دي بتعبر عن اي عدد من الاسترينج فالاول
واخر % بتعبر عن اي عدد من الاسترينج فالاخر 
ال 30!% هي دي ال30% الي بندور عليها لاكن حطينا بينهم ! علشان نحدد بعدها للsql انه يعمل escape للحرف الي بعد ! وميعاملهوش ك special character 

You can replace ! with any other character you prefer, as long as it does not appear in the text you are searching for or in the pattern itself.


---
### ORDER BY clause
to sort the rows in a result set based on one or more columns

```sql
SELECT
    *
FROM
    sales.customers
WHERE
    state = 'CA'
ORDER BY
    first_name;
```
order by default orders at ascending order

In this case, SQL Server processes the clauses of the query in the following sequence: `FROM`, `WHERE`, `SELECT`, and `ORDER BY`.

![SQL Server SELECT - from where select order by](https://www.sqlservertutorial.net/wp-content/uploads/SQL-Server-SELECT-from-where-select-order-by.png)

بتكون فاخر الquery (اخر clause بنضيفه)

بنستخدمها علشان نرتب الداتا الي راجعالنا 
ديفولت بترتبهم تصاعديا asc
ولو عايز تنازليا بستخدم desc 

لو سترينج بيترتب alphabetically

نقدر نرتب بالنسبه لاكتر من column 
لو عندي اكتر من حاجه بمشي عليهم بالترتيب
مثلا فالاول برتب حسب الcity وبعده first_name
يبقي هرتب الcity ولكل مجموعة city شبه بعض هرتب جواهم بالfirst_name

```sql
FROM sales.customers ORDER BY city, first_name;
```
![[Pasted image 20240710114121.png]]
فالاول هرتب عمود الcity 
والي ليهم نفس الcity هروح ارتب بعدهم الfirst_name بتاعهم

اقدر احدد كل واحد فيهم تصاعدي او تنازلي (مش شرط يكونو زي بعض)


اقدر اعمل order by اي column طلاما موجود عندي فالtable مش شرط يكون الcolumn ده معروض معايا فال select statement


```sql
FROM sales.customers ORDER BY LEN(first_name) DESC;
```
فانكشن len بترجع طول الاسترينج 
هنا بيرتب تنازليا بالنسبه لطول الfirst_name 



```sql
FROM sales.customers ORDER BY 1, 2;
```

نقدر نحدد الorder by ب ordinal positions of columns 
يعني نقوله order by 1 2  
يعني رتب بالنسبه للcolumn الاول وبعدين بالنسبه للcolumn التاني فالselect statement بس دي مش الbest practice والافضل اننا نستخدم الاسماء بتاعت الcolumns


اقدر اعمل order بجزء معين من سترينج 
هاخد substring وهعمل order by عليه
https://stackoverflow.com/questions/4785424/how-to-order-by-certain-part-of-a-string

https://www.ibm.com/docs/ko/informix-servers/14.10?topic=clause-ordering-by-substring

```sql
SELECT SUBSTRING(CustomerName, 1, 5) AS ExtractString from Customers
```
بجيب substring معين طوله 5 (من البدايه و5 حروف بعده)
من الcolumn الي اسمه customerName جوه customers
هيرجعلي كل الrows فيها الsubstring بتاعته
![[Pasted image 20240710152449.png]]




For last characters you can use minus values, for example if you want to order by last three characters, order by SUBSTRING(Name , LEN(Name) - 2 , 3)

لو عايز اجيب الاسترينج من الاخر 
مثلا اخر 3 كاركتر 
الsubstring بتاخد  3 بارمتر 
الاول هو الcolumn بتاعك وبعدين البدايه وبعد العدد الي هاخده 
لو انا عايز اخر 3  
هحدد البدايه بتاعتي (هي هتكون الlength ناقص اتنين لان الاندكس بيبدا من 1)
وبعدين هقوله عايز كام حرف بعده 

مثلا moataz عايز اخر 3 
البدايه بتاعتي هي len(moataz) الي هو 6 هطرح منه 2 يبقي 4 
هبدا من اندكس 4 عند حرف الt 
وهقوله عايز بعده 3 يعني هرجع t a z


```
SUBSTRING(column_name, LEN(column_name) - (N - 1), N)
```
الn هي عدد الحروف الي عايز ارجعها من الاخر