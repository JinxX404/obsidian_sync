| Function                                                                                   | Description                                                                          |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| [ABS](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-abs/)         | Return the absolute value of a number.                                               |
| [ACOS](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-acos/)       | Return an angle (in radians) of a specified cosine.                                  |
| [ASIN](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-asin/)       | Return an angle (in radians) of a specified sine.                                    |
| [ATAN](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-atan/)       | Return the arctangent (in radians) of a specified tangent.                           |
| [CEILING](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-ceiling/) | Round a number to the nearest integer greater than or equal to the input number.     |
| [COS](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-cos/)         | Return the cosine of the specified angle, measured in radians.                       |
| [COT](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-cot/)         | Return the cotangent of the specified angle, which is the reciprocal of the tangent. |
| [DEGREES](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-degrees/) | Convert an angle value in radians to degrees.                                        |
| [EXP](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-exp/)         | Return the exponential value of a number.                                            |
| [FLOOR](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-floor/)     | Round a number to the nearest integer less than or equal to the input value.         |
| [LOG](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-log/)         | Return the natural logarithm of a float with a specific base (default to e).         |
| [PI](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-pi/)           | Return the constant value of PI, accurate to 15 digits.                              |
| [POWER](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-power/)     | Return the result of raising a number to a specific power.                           |
| [RAND](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-rand/)       | Return a random float between 0 and 1.                                               |
| [RADIANS](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-radians/) | Convert an angle value in degrees to radians.                                        |
| [ROUND](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-round/)     | Return a number rounded to a specified precision.                                    |
| [SIGN](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-sign/)       | Return the sign of a number, 1 for positive, -1 for negative, and 0 for zero.        |
| [SIN](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-sin/)         | Return the sine of an angle in radians.                                              |
| [SQRT](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-sqrt/)       | Return the square root of a float.                                                   |
| [SQUARE](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-square/)   | Return the square of a number.                                                       |
| [TAN](https://www.sqlservertutorial.net/sql-server-math-functions/sql-server-tan/)         | Return the tangent of the specified angle, measured in radians.                      |


هنمسك منهم الفانكشنز المهمه بالنسبالنا ونشرحها

##### ABS()
بترجعلي الabsolute value بتاعت رقم 

```sql
SELECT Abs(-243.5) AS AbsNum;
```
بقوله هات الabs بتاع رقم , ورجعلي الناتج في column اسمه AbsNum

ممكن يديلنا overflow لما نجيب الabs لرقم بره رينج داتا تايب معين 
```sql
DECLARE @x INT;
SET @x = -2147483648; 
SELECT ABS(@x);
```
هنا الرينج للint من -2,147,483,648  <  2,147,483,647

لو جبت الabs لل -2147483648 هتديلي الموجب 2147483648 وده بره الرينج فهتدي ايرور overflow

لو استخدمتها علي column هترجع قيم الabsoulte للrows دي
![[Pasted image 20240715083611.png]]
هيرجعلي الabs بتاعت كل قيمه في temp ويطرح منها 0.25





##### Ceiling()
Round a number to the nearest integer greater than or equal to the input number.
بتعمل ceil يعني هتوصل الرقم لاقرب رقم اكبر منه 


اقدر استخدمها علي جدول وترجعلي كل قيمه في row عادي


##### Floor()
Round a number to the nearest integer less than or equal to the input value.
عكس الceil 
الfloor بترجع اقل قيمه اقرب من الرقم بتاعي


##### Round()

 allows you to round a number to a specified precision.
```sql
ROUND(number, length [, operation])
```
###### 1) number

`number` is a numeric value or a numeric expression you want to round.
اول بارمتر هو الرقم الي هعمل عليه راوند
###### 2) length

The `length` specifies the precision that you want to round the `number`.

The `length` argument can be a literal number or a numeric expression. The type of the `length` must be either `tinyint`, `smallint`, or int.

The `length` can be positive or negative. If the `length` is a positive number, the function rounds `number` to a precision specified by `length`.
When the `length` is a negative number, the function rounds the `number` on the left side of the decimal point, as specified by `length`.

###### 3) operation

The `operation` indicates the type of operation that the `ROUND()` function will perform.

- If the `operation` is 0, the `ROUND` function will **round** the number.
- If the `operation` is not zero, the `ROUND()` function will **truncate** the number.

The `operation` parameter is optional and defaults to 0.

###### Rounding algorithm

The `ROUND()` function uses the **rounding to the nearest digit**
algorithm. Here are the steps the `ROUND()` function does when rounding a number:

- First, determine the desired number of decimal places to round as specified by the `length` argument.
- Second, find the digit immediately to the right of the desired decimal place. الرقم الي بعد اللينث الي اخترته 
مثلا اخترت length ب 2 يبقا هبص علي الرقم التالت
- Third, if that digit is 5 or greater, the function will **round up** the digit at the desired decimal place. If it is less than 5, the function will leave the digit unchanged.
لو الرقم ده ب5 او اكبر , هعمل راوند للرقم الي الي اخترته فاللينث الي هو في مكان 2 
لو اقل من 5 هسيبه زي ما هو
- Finally, change all digits to the right of the desired decimal place to zero. وبعدين هغير الارقام الي بعد اللينث لزيرو


###### Truncate
البارمتر التالت بيعبر عن الtruncate وهو اوبشنال والديفولت بتاعه زيرو
الزيرو هنا يعني هشتغل rounding 

لو اي رقم غير زيرو (1 10 100 1000 اي قيمه)  في تالت بارمتر
هيعتبر انه العمليه truncating مش rounding

يعني هيروح يقطع الجزء ده (طول بارمتر اللينث) ويرجعه من غير ما يعمل round ليه
```
(1, 123.4567),
(2, 234.5678), 
(3, 345.6789);
```
![[Pasted image 20240715091511.png]]
قولتله عايز اعمل truncate فحددت تالت ارجومنت باي رقم non zero

والطول الي هعمل بيه truncate بحدده في تاني ارجومنت

###### Negative Round
<-- todo -->




----
##### CAST()
بتحول ما بين داتا تايب والتاني explicitly 
بستخدم CAST وبديلها القيمه , وبعدها AS الداتا تايب الي عايزها 
```sql
 CAST( ROUND(SUM(LAT_N) , 2) AS DECIMAL(10,2) )
```
هاخد قيمع الراوند وهعمله كاست لديسمل برقمين بعد العلامه العشريه
بستخدمها ف اني اشيل الاصفار الي بتكون زياده عاليمين بعد الراوند