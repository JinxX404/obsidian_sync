
Window functions in SQL are a type of function that perform calculations across a set of table rows that are related to the current row. But unlike regular aggregate functions (like `SUM()` or `COUNT()`), they don’t collapse the rows into a single result. Instead, they allow you to keep the rows and still apply calculations over a "window" of rows.

- **Window**: It’s like a subset of rows related to the current row.
- **Keeps All Rows**: The result of a window function is calculated for every row, unlike aggregate functions that group rows together.
- **Common Use Cases**: Running totals, row numbering, and calculating moving averages.

مجموعة فانكشنز بتجاوبلي علي اسئلة فالبيزنس 
اسمهم window علشان بيشتغلو علي مجموعة من الداتا من غير ما يعملو collapse للrows
يعني مش هيخفوهم زي الagg functions مثلا ويرجعولي one row

الwindow fun فيه تحتها اكتر من تصنيف 
1. Aggregate Window Functions 
2. Ranking Functions 
3. Value Functions 
4. Distribution Functions 

الsyntax بتاعتها بتكون كده  , بتيجي مع الselect فقط
```sql
<function_name>(<column_name>) OVER ([PARTITION BY <column>] [ORDER BY <column>])
```
اسم الفانكشن وبعدين الcolumn الي هطبقه عليها وبعدين over () 
وجوه بعمل order by او partition by
الpartition بتقسمهم جروبات وكل جروب بيتطبق عليه الفانكشن دي

# Aggregate Window Functions

علي عكس ال normal agg function الي بترجع one row
الويندو مش بتعمل collapse for rows وبترجع الagg لكل الrows 
مثلا قسمتهم ك جروبات 
والطبيعي كان هيرجعلي ناتج لكل جروب 
لاكن فالويندو هيحط الrows الاصليه ويحط جمبها ناتج الagg للجروب ده

##### 1. **Normal Aggregate Functions**

Normal aggregate functions (like `SUM()`, `AVG()`, `COUNT()`, etc.) **combine multiple rows into a single result**. When you use them, they group rows together and return one value for the entire group. You lose the individual row details because they "collapse" the rows into a single summary.

```sql
SELECT Department, SUM(Salary) FROM employees GROUP BY Department;
```
this query will give you the **total salary per department**, but you won't see individual employee rows. The result is a single row per department.
![[Pasted image 20240916092556.png]]

##### 2. **Aggregate Window Functions**

Aggregate window functions (like `SUM() OVER()`, `AVG() OVER()`, etc.) **perform calculations over a "window" of rows**, but they **don’t collapse the rows**. Instead, they return a calculated value for **each row**, while still showing the original row data.

```sql
SELECT Employee, Department, Salary, SUM(Salary) OVER (PARTITION BY Department) AS TotalDeptSalary FROM employees;
```
  
This query will show **each employee’s salary** and the **total salary for their department** without collapsing the rows.
![[Pasted image 20240916092806.png]]
لكل جروب هيحط الميمبرز بتوعه طبيعي ويحط معاهم ناتج الagg للجروب ده
##### Main Differences:

|Feature|Normal Aggregate Functions|Aggregate Window Functions|
|---|---|---|
|**Collapsing Rows**|Rows are grouped and collapsed into one per group (e.g., `GROUP BY`)|All rows are kept, and the function is applied to each row.|
|**GROUP BY Requirement**|Typically used with `GROUP BY` to aggregate rows into groups|No `GROUP BY` needed; works with `OVER()` to define window.|
|**Row Visibility**|Individual rows are lost in the grouping|Original rows remain visible along with the aggregate value.|
|**Result Set**|One row per group|One row per original data row with aggregate calculation included.|
|**Common Use Case**|Summarizing or aggregating data|Analyzing data trends (e.g., running totals, averages within groups).|
- **Normal aggregate functions** summarize data by grouping rows and returning one result per group (good for reporting totals or averages).
- **Aggregate window functions** provide a running or grouped calculation for each row **without losing the details of the individual rows**, making them powerful for detailed analysis across multiple rows.



# Ranking Functions 

مجموعة Special Functions بتحط ارقام علي الrows 
هما 4 فانكشن , كل واحده بترقم بشكل مختلف وبنستخدم الارقام دي ف اننا نجاوب علي الاسئله الي عايزينها
وبيساعدوني اجاوب علي اسئله فالبيزنس كانت هتحتاج complex queries علشان تتحل
مثلا مين تاني او تالت اكبر سالري , دي كانت هتحتاج كذا كويري علشان تتحل 
عكس اكبر سالري كنت هستخدم فانكشن max 

- RANK()
- DENSE_RANK()
- NTILE(n)
- ROW_NUMBER()

#### ROW_NUMBER()
بتستخدم علشان ترقم الrows sequential من 1
```sql
ROW_NUMBER() OVER ( [PARTITION BY partition_expression, ... ] ORDER BY sort_expression [ASC | DESC], ... )
```
بستخدم order by لcol وبعدين بترقمهم 
لو استخدمت بارتشن بcol معين كان هيقسمهم جروبات وكل جروب يبدا يرقم فيه لوحده كانه مش شايف الجروب التاني
```sql
SELECT ROW_NUMBER() OVER ( ORDER BY first_name ) row_num, first_name, last_name, city FROM sales.customers;
```
قولتله يرقم ويعمل اوردر بالفيرست نيم ويعرض جمبه fname , lname,city
![[Pasted image 20240916094510.png]]
لو قولتله اعمل بارتشن بالنسبه للcity كان هيقسمهم جروبات ويبدا يعد فكل جروب لوحده 


#### RANK()

The rows within a partition that have the same values will receive the same rank. The rank of the first row within a partition is one. The `RANK()` function adds the number of tied rows to the tied rank to calculate the rank of the next row, therefore, the ranks may not be consecutive.

بيحط ارقام , لاكن لو لقي rows متكرره هيحطلهم نفس الرقم 
ولو استخدم الرقم ده هيعمل سكيب للي بعده 
مثلا حط ارقام 1 2 2 الي بعده هيحطله 4 لانه عمل سكيب ل3 بسبب التكرار

```sql
RANK() OVER (
    [PARTITION BY partition_expression, ... ]
    ORDER BY sort_expression [ASC | DESC], ...
)
```

```sql
SELECT v, RANK () OVER ( ORDER BY v ) rank_no FROM sales.rank_demo;
```
![[Pasted image 20240916095116.png]]
![[Pasted image 20240916095250.png]]
كل مره بيكرر الرقم بيعد ويبدا من بعده 
استخدم 3 3 3 3 ف هو عد كل الrows دي وبدا من 7 

لو استخدمت بارتشن هعمل نفس الكلام مع كل جروب لوحده


#### DENSE_RANK()

زي RANK() لاكن مش بتسكيب الرقم الي اتكرر 
لو استخدمت 1 2 2 