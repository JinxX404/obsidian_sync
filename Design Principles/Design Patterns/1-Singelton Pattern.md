**Singleton** is a creational design pattern that lets you ensure that a class has only one instance, while providing a global access point to this instance.


**Ensure that a class has just a single instance**. Why would anyone want to control how many instances a class has?
The most common reason for this is to control access to some shared resource—for example, a database or a file.

imagine that you created an object, but after a while decided to create a new one. Instead of receiving a fresh object, you’ll get the one you already created.

Note that this behavior is impossible to implement with a regular constructor since a constructor call **must** always return a new object by design.

###### Solution

All implementations of the Singleton have these two steps in common:

- Make the default constructor private, to prevent other objects from using the `new` operator with the Singleton class.
- Create a static creation method that acts as a constructor. Under the hood, this method calls the private constructor to create an object and saves it in a static field. All following calls to this method return the cached object.

or 
* It is recommended to create a private constructor. It will actually generate an error (cannot create an
* instance from a private constructor). How to create an instance from the private constructor? It should be inside the class and the instance must be created using the access modifiers (private).
 * Creation of a private static reference from the class.
 * Then, use a public static getter method called getinstance to return the created instance, but start check first if the instance is null or not. If Null (create a instance) before getting it.

###### Real-World Analogy

The government is an excellent example of the Singleton pattern. A country can have only one official government. Regardless of the personal identities of the individuals who form governments, the title, “The Government of X”, is a global point of access that identifies the group of people in charge.


###### Structure

![The structure of the Singleton pattern](https://refactoring.guru/images/patterns/diagrams/singleton/structure-en-indexed.png)

1. The **Singleton** class declares the static method `getInstance` that returns the same instance of its own class.
    
    The Singleton’s constructor should be hidden from the client code. Calling the `getInstance` method should be the only way of getting the Singleton object.


###### Applicability

Use the Singleton pattern when a class in your program should have just a single instance available to all clients; for example, a single database object shared by different parts of the program.

The Singleton pattern disables all other means of creating objects of a class except for the special creation method. This method either creates a new object or returns an existing one if it has already been created.

Use the Singleton pattern when you need stricter control over global variables.

Unlike global variables, the Singleton pattern guarantees that there’s just one instance of a class. Nothing, except for the Singleton class itself, can replace the cached instance.

Note that you can always adjust this limitation and allow creating any number of Singleton instances. The only piece of code that needs changing is the body of the `getInstance` method.


###### Types
عندنا نوعين من السينجلتون 
اما Lazy او Eager 

* Creation of an instance based on the static getter method (getinstance) is called **Lazy Singleton.**
*  In other words, the instance is default null and it is created when the get instance is called. 
ال lazy بمعني كسول مش هيتعمل غير لما اناديه ب الميثود الي هتكرييت الاوبجكت 
* There is another was to create a singleton pattern based on **Eager Singleton**. It is based on the creation of an instance in the class without the getter method and using public static access modifiers.
ال eager بيتعمله كرييت مع كرييت الكلاس باستخدام public static refrence وهخزن جواه الاوبجكت, مش محتاج اناديه بميثود 
وهعمل برايفت كونستراكتور 
![[Pasted image 20241124205759.png]]

![[Pasted image 20241124205812.png]]
كل مره هأكسس نفس الاوبجكت علشان متشال في static ref ف هيكون ثابت

An Eager Singleton creates an instance of the Singleton class as soon as the application starts, whereas a Lazy Singleton creates the instance only when it's actually needed.

* The primary reason we don’t always use eager initialization is its potential to be resource-intensive. (Eager initialization means creating the instance of the singleton as soon as the program starts, regardless of whether it will actually be used. This can be wasteful if the class requires a lot of resources to initialize or if the singleton instance is never actually used).
السبب الي مش بيخلينا نستخدم الeager انه بيعمل الاوبجكت لما البرنامج يبدا وممكن اكون مش محتاجه فالوقت ده ف هياخد resources 


* Eager initialization doesn’t offer the same degree of control as lazy initialization. For instance, you might wish to initialize your Singleton based on specific conditions, after certain tasks are completed, or perhaps after fetching configurations from a server. Eager initialization restricts such flexibility
ومش موجود فيه ال flexibility الي موجوده في الlazy 
بسبب انه مش جوه فانكشن زي getInstance تخليني اتحكم في كونديشنز مثلا 
لما اكون محتاج كونديشن معينه تتحقق علشان اعمل الاوبجكت وهكذا


One significant drawback of the lazy singleton design pattern lies in its multi-threaded complexity. The synchronization required can present challenges that might make you question your career choice as a programmer. (In a multi-threaded environment, if two threads try to create an instance of the singleton at the same time, they may both succeed, leading to multiple instances of the class, which defeats the purpose of the singleton pattern. To prevent this, synchronization is required, which adds complexity and performance overhead). In constrast on eager singleton (Since the instance is created at class loading time, there’s no need for synchronization when accessing it. The instance is guaranteed to be initialized before any thread accesses it.)
الlazy مشكلته في ال multi-threaded environment لو اتنين ثريد حاولو يعملو ال instance فنفس الوقت ف ممكن ينجحو وكده هيكون فيه اكتر من instance من الكلاس وهنكسر الباترن


Another substantial concern with the lazy singleton design pattern is the unpredictable instantiation time
مش متوقعين الوقت الي هنعمل فيه call لل getInstance ونعمل الاوبجكت


###### Pros and Cons

 Pros
- You can be sure that a class has only a single instance.
- You gain a global access point to that instance.
- The singleton object is initialized only when it’s requested for the first time.

Cons
- Violates the _Single Responsibility Principle_. The pattern solves two problems at the time.
- The Singleton pattern can mask bad design, for instance, when the components of the program know too much about each other.
- The pattern requires special treatment in a multithreaded environment so that multiple threads won’t create a singleton object several times.
- It may be difficult to unit test the client code of the Singleton because many test frameworks rely on inheritance when producing mock objects. Since the constructor of the singleton class is private and overriding static methods is impossible in most languages, you will need to think of a creative way to mock the singleton. Or just don’t write the tests. Or don’t use the Singleton pattern.