استخدمنا الaggregate functions علي الجدول كله
بنمسك عمود معين نجيب لكل القيم الي فيه الmax , min ..

لاكن ماذا لو عايزين نجيب قيمه الفانكشن دي لجروب معين من الصفوف؟
يعني مثلا هجمع الموظفين الي سنهم رقم معين 
يعني هلم الصفوف دي فجروب مع بعض 
وهطبق عليهم الفانكشن 

عن طريق group by
The `GROUP BY` statement groups rows that have the same values into summary rows, like "find the number of customers in each country".

The `GROUP BY` statement is often used with aggregate functions (`COUNT()`, `MAX()`, `MIN()`, `SUM()`, `AVG()`) to group the result-set by one or more columns.


```sql
SELECT _column_name(s)_  
FROM _table_name_  
WHERE _condition_  
GROUP BY _column_name(s)_
```

![A More Specific SQL COUNT Query](https://dataschool.com/assets/images/how-to-teach-people-sql/aggregations/aggregations_4.gif)

الgroup by هتمسك القيم الي هعملها جروب (القيم الفريده) وتحطهم تحت بعض
وبعدين هتمشي تنفذ الفانكشن بتاعت الaggregate بعدها الي هي count
هتمشي تاني علي الrows وتشوف ده تبع مين وتعده

اي فانكشن هعملها select هيروح ينفذها علي الحاجه الي هعملها جروب
لكل جروب لوحده


---
```sql
select category_id as "category id", sum(list_price) as "price sum for each category" , count(*)
, max(list_price) as "Maximum price for product in each category"
from production.products 
group by category_id
```
هنا بقوله اعملي الجروبات بتاعتي بناء علي ال catergory_id

وبعدين الselect هتتنفذ علي كل جروب لوحده (كل جروب هيطلع منه row من الداتا) 

فالاول هعرض الid 
وبعدين للجروب ده هجيب الsum للlist price الي ليهم نفس الid 
وبعدين هعد الصفوف دول الي ليهم نفس الid وبعدين هجيب اكبر قيمه ظهرت في الاسعار لكاتيجوري معين 

![[Pasted image 20240720141416.png]]

كده كل row بيجيب الaggregate function لجروب معين 




#### Having
عندنا كييوورد بتستخدم مع الgroup by علشان نفلتر بيها  
زي الwhere في الاستخدام العادي

ممكن اقوله رجعلي الجروبات الي ليها قيمه معينه اكبر او اقل من كذا 

مينفعش استخدم where مع ال group by
