C# provides a **ref** keyword to pass argument as  
reference-type. It passes reference of arguments to the function rather  
than copy of original value. The changes in passed values are permanent  
and  
**modify** the original variable value.

اي فاريبل من النوع value variable

وباصيته في ميثود بيتباصي نسخه من الفاريبل في مكان تاني

مش بيتباصي نفس المكان في الميموري

---

### Ref Keyword

لما اكون عايز اباصي مكان الفاريبل بدلا من نسخه من القيمه

هستخدم ref keyword

public void Show(ref int val)

بحط الكيوورد في هيدر الفانكشن

program.Show(ref val);

وبحطها كارجومينت لما بنادي الفانكشن

```C#
class Program
{
public void doSommething(ref int val)
{
val += 3;
}
static void Main(string[] args)
{
Program d1 = new Program();
var val = 55;
d1.doSommething(ref val);
Console.WriteLine(val);
}
}
```

الكيوورد ريف لما استخدمها

لازم الفاريبل الي هبعته يكون واخد قيمه ابتدائيه علشان اقدر ابعته كارجومينت

---

### Out Keyword

لو عايز ابعت فاريبل وانا مش مديله قيمه ابتدائيه

هستخدم الكيورد اوت

بس بعد ما استقبلها في الميثود لازم اديلها قيمه قبل ما اعدل عليها

لنفترض مثلا بعت فاريبل ملوش قيمه

وروحت الميثود قولت عايز اجمع علي الفاريبل القديم 3

زي المثال الي فوق

ف هو ملوش قيمه قبل كده ازاي هجمع 3 علي مفيش؟

ف بعد ما استقبله لازم اديله قيمه جوه الميثود قبل ما اعمل عليه اي عمليه

```C#
class Program
    {
        public void doSommething(out int val)
        {
            val = 2;//لازم اديله قيمه بعد ما اخده في الفانكشن
            val += 3;
        }
        static void Main(string[] args)
        {
            Program d1 = new Program();
            int val;
            d1.doSommething(out val);
            Console.WriteLine(val);
        }
    }
```