
In C#, `Type` is a class that represents information about types in the .NET framework. Every class, struct, enum, and even built-in types (like `int` or `string`) are represented by a `Type` object at runtime. This allows you to inspect and interact with types dynamically.

هو كلاس في الSystem Namespace
بيعبر عن الtype بتاع الobject
وبيوفر معلومات عن الtype لحظة الruntime
You can use the `Type` class to inspect the metadata of types, such as classes, structs, enums, interfaces, and more.

ممكن نجيب تايب اوبجكت معين 
``` C#
int number = 42; 
Type type = number.GetType(); // `type` will be System.Int32

Type type = typeof(string); 
Console.WriteLine(type.Name); // Outputs "String" 
Console.WriteLine(type.Namespace); // Outputs "System" 
Console.WriteLine(type.IsClass); // Outputs "True" (because String is a class)
```

جواه شويه properties زي Name , Namespace, BaseType بترجع معلومات عن التايب ده


### Why Use `Type`?

1. **Inspecting Types**: You can get detailed information about a type, like its name, methods, properties, and more.
2. **Creating Instances Dynamically**: You can create objects of a type at runtime using `Type`.
3. **Checking Type Relationships**: You can check if an object is compatible with a type or if a type is derived from another.