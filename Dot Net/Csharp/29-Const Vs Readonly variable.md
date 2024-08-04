الconst بتتعمل علي الprimitive data types او String
بتحتاج القيمه بتاعتها وقت ال declaration علي نفس السطر
لما بتتعمل مينفعش اغير قيمتها مره تاني
والconst هي compile time constant 
يعني وقت الcomplie لما بعمل Build مثلا
الكومبايلر بيشوف مين الي استخدم الconst ده ويروح يعمله replace مكانه
يعني لو string str = constValue و constValue = "Moataz"
هيروح يشيل constValue ويعمل str = "Moataz"

```C#
public const string name = "Moataz"
```
---
الreadonly
ممكن محطش قيمه جواه وقت الdeclaration اقدر اسيبه فاضي 
لاكن المكان الوحيد الي اقدر اضيف فيه قيمه هو الكونستراكتور
(فيه طرق تاني لاكن بشكل غير مباشر)

الreadonly يعتبر run time constant
يعني مبنعرفش القيمه الي جواه غير وقت الrun
```C#
readonly string name = "Moataz"
```

او ممكن نحطله قيمه في الكونستراكتور
ونقدر نغيرها اكتر من مره 

---
```C#
public const int myConstInt = Add(3, 4);  //Invalid 
public readonly int myReadonlyInt = Add(3, 4); // Valid
```
في الconst منقدرش نسند قيمه جايه من method call 
لاكن في الreadonly نقدر
`const` variables must be initialized with a literal or a constant expression. However, `readonly` variables can be assigned using either a literal or method call, just as long as the assignment occurs during declaration or in a constructor.

const variables must always be implicitly static and can only be declared with basic types, while readonly variables can be both instance and static, as well as reference types.

For example, you can’t declare a private const variable, while you can have private readonly variables:

```C#
private const int myPrivateConst = 42; // Invalid
private readonly int myPrivateReadonly = 42; // Valid
```

### Memory Allocation

During memory allocation, const variables are stored in metadata, while readonly values are stored in the memory heap. The use of readonly variables also allows for lazy allocation, which can lead to improved performance in C# applications.


When deciding between const and readonly values, performance is a critical consideration. Since const values are set at compile time, accessing them is marginally faster. On the other hand, readonly variables are set at runtime and thus have slightly slower access times.

الكونست compile time ف هو اسرع من الreadonly



#
https://www.bytehide.com/blog/const-vs-readonly-in-c-explanation-in-3-minutes#:~:text=Const%20is%20a%20compile%2Dtime,stored%20in%20the%20memory%20heap.

