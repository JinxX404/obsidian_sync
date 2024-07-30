
لو بدور علي قيمه معرفهاش وانا بطبق select statement
مثلا قولتله عايز الدرجات الي اكبر من المتوسط 
هل انا اعرف المتوسط؟
لا 
ف انا بعمل query جوه الquery الاصليه تجبلي المتوسط

الsub بتتنفذ الاول وبترجع قيمه تشتغل بيها الouter query

A subquery is a query nested inside another statement such as SELECT, INSERT, UPDATE, or DELETE.


A subquery is also known as an inner query or inner select, while the statement containing the subquery is called an outer select or outer query:

![SQL Server Subquery](https://www.sqlservertutorial.net/wp-content/uploads/SQL-Server-Subquery.png)

الsubquery هترجعلي مجموعه ارقام 
بقوله رجعلي order_id,order_date,customer_id لو الcustomer_id موجود جوه مجموعه الارقام الي هترجعلي
الIN استخدمناها علشان نقوله الارقام الي جوه الليست
A subquery that is used with the [IN](https://www.sqlservertutorial.net/sql-server-basics/sql-server-in/) operator returns a set of zero or more values. After the subquery returns values, the outer query makes use of them.



 

عندي keywords بستخدمها معاها 
لو الsubquery هترجع اكتر من قيمه 
مينفعش اقول > , < واقارن عادي 
بستخدم > all او > any
يعني بقوله رجعلي القيمه الي اكبر من كل القيم الي راجعالي 
![[Pasted image 20240728132448.png]]
فيه اكتر من قيمه هترجع من الsubquery 
بقوله هاتلي stdno,firstname,lastname 
لما الmark تكون اكبر من كل الي جاي من جوه الquery الداخليه


The subquery is introduced with the `ANY` operator has the following syntax:

`scalar_expression comparison_operator ANY (subquery)`

Assuming that the subquery returns a list of value v1, v2, … vn. The `ANY` operator returns `TRUE` if one of a comparison pair (`scalar_expression`, vi) evaluates to `TRUE`; otherwise, it returns `FALSE`.

For example, the following query finds the products whose list prices are greater than or equal to the average list price of any product brand.
```sql
SELECT
    product_name,
    list_price
FROM
    production.products
WHERE
    list_price >= ANY (
        SELECT
            AVG (list_price)
        FROM
            production.products
        GROUP BY
            brand_id
    )

```
هترجعلي ليست وعايز اقارن 
بقوله رجعلي العمودين دول 
لو الlist_price الي معايا حاليا اكبر من او يساوي اي رقم من الارقام الي جايلالي من الsubquery



شبهها ALL هترجعلي اي قيمه اكبر من اكبر قيمه في ال subquery




#### Nesting subquery

A subquery can be nested within another subquery. SQL Server supports up to 32 levels of nesting.

اقدر احط queries جوه بعضها لحد 32 واحده