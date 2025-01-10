**run time constant**

بيتحدد وقت الرن تايم مين مستخدمه

the `readonly` keyword is used to declare a field that can  
only be assigned a value at the time of declaration or within a  
constructor of the class in which it is defined. Once a  
`readonly` field is assigned a value, it cannot be changed throughout the lifetime of the object.

لما بعمل فيلد ريداونلي

بسمحله يغير قيمه الفاريبل ده بداخل كونستراكتور الكلاس الخاص بيه فقط

مينفعش اعدل قيمه المتغير في اي ميثود مثلا بداخل الكلاس

شبه الكونست كيورد

---

Here's the basic syntax for declaring a `readonly` field:

```C#
public class MyClass
{
    public readonly int MyField;

    public MyClass(int value)
    {
        MyField = value; // Assigning a value to a readonly field in a constructor
    }

    // Other class members and methods
}
```

Key points about `readonly` fields:

1. **Initialization**: A `readonly` field must be assigned a value either at the time of declaration or within the constructor(s) of the class. After that, it cannot be modified.
2. **Constructor Assignment**: You can assign a value to a `readonly` field in one or more constructors of the class. If the class has multiple constructors, each constructor can set the `readonly` field's value, but once set, it remains constant for all instances of the class.
3. **No Further Modification**: You cannot change the value of a `readonly` field in any method or property outside of the constructor(s). Any attempt to do so will result in a compilation error.
4. **Immutability**: `readonly` fields are often used to create immutable objects. Immutable objects have their state set only once and cannot be modified afterward, which can help ensure thread safety and make code more predictable.
5. **Compile-Time Constant**: A `readonly` field can only be assigned a value that can be determined at compile time. This means that the value assigned to a `readonly` field must be a constant, or it must be the result of a compile-time expression.
6. **Usage**: `readonly` fields are commonly used for things like constants, configuration values, or any data that should not change after an object is constructed.

Here's an example of using a `readonly` field to create an immutable `Circle` class:

```C#
public class Circle
{
    public readonly double Radius;
    public readonly double Area;

    public Circle(double radius)
    {
        Radius = radius;
        Area = Math.PI * Radius * Radius;
    }
}
```

In this example, `Radius` and `Area` are both `readonly` fields initialized in the constructor. Once set, they cannot be changed, making the `Circle` class immutable.

> [!info] Readonly in C# - GeeksforGeeks  
> A Computer Science portal for geeks.  
> [https://www.geeksforgeeks.org/readonly-in-c-sharp/](https://www.geeksforgeeks.org/readonly-in-c-sharp/)  

---