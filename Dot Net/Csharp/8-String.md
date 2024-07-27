عارفين الاسترينج من لغات تانيه مش محتاجين شرحه 


الكلاس بتاعه موجود في System namespace 
قولنا انه فيها كل الكلاسات المهمه والاساسيه الي هنستخدمها لانه الرووت namespace

الكلاس فيه اكتر من member نقدر نستخدمهم constructors , fields , properties 


الكونستراكتور الاول public String (char c, int count);
اقدر اباصيله char وتاني بارمتر احددله عدد التكرار (int32)

```C#
char ch = 'a';  
string st = new string(ch ,12);  
string st2 = new string(ch ,5);  
string st3 = new string(ch ,6);  
Console.WriteLine(st);//aaaaaaaaaaaa  
Console.WriteLine(st2);//aaaaa
Console.WriteLine(st3);//aaaaaa
```



تاني كونستراكتور public String (char[]? value);
 
ممكن اباصيله array of characters

```c#
char[] ch2 = new char[]{'a','b','c'};  
string st4 = new string(ch2);  
  
Console.WriteLine(st4);//abc
```



تالت كونستراكتور 
public String (char[] value, int startIndex, int length);

اقدر اباصيله  array of char وبعدين احددله الاندكس الي يبدا فيه واللينث الي يجيبه 
```C#
char[] ch3 = new char[]{'a','b','c','d','e','f','g'};  
string st5 = new string(ch3 , 1 , 4);  
  
Console.WriteLine(st5); // bcde
```
هبدا عند 1 الي هو b وهعد بعده تلاته تاني cde يبقي bcde


فيه اكتر من واحد تاني بياخد بوينتر علي اراي (هنشوفه بعدين)


----
عندنا 2 properites للاسترينج 
الاول هو Length وبيرجعلي طول الاسترينج 
التاني هو Chars[ ]
يعتبر انديكسر 
بيسمحلي اشاور علي كاركتر كاركتر جوه الاسترينج 
بيرجعلي اوبجكت

----



#### Special Characters
عندنا n\\ بتنزل سطر جديد 
و \\t بتعمل 4 مسافات 

لو عايزين نعمل الباك سلاش يتطبع كحرف عادي فالاسترينج ف انا محتاج اعمل سكيب للباك سلاش دي 
بكتب قبلها واحده تاني 
```csharp
Console.WriteLine("Hello\\World");
هتطبع hello\world
``` 
الباك سلاش الاولي بتقوله عامل الي بعدك كحرف عادي
ينفع احطها قبل الSpecial characters الي فوق علشان يتطبع كحروف عاديه

```csharp
Console.WriteLine("Hello\\tWorld"); 
هيطبع الاسبيشيال كاركتر كجزء من الاسترينج
```


عندي استخدام لل@ يقدر يحللي مشكله الاسكيب
اقدر استخدم ال@ علشان توضح ان التيكست ده عايزه يطبعه كله حتي لو فيه special characters 
```C#
Console.WriteLine(@"Hello\t\ntWorld");\\Hello\t\nWorld
```

او اقدر استخدمها في اني اكتب علي اكتر من سطر 
```c#
Console.WriteLine(@"Hello\
in new line: 
World");
```
هيطبعهم علي اكتر من سطر بدون ايرور






#### String Interpolation
اقدر اعمل كونكاتينيشن بال + او بالانتربوليشن

String interpolation in C# allows you to embed expressions inside string literals, making it easier to create formatted strings. It's a powerful feature for building dynamic strings.
ميزه بتسمحلي احط فاريبل جوه الاسترينج واطبعه بشكل افضل فورمات 
وليه اسم تاني هو string templates 

```C#
string s1 = "moataz";
string s2 = "mohammed";
string s3 = s1 +" "+ s2;
string s4 = $"{s1} {s2}";
Console.WriteLine(s3 +" "+s4);//moataz mohammed moataz mohammed
```
بنستخدم $ قبل الكوتيشن 
وبنحط الفاريبل ما بين الاسترينج بال { } 
