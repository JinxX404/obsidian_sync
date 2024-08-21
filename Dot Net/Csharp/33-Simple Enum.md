**Strongly typed named constants**

هو داتا تايب زي اي تايب كانه كلاس او ستراكت
لاكن هو value type
لو عندي مجموعه من الثوابت ليها علاقه بشي معين
مثلا شهور السنه دول ثابتين اقدر اعملهم في enum
او ايام الاسبوع
او الجيندر
كل الي جواه يعتبرو constants


-Each constant inside an `enum` is typically referred to as an "enumerator" or "enum member."

-Enum can only declared inside class or namespace

-The Value of enum members cannot  be changed out of enum declaration 
يعني مقدرش بره في الmain method اقوله Week.Sunday = 5 
طلاما عملت declare جوه الenum مقدرش اغيره بره

-the members of the enum are always public and no access modifiers can be applied

![[Pasted image 20240807215857.png]]

-two or more members of enum can have same value

---


access_modifier enum enum_name {

}
دايما بنسميه اسم مفرد 

القيم الي جواه لو مدتهاش قيمه هو هيبدا باي ديفولت يرقمهم من رقم الزيرو
لو حطيت قيمه ابتدائيه لاول فاريبل مثلا هو هيكمل الباقيين بدا من الرقم ده

----

التايب بتاع الاينم باي ديفولت هو انتجر
لو عايز اخزن فيه فاليو اكبر بحددها صراحة
enum ….. : long {

}

بيقدر ياخد داتا تايب دول فقط (ارقام)
مينفعش كسور
int , uint , short , ushort , long , ulong , byte , sbyte

---
```C#
public enum Color : byte  
{  
    red,  
    green,  
    yellow,  
    black,  
    grey  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {    
        var c1 = Color.black;   
		var c2 = Color.black.GetTypeCode();  
        var c3 = Color.black.ToString();   
		var c4= Color.black.Equals(c1);  
        var c5= Color.green.Equals(c1);   
		var c6 = Color.black.GetType();   
		var c7 = Color.black.CompareTo(c1);   
		var c8 = Color.black.GetHashCode();   
        Console.WriteLine(c1); // black  
        Console.WriteLine(c2); // byte , its data type  
        Console.WriteLine(c3); // returns the instance as string  
        Console.WriteLine(c4); // true , because black equals to black  
        Console.WriteLine(c5); // false , green != black  
        Console.WriteLine(c6); // returns variable type which is enum of color  
        Console.WriteLine(c7); // compare to returns 0 if equal , one if first > second , minus one if second > first  
        Console.WriteLine(c8); // returns hashcode for variable  
          
    }  
}
```

لما باخد منه اوبجكت بقوله اسم الenum وبعده اسم الاوبجكت 
وبعدين الenum.value القيمه دي بتكون جوا الenum فقط ومينفعش احط قيمه من عندي

الenum جواه ديفولت ميثودز زي compareTo , ToString, Equals

---
```C#
class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine((int)Month.FEB);
        }
    }
    enum Month
    {
        JAN, // 0
        FEB, // 1
        MAR, // 2 
        APR, // 3
        MAY, // 4
        JUN, // 5
        JUL, // 6
        AUG, // 7 
        SEP, // 8 
        OCT, // 9 
        NOV, // 10
        DEC  // 11
    }
```
لو عايز اجيب القيمه الي جوا الفاريبل ده 
بعمله كاست للتايب بتاعه

---
Methods like `Enum.Parse`, `Enum.TryParse`, and `Enum.GetValues` require you to specify the `Type` of the enum because the C# language is statically typed, and it relies on type information at compile-time. Enum names alone are not sufficient for these methods to work because they need to know the specific enum type they should operate on, and this information must be known at compile-time.

اللغه statically typed يعني محتاجه وقت الcompile تكون محدد التايب بتاعها

مع الenums اسم الenum مش كفايه انه يحدد التايب بتاعه (مجرد اسم)
بنحتاج فانكشن تجيبلي التايب بتاع الenum وهي typeof()


Here's why you need to specify the `Type` instead of just using the enum name:

1. **Compile-time type safety:** In C#, the type system is designed to catch type-related errors at compile time. If you were to pass just the enum name as a string, it would be a runtime value, and the compiler wouldn't be able to check it against the known enum types. By specifying the `Type` explicitly, you're providing the necessary type information at compile-time, and the compiler can ensure type safety.
2. **Dynamic behavior:** C# is statically typed, meaning that variable types are determined at compile-time. Enums are also a part of this type system. Specifying the `Type` parameter allows these enum-related methods to work dynamically with different enum types in a strongly-typed manner. It enables you to work with enums of various types in a single codebase.
3. **Compile-time constants:** Enums are often used for compile-time constants, and they provide a structured way to represent a set of related values. By requiring the `Type`, these methods ensure that you're working with constants that are known and defined at compile-time.

Here's an example of how you'd use these methods with the `Type`:

```C#
Type enumType = typeof(Month);

// Parse a string into an enum value of the specified type.
object parsedValue = Enum.Parse(enumType, "JAN");

// Get all values of the specified enum type.
Array enumValues = Enum.GetValues(enumType);
```

By providing the `Type` explicitly, you're making your code more readable, maintainable, and type-safe, and you're ensuring that the compiler can catch potential errors related to enum types at compile-time.

ميثود typeof هترجع نوع Type 
هبعتله اسم الenum وهيرجعلي نوعه 
![[Pasted image 20240806213808.png]]

فانكشن GetValues بترجع اراي من القيم الي جوه الenums

فانكشن Parse بترجع اوبجكت من الenum لو لقيته
يعني تاني برامتر ادتله سترينج 
هو هيشوف لو موجود جوه الenum هيرجعلي الاوبجكت بتاعه جوه الEnum
فيه برامتر تالت بتاع ignore case لو عايز اخليه case insensitive لما يسيرش جوه الenum
يعني JAN ممكن تكون جوه الenum لاكن small case
ديفولت الميثود دي case sensitive يعني البرامتر التالت فولس

لو عايزها case insensitive علشان يعمل ignore هنحطها ترو

بنستخدم الميثود بتاعت الparse لو هناخد انبوت من اليوزر وعايزين نشوف هل هو موجود جوه الenum ولا لا

---
ازاي اتشيك علي قيمه جوه الاينم واشوف موجوده ولا لا
يعني يوزر هيديلي قيمه واشوف هيا جوه الاينم ولا لا
ولو موجوده هنرجع قيمتها
Enum.Parse(typeof(Month), m)

ميثود البارث : هتتشيك علي القيمه m الي انا باصيتها ولو لقيتها جوه الاينم هترجع الاوبجكت بتاعها (لو عايزه رقم اعمله كاستينج)

![[/Untitled 6.png|Untitled 6.png]]

الميثود اول ارجومينت بتاخد النوع بتاع الاينم واستخدمت تايب اوف علشان ترجع النوع بتاعها

وتاني ارجومينت فيه الي عايز ادور عليه

**يعني هيا هترجع اوبجكت من الاينم لو لقيته**

  

الطريقه التانيه هستخدم tryParse

```C#
if (Enum.TryParse(m , out Month mon))
{
Console.WriteLine(mon);
}
```
هيتشيك اذا كان الفاريبل الي حاطه بارميتر وان لو موجود هيرجع الاوتبوت ويحطه في mon


> [!info] ChatGPT  
> Hello!  
> [https://chat.openai.com/share/8d7f35ce-1924-49cd-8ced-eaf638d43bc5](https://chat.openai.com/share/8d7f35ce-1924-49cd-8ced-eaf638d43bc5)  

prev link is explain prev example

---

ممكن نستخدم isDefined

ميثود بتتشيك اذا كان الفاريبل ده موجود جوه الاينم ولا لا وبترجع بوليان

```C#
string m = "JAN";

	if (Enum.IsDefined(typeof(Month) ,m))
		{    			               Console.WriteLine((int)Enum.Parse(typeof(Month),m));
    }
    else
    {
        Console.WriteLine("Invalid value");
    }
```

هتتشيك اذا كان القيمه موجوده جوه الاينم ولا لا

لو موجوده هنطبعها بالبارث ميثود الي بترجع اوبجكت من الاينم

والميثود دي ممكن تتشيك بالعكس يعني لو معايا القيمه وعايز اجيب قيمتها من الاينم

```C#
var m = 2;

if (Enum.IsDefined(typeof(Month) ,m))//شوفها موجوده ولا لا
    {
        Console.WriteLine((Month)m); //هات القيمه كرقم وحولها لاوبجكت من الشهور
    }
else
    {
        Console.WriteLine("Invalid value");
    }
```

Console.WriteLine((Month)3); هات العنصر الي قيمته 3 جوه الاينم

---

Traverse : 

```C#
foreach (var month in Enum.GetValues(typeof(Month)))
    {
        Console.WriteLine($"{month} = {(int)month}");
    }
لكل اوبجكت هرجع اسمه والقيمه بتاعته
```

هترافيرس علي الاينم

بقوله لكل month

داخل الاينم جيت فاليو

الEnum.GetValue

بترجع اراي اوف اوبجكتس من الاينم الي هباصيه

---

او بميثود getNames

بترجع اسماء عناصر الاينم

يعني هترجع اراي اوف سترينج

واقدر اخد كل واحد اعمله بارثينج واجيب القيمه بتاعته

```C#
oreach (var month in Enum.GetNames(typeof(Month)))
    {
       Console.WriteLine($"{month} =       {(int)Enum.Parse(typeof(Month),month)}");
    }
```