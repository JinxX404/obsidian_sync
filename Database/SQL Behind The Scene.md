---
refrence: https://medium.com/@abil.samedov502/demystifying-the-database-engine-how-sql-works-behind-the-scenes-56859c27ef69
---
ازاي كود ال sql بيشتغل ويروح يجيب الداتا؟
ايه المراحل الي بيمر عليها؟
فيه اكتر من تقسيمه وحسب كل DBMS بيعامل الكويري ازاي 
بس كل DBMS عندها SQL Engine 

This software component acts as the brain, interpreting and executing SQL statements to interact with the stored data.
ال SQL Engine بيتصرف زي العقل الي بيترجم وينفذ الكويري علشان يتعامل مع الداتا الي متخزنه 

## **From Code to Data: The SQL Engine’s Journey in 4 Steps**

العمليه هتتقسم علي 4 خطوات من الكود للداتا 

1-**Parsing:** When you submit an SQL query, the engine first parses it. This involves breaking down the statement into individual components like keywords, table names, columns, and conditions. The parser checks for syntax errors and ensures the query adheres to the SQL grammar rules.

لما بنكتب كويري ال الengine بيعملها parse يعني بيقسمها لاجزاء وبيتشيك علي ال syntax او الجرامر بتاعت ال sql 
****_Correctness_****
The parser verifies that the SQL statement conforms to SQL semantics, or rules, that ensure the correctness of the query statement. For example, the parser checks if the SQL command ends with a semi-colon. If the semi-colon is missing, the parser returns an error.

****_Authorization_****
The parser also validates that the user running the query has the necessary authorization to manipulate the respective data. For example, only admin users might have the right to delete data.
هدف الParsing Step انه يبص علي ال Correctness , هل هي مكتوبه صح وبتمشي علي الرولز ولا فيه ساينتاكس ايرور؟ (هنرجع ايرور)
وتاني حاجه ال authorization انه يتاكد ان اليوزر الي بينفذ الكويري دي ليه اكسيس علي الداتا الي طالبها فالكويري 


2-**Query Optimization:** Once the query is parsed, the optimizer steps in. Its role is to determine the most efficient way to execute the query. This involves analyzing various factors like available indexes, table statistics, and join algorithms. The optimizer may rewrite the query or choose different execution plans to minimize resource usage and improve performance.

تاني خطوه هي ال query optimization 
بعد ما بنعمل parse 
بنبص علي ازاي هننفذ الكويري دي وايه افضل طريقه ننفذها بيها 
ممكن يختار كويري غير الي انا كتبتها علشان ممكن يكون ليها اقل resource او افضل performance 


3-**Query Execution:** With the optimized plan in hand, the engine starts executing the query. This involves accessing the relevant data from storage, performing operations like filtering and sorting, and finally returning the result set.
بعد ما بقي عندنا افضل طريقه لتنفسذ الكويري المطلوبه (ليها اقل resource وافضل performance)
ال engine هيبدا ينفذها 

4-**Transaction Management:** SQL engines ensure data integrity and consistency through transaction management. A transaction is a logical unit of work that comprises multiple operations. The engine guarantees that all operations within a transaction are either committed (applied to the database) or rolled back (undone) in case of errors or system failures.
ال transaction هي مجموعة من ال operation يخصو حاجه معينه 
اما يتنفذو مع بعض او لو واحده منهم فشلت يقدر يرجع كل ال operations الي حصلت (rollback)
يعني زي العملية البنكية , لازم يتنفذ اكتر من خطوه ك عملية واحده 
مثلا هخصم الفلوس من الحساب الاول وهزودها فالحساب التاني
طب لو تاني خطوه فشلت (اني ازود الفلوس فالحساب التاني) زي ان النور قطع والعمليه التانيه لسه متمتش؟ كده الفلوس راحت فالهوا لانها اتخصمت من مكان ومزادتش فالتاني
ف لازم الداتابيز يكون عندها القدرة تعمل transaction علشان الداتا تكون integrate , consistent
اما كلهم يتنفذو او ميتنفذوش 

----


```sql
mysql> SELECT name, age FROM users WHERE age > 18;
```

The engine parses this query, identifies the table (“users”), columns (“name”, “age”), and the filtering condition (“age > 18”). The optimizer then determines the best way to access the data, potentially utilizing an index on the “age” column. Finally, the engine retrieves the matching rows and returns the “name” and “age” values.

![](https://miro.medium.com/v2/resize:fit:864/1*PtnHexI1Yezdl6HZ-oXpag.png)