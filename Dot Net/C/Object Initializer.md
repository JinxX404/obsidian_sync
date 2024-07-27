> [!info] Object and Collection Initializer in C# - GeeksforGeeks  
> A Computer Science portal for geeks.  
> [https://www.geeksforgeeks.org/object-and-collection-initializer-in-c-sharp/](https://www.geeksforgeeks.org/object-and-collection-initializer-in-c-sharp/)  

بيسمحلي ادي قيم ابتدائيه للفيلد بتاعتي من غير ما استخدم الكونستراكتور ولحظه ما بعمل الاوبجكت بقدر اديله القيم

  

```C#
Type instance = new Type
{
    Property1 = value1,
    Property2 = value2,
    // ...
};
```

```C#
public class Person
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
}

// Create and initialize a Person object using an object initializer
Person person = new Person
{
    FirstName = "John",
    LastName = "Doe"
};
```

Object initializers are particularly useful when you need to create objects with a significant number of properties or fields that need to be set to specific values, as they help improve code readability and reduce the number of lines of code required.