بما ان فانكشن readline بترجع سترينج 
يعني اي انبوت هاخده من اليورز هيكون سترينج 
هحتاج اعمله parsing لداتا تايب تاني علشان اعرف اشتغل عليه 

كل كلاس من كلاسات الداتا تايب الي موجوده في system namespace 
موجود جواها فانكشن parse بتاخد سترينج وترجع الداتا تايب ده

```csharp
string st = "51";  
  
byte byteNum = byte.Parse(st);  
sbyte sbyteNum = sbyte.Parse(st);  
short shortNum = short.Parse(st);  
ushort ushortNum = ushort.Parse(st);  
int intNum = int.Parse(st);  
uint uintNum = uint.Parse(st);  
long longNum = long.Parse(st);  
ulong ulongNum = ulong.Parse(st);  
double doubleNum = double.Parse(st);  
float floatNum = float.Parse(st);  
  
Console.WriteLine(byteNum);  
Console.WriteLine(sbyteNum);  
Console.WriteLine(shortNum);  
Console.WriteLine(ushortNum);  
Console.WriteLine(intNum);  
Console.WriteLine(uintNum);  
Console.WriteLine(longNum);  
Console.WriteLine(ulongNum);  
Console.WriteLine(doubleNum);  
Console.WriteLine(floatNum);

```

----
او بنستخدم الكلاس Convert موجود في System Namespace
بستخدم فانكشن ToInt16 تديلي short
و ToInt32 تديلي int
و ToInt64 تديلي long
وفيه منهم نسخ u للunsigned زي ToUInt64 ,  ToUInt32 ,  ToUInt16
او ToChar , ToString
و ToDouble و ToSingle بتحول لfloat

كلهم بناديهم من Convert. 


-----
بنستخدم ميثود parse

ونباصيلها الاسترينج وتحوله

وكذلك كلاس converter

```C#
int res = Convert.ToInt32(str);
Console.WriteLine(res);
وجواه ميثودز كتير نقدر نستخدمها
int num = 452;
Console.WriteLine(Convert.ToString(num,2));
مثال تاني احول الرقم لاساس ثنائي
```

لاكن يفضل parse

```C#
String str = "123";
Console.WriteLine(int.Parse(str));//123
Console.WriteLine(double.Parse(str));//123
Console.WriteLine(long.Parse(str));//123
Console.WriteLine(short.Parse(str));//123
Console.WriteLine(ushort.Parse(str));//123
Console.WriteLine(uint.Parse(str));//123
```

---

what if string contains any non-numeric value? will throws format-exception

case 2 , what if string value too big in case int or long can’t fit? will throws overflow exception

الحل للاتنين دول اننا نستخدم

tryParse(string,out int number);

في الاول الميثود بتتشيك اذا كان تقدر تحولهم ولا لا

ولو ايوه تقدر تحوله هتحط الاوتبوت جوه الفاريبل الي هباصيه

```C#
String str = "123p";
if (int.TryParse(str,out int number)){
	Console.WriteLine(number);
}
else{
	Console.WriteLine("Invalid String");
}
```

لو الاسترينج ينفع يتحول هيحوله ويحطه ففاريبل number ويطبعه

لو مينفعش هينفذ تاني بلوك