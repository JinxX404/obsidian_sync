Properties are **first class citizens** in C#. The language defines syntax that enables developers to write code that accurately expresses their design intent.
Properties behave like fields when they're accessed. However, unlike fields, properties are implemented with accessors that define the statements executed when a property is accessed or assigned.


_**accessors:**_ This enables data to be accessed easily and helps to promote the flexibility and safety of methods. Encapsulation and hiding of  information can also be achieved using properties. It uses pre defined methods which are “get” and “set” methods which help to access and modify the properties.  

**Accessors:** The block of “set” and “get” is known as “Accessors”. It is very essential to restrict the accessibility of property. There are two type of accessors i.e.

**get accessors** and **set accessors**.

هي خاصيه بتسمحلي اتحكم في القراءة والكتابه علي فيلد في الكلاس بتاعي

والفيلد الي هعمل عليه بروبيرتي بيكون اسمه **backing field**

  

الجافا مفيهاش بروبيرتي مباشرة 
بستخدم الgetter , setter 


اقدر احط او ارجع قيمه لفيلد بميثودز سيتر وجيتر لاكن الطريقه الافضل اني استخدم بروبيرتي

**(في وقت الكومبايل البروبيرتي بتتحول لسيتر وجيتر والكومبايلر بيعاملهم كاتنين ميثود)**


> [!info] C# | Properties - GeeksforGeeks  
> A Computer Science portal for geeks.  
> [https://www.geeksforgeeks.org/c-sharp-properties/](https://www.geeksforgeeks.org/c-sharp-properties/)




```
public class Person
{
    public string? FirstName { get; set; }

    // Omitted for brevity.
}
```

The syntax shown above is the _auto property_ syntax. The compiler generates the storage location for the field that backs up the property. The compiler also implements the body of the `get` and `set` accessors.

### Auto-Implemented Properties
When there is no additional logic in the property accessors and it introduce in C# 3.0.

فالطبيعي من غير بروبيرتي كنت هعمل اتريبيوت عادي بالداتا تايب بتاعته وهعمله اتنين فانكشن جيتر وسيتر احط وارجع بيهم قيمه

لاكن البروبيرتي بتعملي كل ده فاسطر اقل
بتعمل backing field بدلا من الاتريبيوت 
وبتعمل get , set 


بيعمل السيت والجيت اوتو باللوجيك الطبيعي بتاعهم
لو مش محتاج اعمل اي فاليديشن او حاجه زياده وعايز مجرد اسند قيمه وارجعها يبقي هستخدم الauto implemented property


```C#
public string Name { get; set; }
```

كده اقدر اقرا واكتب في الفيلد وبقأ اسمه backing field

بدلا من

```C#
public string Name
{
    get{
        return name;
    }
    set{
        name = value;//القيمه الي هتتبعت من اليوزر هتكون جوه فاريبل فاليو بس انا مش شايفها
    }
}```
الكيوورد value لما بنستخدمها جوه الset هيعتبرها زي برامتر مبعوت للبروبرتي ويسند القيمه الي فيه جوه الفيلد

هتقوم بنفس وظيفه الي فوق



### Read-Only Property
لو عايز اقرا القيمه فقط
يعني انا عايز اقرا القيمه فقط ومقدرش احطلها قيمه غير جوه الكونستراكتور
يعني انت هتبعتلي قيمه جوه الكونستراكتور هحطها في الفيلد
وهعمل البروبيرتي فيها جيت فقط واقدر اقرا القيمه
لاكن مقدرش اغير فيها تاني
حتي جوه اي ميثود في الكلاس بتاعها

لان اسمها read only مجرد ما البروبيرتي بقيت read only يعني مقدرش اعمل مثلا setValue()

واحطلها قيمه (هيديني ايرور)

```C#
public string Name { get; }
بقوله الفيلد ده هيكون ليه جيت فقط يعني اقدر اقرا منه بس      
```



### Init property
نوع اخر من البروبيرتي

بحط الكيوورد بدلا من السيت

وبتدي سلوك يشبه الread only property

بتخليني مقدرش احط قيمه للفيلد الا بداخل كونستراكتور او بطريقه الobject initializer



```C#
public string Name { get; init; }
```

طريقه الاوبجكت انشيالزر هو اني بديله قيمه لحظه ما انا باخد اوبجكت من الكلاس

```C#
Student s1 = new Student {Name="moataz",Age=20 };
```

بدلا من ال( ) ببدلهم ب {} وبعدين باخد كل فيلد واديله قيمه


###
Suppose that your `Person` class should only enable changing the value of the `FirstName` property from other methods in that class. You could give the set accessor `private` accessibility instead of `public`:

```C#
public class Person
{
    public string? FirstName { get; private set; }

    // Omitted for brevity.
}
```

Now, the `FirstName` property can be accessed from any code, but it can only be assigned from other code in the `Person` class.

لو عايز اخلي البروبرتي read only وفنفس الوقت اقدر اخلي الميثودز بتاعت نفس الكلاس تقدر تغيرها يبقي نعملها private set
لو شيلنا الset محدش يقدر يحطلها قيمه غير الكونستراكتور
لاكن الprivate set يقدر يوصلها اي ميثود داخل نفس الكلاس

نقدر نستخدم معاهم اي access modifier
