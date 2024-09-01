لما بعمل overloading للكونستراكتور واعمل منه اكتر من نسخه 
بيكون فيه تكرار للكود 
مثلا فيه كونستراكتور بيدي قيمه لفاريبل واحد 
وكونستراكتور تاني بيدي قيمتين لاتنين فاريبل من ضمنهم الفاريبل الي كتبناه في اول كونستراكتور
طب ليه مستخدمش الكود الي كتبته قبل كده بدلا من تكراره في كونستراكتور تاني؟
هنا هييجي دور الconstructor chaining

بستخدم this() علشان تشير علي الكونستراكتور بتاع الكلاس ولو فيه اكتر من واحد هيتحدد عن طريق البرامترز الي هباصيها

 او اقدر انادي عليه باسمه واباصيله برامترز 

```csharp
public mySampleClass(): this(10)
{
   // This is the no parameter constructor method.// First Constructor
}
```
is equivalent to
```csharp
public mySampleClass()
{
    mySampleClass(10)
     // This is the no parameter constructor method.// First Constructor
}
```


### **Why Use Constructor Chaining?**

- **Code Reusability:** You avoid duplicating code because all constructors funnel through a single point of initialization (the most specific constructor).
- **Maintainability:** If you need to change the initialization logic (e.g., add validation), you only need to do it in one place.
- **Consistency:** It ensures that no matter which constructor is used, the object's properties are initialized in a consistent way.