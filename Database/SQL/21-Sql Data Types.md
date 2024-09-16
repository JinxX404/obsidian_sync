https://www.sqlservertutorial.net/sql-server-basics/sql-server-data-types/

![[Pasted image 20240916122509.png]]
الsql server فيه كذا كاتيجوري للداتا تايب 
- numeric
- decimal 
- char 
- datetime 
- binary 

##### numeric 

``` 
--bit   bool  0:1   true:false 
--tinyint		 1 byte       -128:+127  unsigned 0:255
--smallint		 2 byte	 -32768:+32767 unsigned 0:65555 
--int		   	 4 byte
--big int	   	 8 byte
```

- TINYINT
TINYINT is an 8-bit unsigned integer data type, representing small non-negative whole numbers.

**Range: 0 to 255.**

- **SMALLINT**
is a 16-bit signed integer data type suitable for smaller whole
numbers. 

**Range: -32,768 to 32,767.**

- **INT**
is a 32-bit signed integer data type used to store whole numbers without decimal places.

**Range: -2,147,483,648 to 2,147,483,647.**

- **BIGINT**
is a 64-bit signed integer data type, allowing the storage of larger whole numbers.

**Range: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.**


##### decimal 
```
--smallmoney 4 byte   .0000
--money      8 byte   .0000
--real			0.0000000
--float				0.0000000000000......
--dec dec(digits,floats) dec(5,2) 122.12    12.898 xx
```
ال smallmoney و money بيخزنو 4 علامات عشريه لاكن الفرق فحجم الرقم الصحيح 4 بايت و 8 بايت
ال real فيه 7 علامات عشريه
الfloat اكترهم علامات عشريه

اكثرهم استخداما هو DEC يعتبر داتاتايب وفنفس الوقت فاليديشن عالداتاتايب
لانه بيتحددله طول الرقم ومسموح فيه كام رقم بعد العلامه 
يعني dec(5,2) معناها الرقم طوله 5 منهم 2 بعد العلامه , لو حطيت اكتر هيرفض
الdecimal حجمه dynamic علي حسب طول الرقم الي محدده

##### char 

```
--char(max number 10msln) ficxed length chars reserved
--varchar(max number 10msln) variable length charachter by7gz 3la 2d ma tktb
--nchar()
--nvarchar() n for scability lw 3ayz aktb ai lo3'a 3'er el english
--nvarchar(max)
```

- **CHAR(n)**

is a fixed-length character data type, meaning it stores a specific number of characters for each value, padding the unused space with blank characters.
بيشيل رقم ثابت من الحروف 
وبيحجزهم كلهم
يعني لو قولتله char(10) هيحجزهم كلهم حتي لو مستخدمتش غير 2

- **VARCHAR(n)**

is a variable-length character data type, allowing storage of variable-sized strings without the trailing padding of spaces.
حجمه متغير معايا , مثلا قولتله varchar(10) واستخدمت منهم 2 هيحجز الاتنين بس

- **NCHAR(n) and NVARCHAR(n)**

are similar to char and varchar, but they are designed to store Unicode characters. it can handle and support multilingual data, allowing the storage and retrieval of text in various languages and scripts without encountering encoding issues or character representation problems.
زي الي فاتو لاكن بيستخدمو لتخزين ال unicode characters 
مثلا لو عايز اخزن اي لغة تاني غير الانجليزي هستخدم الاتنين دول 
لان مثلا لو استخدمت عربي صيني ياباني او اي لغة غير الانلجيزي في الchar , varchar هيخزنهم بحروف غير مفهومه ؟؟؟؟

* **NVARCHAR(max)** 
لو هكتب بس مش عارف طول الحاجه الي هكتبها 
هتديلي لحد 2 جيجا



##### datetime 

عندي كذا داتاتايب للوقت والتاريخ

```
--Date        mm/dd/yyyy
--time        hh:mm:ss
--time(7)     hh:mm 12.7875464
--smalldatetime modern dates mm/dd/yyy hh:mm
--datetime      more dates range
--datetime(7)
--datetimeoffset 24/11/2021 10:30 +2:00 time zone
```

ال Date بيشيل تاريخ طبيعي بترتيب , شهر يوم سنه
0001-01-01 >> 9999-12-31

الtime بيتكتب ساعه دقيقه ثانيه , والثواني هنا ممكن تتقسم علي 1000 يعني nanosecond

الtime(7) زي الtime لاكن بقسم الثواني علي 10 مليون وبستخدمها في الاماكن الي محتاج فيها دقه عاليه زي الفضاء مثلا محتاج تفاصيل الثواني
عندي ارقام مختلفه غير ال7 لاكن ال7 max
اقدر استخدم ارقام مختلفه من 4 5 6 
ال default بتاعت الtime هي 3 (يعني نانو ثانيه)

الsmalldatetime بتشيل فيها التاريخ وساعات ودقايق 
ومش بتشيل ثواني
وبيكون فيها تواريخ حديثه بس
1900-01-01 >> 2079-06-06


الdatetime بيكون فيها تواريخ اكبر من smalldatetime ومعاها ثواني ديفولت 3 من الف للثانيه 
1753-01-01 >> 9999-12-31


الdatetime2(7) شبه الdatetime لاكن ب accuracy اعلي للثواني


ال datetimeoffset بيكون زي الdatetime لاكن بيكون معاها timestamp 

##### binary 

جواها binary data type لو عايز اخزن ارقام باينري 0011001101 
وجواها image datatype بيشيل الصور ك binaries

الصور نقدر نخزن الpath بتاعها او نخزنها هي ك باينري
بس حسب ال case 
لو خزناها ك باينري هتكون معانا جوه الداتابيز لو عملنا backup او نقلناها
لاكن لو خزنا الpath مش هتكون معانا جوه الداتابيز وممكن مكانها يتغير 


##### other datatypes 

- XML
- unique_identifier 
- sql_variant 


