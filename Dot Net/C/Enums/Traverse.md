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
                Console.WriteLine($"{month} = {(int)Enum.Parse(typeof(Month),month)}");
            }
```