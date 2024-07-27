لو فيه ميثود انا بستدعيها جوه ميثود تاني ومش محتاجها غير جوه الميثود دي ف ممكن احطها جوه بادي الميثود الي استخدمتها

بغرض التنظيم

لاكن هتكون مقتصره علي الميثود الي شايلاها فقط مقدرش استدعيها من بره

```C#
public void checks(int number)
        {
            //some of code using isEven() method
             bool isEven(int val) => val % 2 == 0;
        }
```

بدلا من

```C#
public void checks(int number)
        {
            //some of code using isEven() method
            isEven(6);
        }
        public bool isEven(int val) => val % 2 == 0;
```