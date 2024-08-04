كل البرامترز بتتباصي فالميثودز بالvalue 
يعني بنبعت منها نسخه (مش الريفرنس)
ف لو الميثود عدلت في البرامتر ده 
التعديل مش هينعكس علي الفاريبل الي معايا 
لانه فالاصل بقا موجود منه نسختين
النسخه الي معايا والنسخه الي باصيتها فالميثود واتعدل فيها 
علشان كده التعديل مش هيسمع فالاصليه 

نحل ازاي المشكله دي؟
ب اننا نباصي الريفرنس مش الvalue
يعني هنباصي عنوان الفاريبل ده فالميموري
ف التعديل هيتم علي نفس المكان وهتسمع علي الفاريبل الي معايا

عندي اتنين keywords بيباصو البرامتر بreference هما ref , out
Ref and out keywords in C# are used to pass arguments within a method or function. Both indicate that an argument/parameter is passed by reference. By default, parameters are passed to a method by value. By using these keywords (ref and out) we can pass a parameter by reference.

مع بعض الاختلافات بينهم

## Ref Keyword

The ref keyword passes arguments by reference. It means any changes made to this argument in the method will be reflected in that variable when the control returns to the calling method.
#### Example code

```csharp
public static void GetNextNum(ref int id)  
{  
    id += 1;  
}  
  
private static void Main(string[] args)  
{  
    var i = 1;  
    Console.WriteLine("Current value of integer i:" + i);  
    GetNextNum(ref i);  
    Console.WriteLine("Next value of integer i:" + i);  
}
```
معايا رقم 1 هطبعه 
وبعدين هباصيه للميثود تعدل فقيمته وترجعه 
بنحط ref قبل البرامتر وقبل الارجومنت


## Out Keyword

The out keyword passes arguments by reference. This is very similar to the ref keyword.

#### Example Code

```csharp
public static void GetNextNum(out int id)  
{  
    id += 1;  
}  
  
private static void Main(string[] args)  
{  
    var i = 1;  
    Console.WriteLine("Current value of integer i:" + i);  
    GetNextNum(out i);  
    Console.WriteLine("Next value of integer i:" + i);  
}
```


عندنا بعض الفروقات بين الاتنين 
مع ref لازم اكون عامل intialization للفاريبل قبل ما اباصيه للميثود
لاكن الout مش لازم 

تاني حاجه
مع ref مش لازم اغير فقيمه البرامتر الي باصيته جوه الميثود (مش اجباري) ممكن ارجعه هو هو 
لاكن مع out لازم القيمه تتغير قبل الmethod call يخلص

مع out لازم اعمل intialize للفاريبل جوه الميثود قبل ما الcall يخلص
لاكن ref مش لازم

|   |   |
|---|---|
|Ref|Out|
|The parameter or argument must be initialized first before it is passed to ref.|It is not compulsory to initialize a parameter or argument before it is passed to an out.|
|It is not required to assign or initialize the value of a parameter (which is passed by ref) before returning to the calling method.|A called method is required to assign or initialize a value of a parameter (which is passed to an out) before returning to the calling method.|
|Passing a parameter value by Ref is useful when the called method is also needed to modify the passed parameter.|Declaring a parameter to an out method is useful when multiple values need to be returned from a function or method.|
|It is not compulsory to initialize a parameter value before using it in a calling method.|A parameter value must be initialized within the calling method before its use.|
|When we use REF, data can be passed bi-directionally.|When we use OUT data is passed only in a unidirectional way (from the called method to the caller method).|
|Both ref and out are treated differently at run time and they are treated the same at compile time.|
|Properties are not variables, therefore they cannot be passed as an out or ref parameter.|

مقدرش اباصي property كريفرنس 

ومقدرش اعمل  overloading للميثود (يعني استخدم نفس الميثود لاكن واحده ref  وواحده out)

ممكن اعمل overloading لو ميثود بتاخد ref/out والتانيه مش بتاخد حاجه منهم


بستخدم out لما اكون هرجع اكتر من قيمه فالميثود 
يعني هباصي كذا بالريفرنس اشتغل عليهم وارجع الاقيهم اتعدلو 
كده يعتبر رجعت اكتر من قيمه حتي من غير ما اعمل return

----

من تطبيقات الout/ref
في ميثودز جوه كل داتا تايب لل parse
من ضمنهم tryParse() 
بتاخد الحاجه تجرب تعملها  parse 
ولو عرفت تحولها هترجع ترو والقيمه في متغير معموله out 
لو معرفتش تحولها هترجع الديفولت 0 
```C#
bool isSuccesd = int.TryParse("Moataz", out int res);  
Console.WriteLine(res);
```
عملت فاريبل res وباصيته للميثود 
لو عرف يحولها هيرجعه جوه res 
لو معرفش هيرجع 0 

بدلا من parse() الي لو معرفتش تحولها هترمي اكسبشن
