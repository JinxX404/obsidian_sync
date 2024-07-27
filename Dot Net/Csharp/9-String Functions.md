
### Length

```c#
string st = "Moataz"
Console.Write(st.Length); // 6
```


### ToLower()

```C#
string st = "Moataz"
Console.Write(st.ToLower()); // moataz
```

### ToUpper()

```C#
string st = "Moataz"
Console.Write(st.ToUpper()); // MOATAZ
```

### Contains()
return true or false

|                                                                                                                                                                                      |                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| [Contains(Char)](https://learn.microsoft.com/en-us/dotnet/api/system.string.contains?view=net-8.0#system-string-contains(system-char))                                               | Returns a value indicating whether a specified character occurs within this string.                                       |
| [Contains(Char, StringComparison)](https://learn.microsoft.com/en-us/dotnet/api/system.string.contains?view=net-8.0#system-string-contains(system-char-system-stringcomparison))     | Returns a value indicating whether a specified character occurs within this string, using the specified comparison rules. |
| [Contains(String)](https://learn.microsoft.com/en-us/dotnet/api/system.string.contains?view=net-8.0#system-string-contains(system-string))                                           | Returns a value indicating whether a specified substring occurs within this string.                                       |
| [Contains(String, StringComparison)](https://learn.microsoft.com/en-us/dotnet/api/system.string.contains?view=net-8.0#system-string-contains(system-string-system-stringcomparison)) | Returns a value indicating whether a specified string occurs within this string, using the specified comparison rules.    |


عندي 4 overloaded methods لcontains

الاول ينفع اباصيلها كاركتر تشوفه جوه الاسترينج ولا لا 
التانيه اقدر اباصيلها الكاركتر ومعاه بارمتر بتحدد هيقارن علي اي اساس
يعني ممكن اقوله يقارن ويعمل ignorecase يعني سواء الحرف ده موجود كابتل او سمول يرجعه 
لاكن ديفولت كان لازم يشوف الحرف بالظبط

التالت بتاخد سترينج تدور عليه جوه 
والرابع بتاخد نفس الاسترينج بس بتاخد بارمتر تحدد هيقارن علي اي اساس


تاني برامتر هو enumeration value

```C#
string st7 = "Moataz";  
Console.WriteLine(st7.Contains('M')); // True  
Console.WriteLine(st7.Contains('m')); // False  
Console.WriteLine(st7.Contains('m' , StringComparison.OrdinalIgnoreCase)); // True  
Console.WriteLine(st7.Contains("Moa")); // True  
Console.WriteLine(st7.Contains("moa")); // False  
Console.WriteLine(st7.Contains("moa" , StringComparison.OrdinalIgnoreCase)); // True  
Console.WriteLine(st7.Contains("MM")); // False
```
لما باصينا الenumeration value فتاني برامتر وقولناله يقارن وميعملش حساب الكابتل والاسمول 
يعني فتالت سطر لما اخد البارمتر (الاسترينج بيبدا بكابتل) وبنقارن باسمول وهيرجعلي ترو




### StartsWith()

بياخد كاركتر او سترينج وممكن اباصيله enumerate كبارمتر تاني واحدد طريقه المقارنه (ممكن اعمل ignore case)
مش بتاخد بارمتر للignore case مع الكاركتر (سترينج فقط)

```C#
string st8 = "Moataz";  
Console.WriteLine(st8.StartsWith('M')); // True  
Console.WriteLine(st8.StartsWith('m')); // False  
Console.WriteLine(st8.StartsWith("Moa")); // True  
Console.WriteLine(st8.StartsWith("moa")); // False  
Console.WriteLine(st8.StartsWith("moa" , StringComparison.OrdinalIgnoreCase)); // True  
Console.WriteLine(st8.StartsWith("MM")); // False
```


### EndsWith()
نفس الStartwith بنفس الكونستراكتورز الي جواه 
بس بتشوف هل الي انا بصيته موجود فاخر الاسترينج بتاعي ولا لا

```C#
string st9 = "Moataz";  
Console.WriteLine(st9.EndsWith('z')); // True  
Console.WriteLine(st9.EndsWith('A')); // False  
Console.WriteLine(st9.EndsWith("taz")); // True  
Console.WriteLine(st9.EndsWith("moa")); // False  
Console.WriteLine(st9.EndsWith("TAZ" , StringComparison.OrdinalIgnoreCase)); // True  
Console.WriteLine(st9.EndsWith("zz")); // False
```


### IndexOf()

Reports the zero-based index of the first occurrence of a specified Unicode character or string within this instance. The method returns -1 if the character or string is not found in this instance.

بترجعلي اندكس اول ظهور للكاركتر او الاسترينج الي باصيته
ممكن ياخد سترينج او كاركتر 
وممكن ياخد eneumerate type يقوله يقارن علي اساس ايه (مثلا سمول او كابتل ....)

ممكن بعد ما اباصي الكاركتر اباصيله بارمتر اقوله ابدا من عند الاندكس ده

```C#
string st10 = "Moataz";  
Console.WriteLine(st10.IndexOf('z')); // 5  
Console.WriteLine(st10.IndexOf('A')); // -1  
Console.WriteLine(st10.IndexOf('A' , StringComparison.OrdinalIgnoreCase)); // 2  
Console.WriteLine(st10.IndexOf("taz")); // 3  
Console.WriteLine(st10.IndexOf("moa")); // -1  
Console.WriteLine(st10.IndexOf("TAZ" , StringComparison.OrdinalIgnoreCase)); // 3  
Console.WriteLine(st10.IndexOf("zz")); // -1
```

ممكن نستخدم الاتنين بارمترز startIndex و Length
الاول بيقوله ابدا دور من عند كذا والتاني بيقوله امشي لحد كذا بعد الاندكس الي حددته 
```C#
string st10 = "MoatazM";  
Console.WriteLine(st10.IndexOf('M',3)); // 6  
Console.WriteLine(st10.IndexOf('M',3,2)); // -1
```
الاول هيبدا يدور من عند اندكس3 (يعني مش هيشوف ان الحرف موجود فالاول)
التاني هيبدا من 3 ويقف عند 5 يعني مش هيلحق يشوف اندكس 6 فهيرجع -1



### LastIndexOf()
Reports the zero-based index position of the last occurrence of a specified Unicode character or string within this instance. The method returns -1 if the character or string is not found in this instance.

نفس ميثود indexOf لاكن بيجيب اندكس اخر ظهور للكاركتر او الاسترينج

```C#
string st11 = "MoatazM";  
Console.WriteLine(st11.LastIndexOf('M')); // 6  
Console.WriteLine(st11.LastIndexOf('A')); // -1
```


### Replace()
ممكن ابدل حرف بحرف او سترينج باسترينج 
وممكن اباصيله enumerate واحددله يقارن علي اي اساس
اول بارمتر هيكون الحاجه القديمه الي عايزه تتغير
وتاني بارمتر الحاجه الجديده
وبترجعلي سترينج جديد


### Split()
 عكس جوين

باخد سترينج وافصله لااري اوف سترينج

بديله سيباراتور معين وهو كل ما يلاقيه بيقطع العنصر ويحطه فالاراي

### Join()

جوين بتاخد اراي وبتلزق عناصرها فبعض

In C#, _**Join()**_ is a [**string**](https://www.geeksforgeeks.org/c-string/) method. This method is used to concatenates the members of a collection  
or the elements of the specified array, using the specified separator between each member or element. This method can be overloaded by passing different parameters to it.  

`public static string Join(string separator, params obj[] array)`

الميثود الاولي

بتاخد سترينج في الاول وهو السيبارتور بتاعي

العلامه الي هحطها تفصل بين العناصر لما الزقهم

تاني بارميتر هو الاراي الي عايز الزق عناصرها

---

`public static string Join(string separator, params string[ ] array)`

الميثود التانيه

this method is used to concatenate the elements of a String array with the help of a user-specified separator between each element of the string array.

```C#
object[] array = { "Hello", "Geeks", 12345, 786 };
string s1 = string.Join(",", array); //Hello,Geeks,12345,786
Console.WriteLine(s1);
```

---
الميثود التالته

`public static string Join(string separator, params string[] array, int pos1, int pos2)`

This method is used to concatenate the elements of a String array between the specified positions with the help of a user-defined separator between each element of the array.

```C#
string[] array = { "Hello", "Geeks", "thank","you","all" };
string s1 = string.Join(",", array,1,2);  
Console.WriteLine(s1); //Geeks,thank
```

بقوله هات من اندكس كذا لكذا

البوزيشن الاول والتاني معانا (inclusive)

يعني من 1ل3

يعني معايا 1و2و3

 [https://www.geeksforgeeks.org/c-sharp-join-method-set-1/](https://www.geeksforgeeks.org/c-sharp-join-method-set-1/)




### PadLeft() & PadRight()

ميثود جوه الاسترينج

بنعمل بيها بادينج لاسترينج معين

مثلا حاطط 5 جوه سترينج

وعايز اخليه يتكون من 4 خانات ويكون شمال الرقم اصفار

هستخدم PadLeft

```C#
int x = 5;
Console.WriteLine(x.ToString().PadLeft(4,'0'));//0005
```
البارميتر الاول معناه عايز الاسترينج يكون 4 خانات
وباقي الخانات حطها زيرو
هو هيكون كده "5" وبعدين هيشوف محتاج كام علشان اوصل لعدد الخانات الي انا 
طالبها وهيحط الكاركتر الي طالبه منه فباقي الخانات


عندي واحده تاني بتاخد ارجومينت واحد

بتاخد عدد ومش هقولها تحط ايه في الخانات الباقيه فهتحط مسافه

```C#
string s1 = "GeeksForGeeks";
   
        Console.WriteLine("String : " + s1);
   
        // totalwidth is less than string length
        Console.WriteLine("Pad  2 :'{0}'", s1.PadLeft(2));
   
        // totalwidth is equal to string length
        Console.WriteLine("Pad 13 :'{0}'", s1.PadLeft(13));
   
        // totalwidth is greater then string length
        Console.WriteLine("Pad 20 :'{0}'", s1.PadLeft(20));

//output
String : GeeksForGeeks
Pad  2 :'GeeksForGeeks' الي طلبته منه اقل من الطول الحقيقي مش هعمل حاجه
Pad 13 :'GeeksForGeeks'
Pad 20 :'       GeeksForGeeks' هنا اكبر من الطول الحقيقي هسيب مسافه علي شماله لحد ما اوصل 20 
```

[https://www.geeksforgeeks.org/c-sharp-padleft-method/](https://www.geeksforgeeks.org/c-sharp-padleft-method/)  

وكذلك الامر مع PadRight

بتحط الخانات الي طلبتها علي اليمين

 [https://www.geeksforgeeks.org/c-sharp-padright-method/](https://www.geeksforgeeks.org/c-sharp-padright-method/)