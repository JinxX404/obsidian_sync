struct is immutable

  

![[/Untitled 5.png|Untitled 5.png]]

الكلاس والاستراكت يوزر ديفايند يعني بنعملهم بنفسنا

---

الاتنين بيقبلو كونستراكتور

---

مقدرش ادي قيمه ابتدائيه للفيلدس جوه الاستراكت

اقدر ادي قيمه للكونست فاريبل

```C#
int x=10; //wrong
```

---

**لاكن الاستراكت مبيقبلش بارميتارليس كونستاركتور يعني لازم كونستراكتور بباصيله قيمه**

**لو بدون براميتر هيدي ايرور لانه مش مسموحلي اعمل اوفرايد علي الباراميترليس كونستراكتور الديفولت بتاع الاستراكت**

لاكن في الكلاس اقدر اعمل اوفرايد علي النو ارجومينت كونستراكتور

---

الاستراكت اقدر احط فيه فيلدس

لاكن الاستراكت غير محبذ للداتا تايب الكبيره

يعني الكونفنشنت انهم بيستخدموه لداتا تايب لحد 16 بايت

يعني يقدر يشيل 4 فاريبل انتجر

وغير محبذ اننا نستخدم ريفرنس تايب فاريبلز جواه لانه غير محدد ليها داتا تايب وممكن نزيد عن 16 بايت زي الاسترينج

---

الاستراكت جواه ميثودز وانديكسرز وبروبيرت وايفينت وابيرتور اوفرلودينج

---

مش بيقبل ديستراكت او فاينليزر

---

مش بيقبل التوريث لاكن هو وارث من الاوبجكت كلاس بشكل ضمني

لان كل العناصر الي في اللغه وارثه من الاوبجكت كلاس

---

الاستراكت فاليو تايب يعني كله بيتخزن في الاستاك (بكل الي جواه)

عكس الكلاس ريفرنس تايب بيتخزن الفاريبل ادينتفاير جوه الاستاك لاكن بيشاورو علي الكلاس فالهيب ميموري

---

الاستراكت مش لازم اعمله ب نيو كيوورد

مش اجباري

```C#
class Program
    {
        static void Main(string[] args)
        {

            Person p;
            p.doSeomthing();
        }
    }
    struct Person
    {
        public void doSeomthing()
        {
            Console.WriteLine("Hello");
        }
    }
```

لاكن ممكن استخدم النيو كييورد في حاله ان عندي فيلد جوه الاستراكت (لان الفيلد مش واخد قيمه ابتدائيه ومن غير كونستراكتور بكيوورد نيو هو مش هياخد قيمه)

```C#
class Program
    {
        static void Main(string[] args)
        {

            Person p;
            p.doSeomthing();//error
        }
    }
    struct Person
    {
        public int Id;
        public void doSeomthing()
        {
            Console.WriteLine("Hello");
        }
    }
```

في الحاله دي عندي حلين

اما استخدم نيو كيورد ويعمل كونستراكتور ضمني ويدي قيمه ابتدائيه للفيلد وساعتها مفيش مشكله

```C#
static void Main(string[] args)
        {

            Person p = new Person();
            p.doSeomthing();//no problem
        }
```

الحل التاني اني اكسس علي الفاريبل واديله قيمه ابتدائيه

```C#
static void Main(string[] args)
        {

            Person p;
            p.Id = 2;
            p.doSeomthing();//no problem
        }
```

---

---