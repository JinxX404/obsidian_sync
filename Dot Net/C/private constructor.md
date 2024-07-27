> [!info] Private Constructors in C# - GeeksforGeeks  
> A Computer Science portal for geeks.  
> [https://www.geeksforgeeks.org/private-constructors-in-c-sharp/](https://www.geeksforgeeks.org/private-constructors-in-c-sharp/)  

بنعمل الكونستراكتورز بتوعنا برايفت علشان نمنع الكلاسات انها تاخد اوبجكت مني

وبستخدم ميثود ستاتيك داخل الكلاس بتاعي هي الي تعمل مني اوبجكت وترجعه

مقدرش اعمل اي اوبجكت الا من الميثود دي

A private constructor in C# is used for several specific purposes, and its primary role is to control and restrict the instantiation of a class. Here are some common reasons to use a private constructor:

1. **Singleton Pattern**: One of the most common use cases for a private constructor is when implementing the Singleton design pattern. A Singleton ensures that a class has only one instance and provides a global point of access to that instance. By making the constructor private, you prevent the creation of multiple instances from outside the class.
    
    ```C#
    public class Singleton
    {
        private static Singleton instance;
    
        private Singleton() { } // Private constructor
    
        public static Singleton GetInstance()
        {
            if (instance == null)
            {
                instance = new Singleton();
            }
            return instance;
        }
    }
    ```
    
2. **Utility Classes**: Sometimes, you might have a class that contains only static methods or fields and should not be instantiated. In such cases, you can make the constructor private to prevent accidental instantiation.
    
    ```C#
    public static class UtilityClass
    {
        private UtilityClass() { } // Private constructor
    
        public static void DoSomething() { }
    }
    ```
    
3. **Factory Methods**: Private constructors can be used in combination with public static factory methods to control object creation and initialization. The factory method can provide more context or customization options than a public constructor.
    
    ```C#
    public class Product
    {
        private Product() { } // Private constructor
    
        public static Product CreateProduct(string name, decimal price)
        {
            var product = new Product();
            product.Name = name;
            product.Price = price;
            return product;
        }
    
        public string Name { get; private set; }
        public decimal Price { get; private set; }
    }
    ```
    
4. **Immutable Types**: In cases where you want to create immutable types (types whose state cannot be changed after construction), you can make all properties read-only and initialize them in the private constructor.
    
    ```C#
    public class ImmutablePerson
    {
        public string Name { get; }
        public int Age { get; }
    
        private ImmutablePerson(string name, int age)
        {
            Name = name;
            Age = age;
        }
    
        public static ImmutablePerson Create(string name, int age)
        {
            return new ImmutablePerson(name, age);
        }
    }
    ```
    
5. **Preventing Inheritance**: By making the constructor private in a class, you can prevent the class from being subclassed outside of the current assembly.
    
    ```C#
    public class SealedClass
    {
        private SealedClass() { } // Private constructor
    }
    ```
    

In summary, a private constructor in C# serves various purposes, including controlling object creation, enforcing design patterns like Singleton and Factory, ensuring immutability, and preventing inheritance or accidental instantiation of utility classes. It provides a level of control over how instances of a class are created and used.

The use cases for private constructors and the patterns or scenarios they enable are all related to controlling how objects are created, initialized, and used in your C# code. Let me break down each use case and its rationale:

1. **Singleton Pattern**:
    - **Use Case**: Ensuring that a class has only one instance and providing a global point of access to that instance.
    - **Rationale**: This is useful in scenarios where you want a single, shared instance of a class to manage a particular resource or state, such as a configuration manager, a connection pool, or a logging service.
2. **Utility Classes**:
    - **Use Case**: Preventing the instantiation of a class that contains only static methods or fields.
    - **Rationale**: Utility classes typically provide helper methods or constants and don't need to be instantiated. Making the constructor private prevents users of the class from accidentally creating instances when they shouldn't.
3. **Factory Methods**:
    - **Use Case**: Controlling object creation and providing more context or customization options than a public constructor.
    - **Rationale**: Factory methods allow you to encapsulate the logic of object creation, perform validation, and provide a more expressive way to create instances. They can also be used for object pooling and recycling.
4. **Immutable Types**:
    - **Use Case**: Creating types whose state cannot be changed after construction, ensuring thread safety and predictability.
    - **Rationale**: Immutable types simplify code by eliminating the need for synchronization when working with objects across multiple threads. They also make it easier to reason about the state of an object.
5. **Preventing Inheritance**:
    - **Use Case**: Preventing a class from being subclassed outside of the current assembly.
    - **Rationale**: In some cases, you want to ensure that a class is not extended or modified in ways that could break its functionality or violate its contract. By making the constructor private, you prevent inheritance from classes outside the assembly.

These use cases and patterns are design principles that help you write robust, maintainable, and predictable code. They enforce best practices, such as encapsulation, immutability, and single responsibility, which contribute to better software architecture and reduce the likelihood of bugs and unexpected behavior.

While not all code will require the use of private constructors or these patterns, they are tools in your toolkit that you can apply when they align with the specific design goals and requirements of your application.