  

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

لازم علشان يرجعلي القيمه اعملها كاستينج للتايب بتاعها

لو سيبتها هيبدا من الديفولت زيرو

لو حطيت رقم لاول هيبدا يعد من عنده

لو حطيت قيمه لفاريبل في النص

هيكون الي قبله يعد من زيرو

والي بعده يعد من قيمه الفاريبل ده

---

كان عندنا طريقه نرجع بيها قيمه من الاينم وهيا الكاستينج

ولو عايز ارجع القيمه كاسترينج هستخدم ميثود توسترينج او باسم الاينم عادي Month.JUN

---

ازاي اتشيك علي قيمه جوه الاينم واشوف موجوده ولا لا

يعني يوزر هيديلي قيمه واشوف هيا جوه الاينم ولا لا

ولو موجوده هنرجع قيمتها

Enum.Parse(typeof(Month), m)

ميثود البارث : هتتشيك علي القيمه ام الي انا باصيتها ولو لقيتها جوه الاينم هترجع الاوبجكت بتاعها (لو عايزه رقم اعمله كاستينج)

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
هيتشيك اذا كان الفاريبل الي حاطه بارميتر وان لو موجود هيرجع الاوتبوت ويحطه في 
mon
```

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
            {
                Console.WriteLine((int)Enum.Parse(typeof(Month),m));
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

---

Console.WriteLine((Month)3); هات العنصر الي قيمته 3 جوه الاينم

---