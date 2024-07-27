
قواعد التسميه للفاريبلز زي الجافا 
مينفعش ابدا برقم لاكن ممكن ابدا بحروف او underscore
مينفعش اي special characters
مينفعش اي reserved keyword استخدمها كاسم فاريبل
لو عايز استخدمها (في حالات خاصه) بحط قبلها @ بيعرف ان الkeyword دي اسم فاريبل مش keyword  
```C#
string @string = "Moataz";
Console.WriteLine(@string);
```

لازم اسند قيمه للمتغير مينفعش اعمله declaration واسيبه




| Category       | Class name                                                             | Description                                                                                                                                                                     | C# data type |
| -------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| Integer        | [Byte](https://learn.microsoft.com/en-us/dotnet/api/system.byte)       | An 8-bit unsigned integer.                                                                                                                                                      | `byte`       |
|                | [SByte](https://learn.microsoft.com/en-us/dotnet/api/system.sbyte)     | An 8-bit signed integer.  <br>  <br>Not CLS-compliant.                                                                                                                          | `sbyte`      |
|                | [Int16](https://learn.microsoft.com/en-us/dotnet/api/system.int16)     | A 16-bit signed integer.                                                                                                                                                        | `short`      |
|                | [Int32](https://learn.microsoft.com/en-us/dotnet/api/system.int32)     | A 32-bit signed integer.                                                                                                                                                        | `int`        |
|                | [Int64](https://learn.microsoft.com/en-us/dotnet/api/system.int64)     | A 64-bit signed integer.                                                                                                                                                        | `long`       |
|                | [UInt16](https://learn.microsoft.com/en-us/dotnet/api/system.uint16)   | A 16-bit unsigned integer.  <br>  <br>Not CLS-compliant.                                                                                                                        | `ushort`     |
|                | [UInt32](https://learn.microsoft.com/en-us/dotnet/api/system.uint32)   | A 32-bit unsigned integer.  <br>  <br>Not CLS-compliant.                                                                                                                        | `uint`       |
|                | [UInt64](https://learn.microsoft.com/en-us/dotnet/api/system.uint64)   | A 64-bit unsigned integer.  <br>  <br>Not CLS-compliant.                                                                                                                        | `ulong`      |
| Floating point | [Half](https://learn.microsoft.com/en-us/dotnet/api/system.half)       | A half-precision (16-bit) floating-point number.                                                                                                                                |              |
|                | [Single](https://learn.microsoft.com/en-us/dotnet/api/system.single)   | A single-precision (32-bit) floating-point number.                                                                                                                              | `float`      |
|                | [Double](https://learn.microsoft.com/en-us/dotnet/api/system.double)   | A double-precision (64-bit) floating-point number.                                                                                                                              | `double`     |
| Logical        | [Boolean](https://learn.microsoft.com/en-us/dotnet/api/system.boolean) | A Boolean value (true or false).                                                                                                                                                | `bool`       |
| Other          | [Char](https://learn.microsoft.com/en-us/dotnet/api/system.char)       | A Unicode (16-bit) character.                                                                                                                                                   | `char`       |
|                | [Decimal](https://learn.microsoft.com/en-us/dotnet/api/system.decimal) | A decimal (128-bit) value.                                                                                                                                                      | `decimal`    |
|                | [IntPtr](https://learn.microsoft.com/en-us/dotnet/api/system.intptr)   | A signed integer whose size depends on the underlying platform (a 32-bit value on a 32-bit platform and a 64-bit value on a 64-bit platform).                                   | `nint`       |
|                | [UIntPtr](https://learn.microsoft.com/en-us/dotnet/api/system.uintptr) | An unsigned integer whose size depends on the underlying platform (a 32- bit value on a 32-bit platform and a 64-bit value on a 64-bit platform).  <br>  <br>Not CLS-compliant. | `nuint`      |
|                | [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object)   | The root of the object hierarchy.                                                                                                                                               | `object`     |
|                | [String](https://learn.microsoft.com/en-us/dotnet/api/system.string)   | An immutable, fixed-length string of Unicode characters.                                                                                                                        | `string`     |


```C#
byte range : 0 -> 255
short range : -32768 -> 32767
int range : -2147483648 -> 2147483647
long range : -9223372036854775808 -> 9223372036854775807
double range: -1.7976931348623157E+308 -> 1.7976931348623157E+308
float range: -3.4028235E+38 -> 3.4028235E+38
unsigned int range: 0 -> 4294967295
unsigned long range: 0 -> 18446744073709551615
unsigned short range: 0 -> 65535
decimal range: -79228162514264337593543950335 -> 79228162514264337593543950335

Console.WriteLine("byte range : "+byte.MinValue + " -> " + byte.MaxValue);

Console.WriteLine("short range : "+short.MinValue + " -> " + short.MaxValue);

Console.WriteLine("integer range : " + int.MinValue + " -> "+ int.MaxValue);

Console.WriteLine("long range : " + long.MinValue + " -> " + long.MaxValue);

Console.WriteLine("double range: " + double.MinValue +" -> "+ double.MaxValue);

Console.WriteLine("float range: " + float.MinValue+" -> "+float.MaxValue);

Console.WriteLine("unsigned int range: " + uint.MinValue + " -> " + uint.MaxValue);

Console.WriteLine("unsigned long range: " + ulong.MinValue + " -> " + ulong.MaxValue);

Console.WriteLine("unsigned short range: " + ushort.MinValue + " -> " + ushort.MaxValue);

Console.WriteLine("decimal range: " + decimal.MinValue + " -> " + decimal.MaxValue);
```




#### Boolean 
اقدر اعرفه bool او Boolean (وباقي الداتا تايبس اقدر اعملهم باسم الكلاس او Shorthand)

يعتبر اصغر داتا تايب فالميموري
اما True or False 

اقدر اطبق عليه العمليات ال logical زي and , or , not , xor

```C#
bool b1 = true , b2 = false;
Console.Write(b1 & b2);
Console.Write(b1 && b2);
```
الاتنين يعتبرو And لاكن فيه فرق بسيط ما بينهم 
ان التانيه && تعتبر short circuit يعني هو بيمشي من الشمال لليمين 
لو الشرط متحققش من الشمال هيوقف بدلا من انه يكمل للاخر
 عكس ال& هتكمل للاخر حتي لو الشرط بقي فولس 

عارفين ان الand اي فولس هتظهر هتخلي الناتج فولس
 يعني لو عندي 
 false && true && true && true 
 من اول واحده هيلاقي فولس هيحسب الاكسبريشن كله فولس
لاكن 
 false & true & true & true 
 اول واحده هتوضحله انه فولس والمفروض ميكملش
 لاكن هو هيكمل لاخر الاكسبريشن وبعدين يطلع الناتج 
 نفس الكلام مع الor في | و || 




