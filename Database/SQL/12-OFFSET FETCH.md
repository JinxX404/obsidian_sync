ليها استخدام شبيه لselect top في انها بترجع عدد معين من الrows حسب حاجه معينه هنحددها

ممكن اعمل سكيب لعدد معين من الrows واخد الي بعدهم
بتستخدم مع order by

```sql
ORDER BY column_list [ASC |DESC] 
OFFSET offset_row_count {ROW | ROWS}
FETCH {FIRST | NEXT} fetch_row_count {ROW | ROWS} ONLY
```
- The `OFFSET` clause specifies the number of rows to skip before starting to return rows from the query. The `offset_row_count` can be a constant, variable, or parameter that is greater or equal to zero.

- The `FETCH` clause specifies the number of rows to return after the `OFFSET` clause has been processed. The `offset_row_count` can be a constant, variable, or scalar that is greater or equal to one.

- The `OFFSET` clause is mandatory while the `FETCH` clause is optional. Also, the `FIRST` and `NEXT` are synonyms, so you can use them interchangeably. Similarly, you can use the `FIRST` and `NEXT` interchangeably.


بعد order by 
بستخدم  OFFSET علشان اسكيب عدد معين 
يعني لو قولت OFFSET 10 يعني بسكيب اول 10 row

وبعدها Fetch اوبشنال 
ممكن اقوله هاتلي الnext or first 10 only 
الي هما بعد الي عملتلهم سكيب

يعني لو عندي30 row
هعمل سكيب لاول 10 
وهرجع ال10 الي بعدهم


![[Pasted image 20240728125923.png]]

> [!NOTE]
> **The OFFSET and FETCH clauses are preferable for implementing the query paging solution than the TOP clause.**
> 
