https://stackoverflow.com/questions/740658/whats-the-difference-between-an-object-initializer-and-a-constructor

C# 3.0 (.NET 3.5) introduced _Object Initializer Syntax_, a new way to initialize an object of a class or collection. Object initializers allow you to assign values to the fields or properties at the time of creating an object without invoking a constructor.

بيفيد في اننا نحط قيم للproperites , fields من غير ما نحتاج الكونستراكتور 

ايه الفرق بينه وبين الكونستراكتور؟
الكونستراكتور بياخد البرامترز الي هباصيها وهيروح يعمل اوبجكت بيهم ويرجع الريفرنس فالفاريبل 
يعني الكونستراكتور هيتنفذ الاول

لاكن الاوبجكت انشياليزر بيتنفذ بعد الكونستراكتيد بتاع الاوبجكت 
يعني بعد ما يتنفذ الكونستراكتور (الاوبجكت اتعمل)
هيروح يعمل انشياليزيشن للقيم دي الي انا باصيتها


Object Initializers were something added to C# 3, in order to simplify construction of objects when you're using an object.

Constructors run, given 0 or more parameters, and are used to create and initialize an object _before_ the calling method gets the handle to the created object. For example:

```csharp
MyObject myObjectInstance = new MyObject(param1, param2);
```

In this case, the constructor of `MyObject` will be run with the values `param1` and `param2`. These are both used to create the new `MyObject` in memory. The created object (which is setup using those parameters) gets returned, and set to `myObjectInstance`.

In general, it's considered good practice to have a constructor require the parameters needed in order to completely setup an object, so that it's impossible to create an object in an invalid state. 
الكونستراكتور مفيد لو هحتاج اباصي قيم الاوبجكت مينفعش يتعمل غير بيها (اساسي)

An Object Initializer lets you set properties or fields on your object _after_ it's been constructed, but _before_ you can use it by anything else. For example:

```csharp
MyObject myObjectInstance = new MyObject(param1, param2)
{
    MyProperty = someUsefulValue
};
```

This will behave about the same as if you do this:

```csharp
MyObject myObjectInstance = new MyObject(param1, param2);
myObjectInstance.MyProperty = someUsefulValue;
```

في الاوبجكت انشياليزر كاننا عملنا الاوبجكت وبعد ما خلصنا روحنا نادينا علي البروبرتي دي وحطينا جواها القيمه

