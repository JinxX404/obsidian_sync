علشان اطبق مفهوم DRY

في الكود

لما اعمل اوفرولدينج علي كونستراكتور هستخدم مصطلح constructor chaining

علشان مكررش الكود بتاعي

مثلا انا كان عندي كونستراكتور بيعمل حاجه معينه وهعمله اوفرلودينج

الكونستراكتور الجديد هينفذ الي كان بيعملها الكونستراكتور الاول ومعاه حاجه كمان مثلا

ف انا كده لما اعمل الكونستراكتور التاني هكرر كلام كنا كاتبينه قبل كده

الحل اني استخدم الكونستراكتور الاول بداخل التاني وينفذ الجزء المشترك ما بينهم بدلا من تكراره مره تاني

وده اسمه chaining

باستخدم this keyword

```C#
 				public Date() : this(5)
        {
            Console.WriteLine("something....");
        }
       public Date(int d)
        {
            day = d;
        }
```

الكونستراكتور الاول هينادي التاني يعمله حاجه معينه

  

> [!info] C# | Constructor Overloading - GeeksforGeeks  
> A Computer Science portal for geeks.  
> [https://www.geeksforgeeks.org/c-sharp-constructor-overloading/](https://www.geeksforgeeks.org/c-sharp-constructor-overloading/)