
Applied to a member to indicate that it belongs to the class itself, not to instances of the class. Static members are accessed through the class name.

بنناديه باسم الكلاس

---

فاريبل الاستايتك بيتخزن في منطقه اسمها

high frequency heap

جوه الheap memory

وبتكون مساحتها صغيره لاكن الوصول للفاريبلز جواها سريع

---
عندنا static class 
لما بستخدم static بيمنع اننا ناخد اوبجكت من الكلاس ده 
والstatic بيشيل جواه static فقط 
مقدرش استخدم جواه non-static سواء fields or functions

لو الclass non static اقدر احط جواه static لاكن العكس مينفعش
لو الكلاس فيه non static method بناديها من بره باسم الكلاس
مينفعش اخد اوبجكت واناديها منه
لانها مش تبع الاوبجكت



الكونستراكتور بتاع الstatic class هيتنادي مره واحده فقط لما اعمل call منه 
يعني لو عملت 15 call لميثود جواه 
الكونستراكتور هيتنفذ اول حاجه ومره واحده فقط 
```c#
static MyStaticClass()  
{  

}
```
بنحط static keyword للكونستراكتور

```c#
class Program  
{  
    static void Main(string[] args)  
    {       
        MyStaticClass.doSomethingStatic();  
        MyStaticClass.doSomethingStatic();  
        MyStaticClass.doSomethingStatic();  
        MyStaticClass.doSomethingStatic();  
        MyStaticClass.doSomethingStatic();  
        MyStaticClass.doSomethingStatic();  
        MyStaticClass.doSomethingStatic();  
        MyStaticClass.doSomethingStatic();  
    }  
}

public static class MyStaticClass  
{  
  
    public static string NameStatic { get; set; };
   
  
    static MyStaticClass()  
    {  
     Console.WriteLine("Hello from static constructor");  
    }    
    public static void doSomethingStatic()  
    {   
    Console.WriteLine("Hello World from static method");  
    }   
    }
}


```

مع الcalls الكتير الي عملتها
الكونستراكتور هيتنفذ اول مره فقط وبعده باقي الcalls
```
Hello from static constructor
Hello World from static method
Hello World from static method
Hello World from static method
Hello World from static method
Hello World from static method
Hello World from static method
Hello World from static method
Hello World from static method
```


#### Rules for Static Class

1. Static classes cannot be instantiated.
2. All the members of a static class must be static; otherwise the compiler will give an error.
3. A static class can contain static variables, static methods, static properties, static operators, static events, and static constructors.
4. A static class cannot contain instance members and constructors. 
هنا الinstance معناها non-static
5. Indexers and destructors cannot be static
6. `var` cannot be used to define static members. You must specify a type of member explicitly after the `static` keyword.
7. Static classes are sealed class and therefore, cannot be inherited.
8. A static class cannot inherit from other classes.
9. Static class members can be accessed using `ClassName.MemberName`.
10. A static class remains in memory for the lifetime of the application domain in which your program resides.

The normal class (non-static class) can contain one or more static methods, fields, properties, events and other non-static members.

It is more practical to define a non-static class with some static members, than to declare an entire class as static.


#
---
1. **Static Methods and Fields**:
    - Static methods are associated with the class itself, not with instances of the class. You can call them using the class name, and you don't need to create an instance of the class to invoke them, just like in Java.
    - Static fields are also associated with the class and are shared among all instances of the class. They can be accessed using the class name.

Example of calling static members in C#:

```C#
public class MyClass
{
    // Static field
    public static int staticField = 42;

    // Static method
    public static void StaticMethod()
    {
        Console.WriteLine("This is a static method.");
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Accessing static field
        int fieldValue = MyClass.staticField;

        // Calling static method
        MyClass.StaticMethod();
    }
}
```

1. **Non-Static (Instance) Methods and Fields**:
    - Non-static methods and fields are associated with instances (objects) of the class, just like in Java. You need to create an object of the class to access them.

Example of calling non-static members in C#:

```C#
public class MyClass
{
    // Non-static field
    public int nonStaticField = 0;

    // Non-static method
    public void NonStaticMethod()
    {
        Console.WriteLine("This is a non-static method.");
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Create an object of MyClass
        MyClass obj = new MyClass();

        // Accessing non-static field
        int fieldValue = obj.nonStaticField;

        // Calling non-static method
        obj.NonStaticMethod();
    }
}
```

So, in C#, the concepts are quite similar to Java regarding static and non-static members. Non-static methods and fields in C# are associated with instances and require objects to access, just like in Java.

---

methods and fields can be classified as either static or non-static (also called instance). The difference between these two types lies in how they are associated with the class and objects created from that class:

1. **Static Methods and Fields**:
    - Static methods belong to the class itself, not to any particular instance (object) of the class. They can be called using the class name, and you don't need to create an instance of the class to invoke them. For example, `ClassName.staticMethod()`.
    - Static fields are also associated with the class and are shared among all instances of the class. They can be accessed using the class name as well, like `ClassName.staticField`.
2. **Non-Static (Instance) Methods and Fields**:
    - Non-static methods and fields are associated with instances (objects) of the class. You need to create an object of the class to access them. For example, `ClassName object = new ClassName();` to create an instance, and then `object.nonStaticMethod()` to call a non-static method, or `object.nonStaticField` to access a non-static field.

When you have a non-static method, it typically operates on the data that belongs to a specific instance of the class. Since non-static methods are associated with instances, they don't exist until you create an object from the class. Therefore, you need an object to invoke a non-static method because the method may need to work with the specific data and state of that object.

In other words, non-static methods often access and manipulate the instance (object) variables, which are unique to each instance. That's why you need an object to call a non-static method because the method's behavior is specific to the instance it's called on.

Here's a simple example to illustrate this concept:

```Java
public class MyClass {
    // Non-static field
    private int value;

    // Constructor to initialize the value
    public MyClass(int value) {
        this.value = value;
    }

    // Non-static method that uses the instance variable
    public void printValue() {
        System.out.println("Value: " + value);
    }

    public static void main(String[] args) {
        // Create an object of MyClass
        MyClass obj = new MyClass(42);

        // Call the non-static method using the object
        obj.printValue();
    }
}
```

In this example, `printValue()` is a non-static method that accesses the `value` instance variable. You can only call `printValue()` by creating an object (`obj`) because it operates on the specific `value` associated with that instance.

In summary, non-static methods are tied to the state of individual instances of a class, so you need to create objects to use them and access the instance-specific data.



----
```C#
public class StopWatch
{
    public static int NoOfInstances = 0;
    
    // instance constructor
    public StopWatch()
    {
        StopWatch.NoOfInstances++;
    }
}

class Program
{
    static void Main(string[] args)
    {
        StopWatch sw1 = new StopWatch();
        StopWatch sw2 = new StopWatch();
        Console.WriteLine(StopWatch.NoOfInstances); //2 
			
        StopWatch sw3 = new StopWatch();
        StopWatch sw4 = new StopWatch();
        Console.WriteLine(StopWatch.NoOfInstances);//4
    }
}

```
مثال علي الshared field 
الnoOfIstances مشترك ما بينهم كلهم لانه static
مش حكر علي اوبجكت معين 

يعني كل مره هعمل اوبجكت جديد هروح ااكسس نفس الfield الي موجود وهزود عليه 
مش هعمل واحد جديد لكل اوبجكت


---
#### Static Methods:

You can define one or more static methods in a non-static class. Static methods can be called without creating an object. You cannot call static methods using an object of the non-static class.

The static methods can only call other static methods and access static members. You cannot access non-static members of the class in the static methods.

منقدرش نوصل لnon static variable او ميمبر من جوه الstatic method
لازم تكون Static

مثلا لو عندي global non static variable وعايز اشوفه من الmain (static) ف مش هعرف 
هضطر اعمله static 
او هاخد اوبجكت من الكلاس واناديه منه

1. Static methods can be defined using the `static` keyword before a return type and after an access modifier.
2. Static methods can be overloaded but cannot be overridden.
3. Static methods can contain local static variables.
4. Static methods cannot access or call non-static variables unless they are explicitly passed as parameters.

----
#### Static Constructors:
اقدر احط static and instance constructors في الnon static class

لو معملتش اوبجكت من الكلاس كده مش هستخدم new ف مش هنادي الinstance constructor 
لاكن ناديت فانكشن
ف هينادي الstatic constructor

لو عملت اوبجكت 
هينادي الstatic مره واحده وبعده الinstance

```c#
class Program  
{  
    public static int numm = 5;  
  
   static void Main(string[] args)  
    {          
	    MyStaticClass.doSomethingStatic();//static method call
    }  
}

public class MyStaticClass  
{  
  
    public static string NameStatic { get; set; }  

	static MyStaticClass()  
    {       
	 Console.WriteLine("Hello from static constructor");  
    }  
    
    public MyStaticClass()  
    {     
     Console.WriteLine("Hello From Instance Constructor");  
    }    
    
    public static void doSomethingStatic()  
    {       
     Console.WriteLine("Hello World from static method");  
    }     
    
 }
 }
```
لما ناديت الstatic method 
هيروح ينادي الstatic constructor فالاول وبعده الميثود
```
Hello from static constructor
Hello World from static method
```
مش هينفذ الinstance constructor علشان معملناش اوبجكت 


```c#
MyStaticClass obj = new MyStaticClass();  
obj.doSomething();  
MyStaticClass obj2 = new MyStaticClass();  
obj2.doSomething();
```
لو عملت اوبجكتس هيروح ينادي اول حاجه ال static constructor مره واحده وبعده ينادي الinstance constructor لكل اوبجكت هيتعمل

1. The static constructor is defined using the `static` keyword and without using access modifiers public, private, or protected.
2. A non-static class can contain one parameterless static constructor. Parameterized static constructors are not allowed.
3. Static constructor will be executed only once in the lifetime. So, you cannot determine when it will get called in an application if a class is being used at multiple places.
4. A static constructor can only access static members. It cannot contain or access instance members.
##### Usage

- A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.
- Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.
- Static constructors are also a convenient place to enforce run-time checks on the type parameter that can't be checked at compile time via type-parameter constraints.




#### Static members are stored in a special area in the memory called High-Frequency Heap. Static members of non-static classes are shared across all the instances of the class. So, the changes done by one instance will be reflected in all the other instances.



https://www.tutorialsteacher.com/csharp/csharp-static
