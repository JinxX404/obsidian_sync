Inheritance is a fundamental concept in object-oriented programming that allows us to define a new class based on an existing class. The new class inherits the properties and methods of the existing class and can also add new properties and methods of its own. Inheritance promotes code reuse, simplifies code maintenance, and improves code organization.

In C#, there are 4 types of inheritance:

1. Single inheritance: A derived class that inherits from only one base class.
2. Multi-level inheritance: A derived class that inherits from a base class and the derived class itself becomes the base class for another derived class.
3. Hierarchical inheritance: A base class that serves as a parent class for two or more derived classes.
4. Multiple inheritance: A derived class that inherits from two or more base classes. (using interfaces)

### Advantages of Inheritance:

1. Code Reusability: Inheritance allows us to reuse existing code by inheriting properties and methods from an existing class.
2. Code Maintenance: Inheritance makes code maintenance easier by allowing us to modify the base class and have the changes automatically reflected in the derived classes.
3. Code Organization: Inheritance improves code organization by grouping related classes together in a hierarchical structure.
### Disadvantages of Inheritance:

1. Tight Coupling: Inheritance creates a tight coupling between the base class and the derived class, which can make the code more difficult to maintain.
2. Complexity: Inheritance can increase the complexity of the code by introducing additional levels of abstraction.
3. Fragility: Inheritance can make the code more fragile by creating dependencies between the base class and the derived class.


###
- **Super Class:** The class whose features are inherited is known as super class(or a base class or a parent class).
- **Sub Class:** The class that inherits the other class is known as subclass(or a derived class, extended class, or child class). The subclass can add its own fields and methods in addition to the superclass fields and methods.

**Important facts about inheritance in C#**

- **Default Superclass**: Except Object class, which has no superclass, every class has one and only one direct superclass(single inheritance). In the absence of any other explicit superclass, every class is implicitly a subclass of Object class.
- **Superclass can only be one:** A superclass can have any number of subclasses. But a subclass can have only **one** superclass. This is because C# does not support multiple inheritance with classes. Although with interfaces, multiple inheritance is supported by C#.
- **Inheriting Constructors:** A subclass inherits all the members (fields, methods) from its superclass. Constructors are not members, so they are not inherited by subclasses, but the constructor of the superclass can be invoked from the subclass.
- **Private member inheritance:** A subclass does not inherit the private members of its parent class. However, if the superclass has properties(get and set methods) for accessing its private fields, then a subclass can inherit.


###
علشان نحدد ان الكلاس ده هيورث من تاني فالكود بنكتب : وبعدها اسم الكلاس 
عكس الجافا بنكتب extend


لما بنعمل inherite لكلاس
ف الكومبايلر من نفسه بيعمل اوبجكت من الparent جوه الchild 
والاوبجكت ده بنشاور علي الريفرنس بتاعه ب base keyword
زي super فالجافا
كده اقدر اشاور علي الميمبرز بتاعت الاب ب base.  
او استخدم الconstructor بتاع الاب ب base()

---
عندنا access modifier جديد للميمبرز اسمه protected وبيكون ما بين الpublic , private فالصلاحيات بتاعته 

اقدر اوصل للفاريبلز البروتيكتد عن طريق الابناء (لو حد واخد اوبجكت من الابن مقدرش اوصل للبروتيكتد الي هو اصلا وارثه من السوبر)

البروتيكتد اقدر اوصله من نفس الكلاس والكلاسات الي وارثه منه فقط 

----

 [Internal](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/internal) members are visible only in derived classes that are located in the same assembly as the base class. They are not visible in derived 
 classes located in a different assembly from the base class.
 الinternal members اقدر اشوفهم من الابناء الي جوه نفس الاسيمبلي بس

----

عندنا modifier تاني اسمه sealed 
بيمنع ان حد يقدر يورث من الكلاس ده 
بيمنع الinheritance

```csharp
sealed class Vehicle 
{
  ...
}

class Car : Vehicle 
{
  ...
}
```

The error message will be something like this:
`'Car': cannot derive from sealed type 'Vehicle'`



----
### C# Default Behavior:

- In C#, just like in Java, when you create an instance of a derived class, the base class constructor is called first.
- If you don't explicitly call a base class constructor using `base(...)`, C# will try to call the **parameterless** (default) constructor of the base class.
-لما بنعمل اوبجكت من الchild class 
اول حاجه هتتنفذ هي الكونستراكتور بتاع الاب وبعده الابن

في كونستراكتور الابن محتاج انادي كونستراكتور الاب ب base 
ف ديفولت هو هينادي الparameterless constructor من الاب
لو مفيش واحد parameterless ف هيديلي ايرور 
##### Example 1: Base Class with Parameterless Constructor

###### Base Class
```C#
public class Person
{
    public string Name;

    // Parameterless constructor
    public Person()
    {
        Name = "Default Name";
        Console.WriteLine("Person parameterless constructor called.");
    }
}
```

###### Derived Class
```C#
public class Student : Person
{
    public int StudentId;

    public Student(int studentId)
    {
        StudentId = studentId;
        Console.WriteLine("Student constructor called.");
    }
}
```
###### What Happens:

- Since `Person` has a parameterless constructor, you don't need to explicitly call it in `Student`.
- The `Student` constructor works without errors because C# automatically calls the parameterless constructor of `Person`.

###### Output:
```
Person parameterless constructor called.
Student constructor called.
```
مش هتحصل مشكله لانه لقي كونستراكتور parameterless ونفذه ديفولت 
المشكله هتحصل لو مش هيلاقيه 


##### Example 2: Base Class Without Parameterless Constructor

###### Base Class
```C#
public class Person
{
    public string Name;

    // Constructor with parameters
    public Person(string name)
    {
        Name = name;
        Console.WriteLine("Person constructor with name called.");
    }
}
```
###### Incorrect Derived Class (Will Cause an Error)
```C#
public class Student : Person
{
    public int StudentId;

    public Student(int studentId)
    {
        StudentId = studentId;
        Console.WriteLine("Student constructor called.");
    }
}
```
###### What Happens:

- C# will try to call a parameterless constructor in `Person`, but since it doesn't exist, this code will **not compile** and will produce a compile-time error.

###### Error Message:
```
'Person' does not contain a constructor that takes 0 arguments.
```

###### Corrected Version:

You need to explicitly call the base class constructor using `base(...)` in the `Student` constructor:

```C#
public class Student : Person
{
    public int StudentId;

    public Student(string name, int studentId) : base(name)
    {
        StudentId = studentId;
        Console.WriteLine("Student constructor called.");
    }
}
```


###### What Happens Now:

- The `Student` constructor now correctly calls the `Person` constructor with the `name` argument.
- This ensures that `Name` is properly initialized.

###### Output:

```
Person constructor with name called.
Student constructor called.
```


لما ملقيش paramterless construcor هيديلي ايرور 
هحتاج اشاور بنفسي علي الكونستراكتور الي موجود باستخدم base 