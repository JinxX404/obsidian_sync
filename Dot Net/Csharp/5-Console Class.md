Represents the standard input, output, and error streams for console applications. This class cannot be inherited.
الكلاس الي مسئول عن التعامل مع الconsole window
من خصائصها انه لما بتخلص الاكواد الي المفروض تنفذها , بتقفل 
لو عايزها تفضل مفتوحه مثلا هخليها تستني تاخد انبوت من اليوزر 


الكلاس جوه  [system namespace](obsidian://open?vault=Obsidian%20Vault&file=Dot%20Net%2FCsharp%2F4-System%20Namespace)

الكلاس مينفعش اورث منه 

A console is an operating system window through which a user can communicate with the operating system or we can say a console is an application in which we can give text as an input from the keyboard and get the text as an output from the computer end. The command prompt is an example of a console in the windows and which accept MS-DOS commands. ==**The console contains two attributes named as screen buffer and a console window.**==  
In C#, the Console class is used to represent the standard input, output, and error streams for the console applications. You are not allowed to inherit Console class. This class is defined under _System_ namespace. This class does not contain any constructor. Instead of the constructor, this class provides different types of properties and methods to perform operations.
https://www.geeksforgeeks.org/console-class-in-c-sharp/
https://learn.microsoft.com/en-us/dotnet/api/system.console?view=net-8.0
---


جواها بروبرتس اقدر استخدمها زي BackgroudColor و ForegroundColor
الاولي بتغير الباكجراوند والتانيه لون الكلام 
لما بغيرها بتتغير لكل الي هييجي بعدها 
لو هحتاجها فحاجه معينه فقط لازم اعملها ريسيت بعدها 

بخزن قيم جواهم من الEnum بتاع الالوان , مقدرش اسندله قيمه من عندي 

```C#
Console.BackgroundColor = ConsoleColor.Black;
Console.ForegroundColor = ConsoleColor.Blue;
Console.Write("HELLO");
```
بروح للبروبرتي backgroundcolor , foregroundcolor وبحطلهم قيم الالوان من الي جوه الenum 

---
عندي Title اقدر اغير بيه التايتل الي بتظهر بيه الكونسول ويندو 

----

فيه ميثودز زي [Clear()](https://www.geeksforgeeks.org/console-clear-method-in-c-sharp/)
بتمسح الكلام الي موجود عالكونسول قبل ما استدعيها 

---
فيه ميثود [ResetColor()](https://www.geeksforgeeks.org/console-resetcolor-method-in-c-sharp/) بترجع ال foreground , background للديفولت بتوعهم 
**Method** is used to the foreground and background console colors to their defaults i.e. background to black and foreground to white.


----

من اهم الفانكشنز الي جواها هما 


##### 1-[ReadKey()](https://www.geeksforgeeks.org/console-readkey-method-in-c-sharp/)
makes the program wait for a key press and it prevents the screen until a key is pressed. In short, it obtains the next character or any key pressed by the user. The pressed key is displayed in the console window(if any input process will happen).
من وظايفه انه بيستني انبوت من اليوزر علشان يقفل الكونسول 
ممكن استخدمه فاكتر من حاجه 
مثلا لو عايز اقفل الويندو لما اليوزر يكتب حرف معين 
ممكن احطها في while loop واخليه شغال طلاما الحرف الي هيحطه اليوزر مش بيساوي الحرف الي عايزينه 
بنستخدم معاه enum اسمه ConsoleKey بيكون فيه كل الحروف الي موجوده عالكيبورد 
```C#
	while(Console.ReadKey().Key != ConsoleKey.E) {}
```
هنا بنقوله خلي الكونسول شغاله وخد انبوت من اليوزر , ولو الانبوت ده مش بيساوي E خليك شغال 
لو هيساوي E الكونسول هيقفل

عندنا overloaded method تانيه بتاخد boolean as argument
**Syntax:** public static ConsoleKeyInfo ReadKey (bool key);  
Here, **“key”** is used to determines whether to display the pressed key in the console window. If “true” then the pressed key will not be shown in the output window. If “false” then the pressed key will be shown in the output window.

لو ترو مش هيعرض الحرف الي اخترته عالشاشه (هيعمل الوظيفه زي الميثود العاديه لاكن مش هيعرض الحرف)
لو فولس هيعرض الحرف عالشاشه


---
#### 2-[Read()](https://www.geeksforgeeks.org/console-read-method-in-c-sharp/)
is used to read the next character from the standard input stream. This method basically blocks its return when the user types some input characters. As soon as the user press ENTER key it terminates.

بتقرا كاركتر من الكونسول
لو كتبت اكتر من حاجه ما بينهم مسافات , هتقرا اول واحد فقط
It returns the next character from the input stream, or a negative one (-1) if there are currently no more characters to be read.


بتاخد الكاركتر من الكونسول كانتجر 
وانا هاخد الانتجر ده (الي هو الاسكي بتاع الحرف او الرقم الي اتكتب)
وهحوله زي ما انا عايز بالكاستينج 

الRead() بتقرا كاركتر واحد 
ولما متلاقيش حاجه تقراها (الكتابه خلصت) هترجع -1 

باستغلال النقطه دي اقدر اعمل لووب تقرا كذا كاركتر بالRead 
هقوله طلاما الي انت قريته != -1 يبقي خليك شغال واقراه 

- `Console.Read()` reads a single character from the input and returns its Unicode value as an `int`.
- `while ((input = Console.Read()) != -1)` is a loop that reads characters until `Console.Read()` returns `-1`, indicating no more characters to read.

لما بكتب فالكونسول
بتتخزن في buffer 
الread بتقرا من البافر دي
لو كتبت رقم 1 مثلا ودوست انتر
هتتهندل بانه هياخد الرقم يحطه فالبافر وينزل بعده سطر جديد (هيحطه فالبافر برضو) عندنا في ويندوز 11 بيتعامل معاها مختلف شويه ف ممكن قبل ما ينزل سطر جديد هيعمل Carriage Return قبل ال/n فهيحطها برضو فالبافر 

لما اعمل لووب علشان تاخد حرف واحد هضطر اتعامل مع الحرف واتنين كمان معاه متخزنين فالبافر 
```
اقدر اهندلهم بكوندشن if (x == 13 || x == 10) continue;
```
لو لقي الحرف الي واخده ب10 يعني new line او 13 يعني carriage return هيعمل continue 

```c#
while(true){

    int x = Console.Read();
    Console.WriteLine(x);

}
```

اللوب دي مع كل لفة هتطبع 3 حاجات 
الكاركتر الي حطيته كانبوت 
وبعده هتلف تاني للnew line وبعده للcarriage return
![[Pasted image 20240711161247.png]]
كتبت 2 اخدها كانتجر اسكي 
وبعده الcarriage وبعده الnew line






----

#### 3-[ReadLine()](https://www.geeksforgeeks.org/console-readline-method-in-c-sharp/)
This method is used to read the next line of characters from the standard input stream. It comes under the [Console class](https://www.geeksforgeeks.org/console-class-in-c-sharp/)(System Namespace). If the standard input device is the keyboard, the ReadLine method blocks until the user presses the Enter key. And if standard input is redirected to a file, then this method reads a line of text from a file.
****Syntax:**** public static string ReadLine ();  
****Return Value:**** It returns the next line of characters of string type from the input stream, or null if no more lines are available.

بتقرا سطر كامل كسترينج ونعمله بارسينج بعدين 
نقدر نستخدمها فاخر الكود علشان تسيب الكونسول مفتوحه مستنيه انبوت من اليوزر (لو دوسنا انتر هتقفل)


مش هتقابلني مشاكل البافر الي في Read()
###### How `Console.ReadLine()` Works

- **Reading a Line:** `Console.ReadLine()` reads all characters from the current position to the end of the line. This includes any characters you type before pressing Enter.
- **New Line Characters:** When you press Enter, `Console.ReadLine()` reads up to but does not include the newline characters (`\r\n` on Windows, `\n` on Unix-like systems). It effectively removes them from the input stream.

###### Behavior of `Console.ReadLine()`

1. **Input Handling:** When you type "Hello" and press Enter, the buffer contains:
    
    - `['H', 'e', 'l', 'l', 'o', '\r', '\n']` on Windows
    - `['H', 'e', 'l', 'l', 'o', '\n']` on Unix-like systems
2. **Reading the Input:**
    
    - `Console.ReadLine()` reads "Hello" and discards the `\r\n` (or `\n`).
    - It returns the string "Hello".





---

#### 4-Write()

بتطبع من غير سطر جديد بعدها

----

#### 5-WriteLine()
بتطبع سطر جديد بعد اي حاجه تطبعها



















### Input Buffer
##### What is an Input Buffer?

An input buffer is a temporary storage area in memory where data is held before it is processed. When you type characters on the keyboard, these characters are first stored in the input buffer. The program then reads characters from this buffer.

```C#
int x = Console.Read();
Console.WriteLine(x);

int y = Console.Read();
Console.WriteLine(y);

int z = Console.Read();
Console.WriteLine(z);
```
لو دخلت 1 الكود ده هيطبع 49 وبعدين 13 وبعدين 10 
لانه مع كل كوول للRead() هتروح للبافر تاخد الي جواه تحطه جوه الفاريبل وتطبعه
حتي مش هتطلب مني انبوت علي الكونسول

مع اول كوول وهحط 1 , البافر هيكون فيها 49,13,10 هتاخد ال49 تحطها فالx وتطبعها
المره الي بعدها هتعمل call للread هتاخد ال13 الي فالبافر وتحطها في y وتطبعها
المره الي بعدها هتاخد 10 وتحطها في z وتطبعها


علشان اخرج من المشكله دي هعمل كوول للread مرتين بعد كل فاريبل علشان يشيلو الرقمين الزياده
```C#
int x = Console.Read();
Console.WriteLine(x);
Console.Read();
Console.Read();

int y = Console.Read();
Console.WriteLine(y);
Console.Read();
Console.Read();

int z = Console.Read();
Console.WriteLine(z);
Console.Read();
Console.Read();
```



##### How Input Buffering Works

When you type characters and press Enter, here's what typically happens:

1. **Typing Characters:** As you type, each character is stored in the input buffer.
2. **Pressing Enter:** When you press Enter, a Carriage Return (`\r`, ASCII 13) and a Line Feed (`\n`, ASCII 10) are added to the buffer (on Windows).
3. **Reading from the Buffer:** When the program reads from the input buffer, it processes each character one by one.

##### What Happens When You Type Input

1. **Typing Characters:** When you type characters on the keyboard, each character is stored in the input buffer.
2. **Pressing Enter:** When you press Enter, a Carriage Return (`\r`, ASCII 13) and a Line Feed (`\n`, ASCII 10) are added to the buffer (on Windows).

##### Example: Typing "1" and Pressing Enter

When you type the character '1' and then press Enter, the buffer will contain:

- `['1', '\r', '\n']`


###### How `Console.Read()` Works

- **Reading Characters:** `Console.Read()` reads one character at a time from the input buffer and returns the Unicode value of that character as an `int`.
- **Buffer Management:** `Console.Read()` processes each character in the order they were entered and does not automatically handle or discard newline characters.

##### Detailed Behavior

1. **First Call to `Console.Read()`:**
    
    - Reads '1' (ASCII 49).
    - Removes '1' from the buffer.
    - Returns 49.
2. **Second Call to `Console.Read()`:**
    
    - Reads Carriage Return (`\r`, ASCII 13).
    - Removes `\r` from the buffer.
    - Returns 13.
3. **Third Call to `Console.Read()`:**
    
    - Reads Line Feed (`\n`, ASCII 10).
    - Removes `\n` from the buffer.
    - Returns 10.