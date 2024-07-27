When there is no additional logic in the property accessors and it introduce in C# 3.0.

بيعمل السيت والجيت اوتو باللوجيك الطبيعي بتاعهم

اني اريتيرن قيمه واخد قيمه احطها في الفيلد

بدون اي لوجيك جديد ساعتها بستخدم الاوتو

```C#
public string Name { get; set; }
```

كده اقدر اقرا واكتب في الفيلد وبقأ اسمه backing field

بدلا من

```C#
public string Name
        {
            get
            {
                return name;
            }
            set
            {
                name = value;//القيمه الي هتتبعت من اليوزر هتكون جوه فاريبل فاليو بس انا مش شايفها
            }
        }
هتقوم بنفس وظيفه الي فوق
```