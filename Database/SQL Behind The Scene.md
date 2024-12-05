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
