![[adapter-design-pattern.webp]]
هو structural pattern 
لما يكون عندنا نظامين incompatible مع بعض
غير متطابقين 
يعني ده مينفعش يتواصل مع ده بطريقه مباشره 

![[Pasted image 20250108132223.png]]
عندنا اتنين فانكشن واحده بتاخد xml file 
والتانيه بترجع json 
ف محتاجين نعمل adapt  بين الاتنين 
هو ده الادابتر باترن 

كنا هناخد json داتا وعايزين نحولها لxml علشان نبعتها للفانكشن التانيه (الي بتستقبل xml) 
العمليه الي فالنص هي الادابتر 

![[Pasted image 20250108132758.png]]


Two incompatible interfaces or systems can cooperate by using the adapter design pattern, a structural design pattern. Because of incompatible interfaces, it serves as a bridge between two classes that would not otherwise be able to communicate. The adapter approach is very helpful when attempting to incorporate third-party libraries or legacy code into a new system.
لما يكون فيه اتنين سيستم او انترفيسيس مختلفين عن بعض وعايز اخليهم يتواصلو ويشتغلو مع بعض 
الادابتر هيكون مفيد فالحاله دي وهيتصرف كانه كوبري ما بين الاتنين 

بنعمل زي wrapper او adaptor علي الانترفيس علشان تعرف تتواصل مع الشكل الجديد

---

 *Components of Adapter Design Pattern

Below are the components of adapter design pattern:

- ****Target Interface****: Defines the interface expected by the client. It represents the set of operations that the client code can use. It’s the common interface that the client code interacts with.
- ****Adaptee****: The existing class or system with an incompatible interface that needs to be integrated into the new system. It’s the class or system that the client code cannot directly use due to interface mismatches.
- ****Adapter****: A class that implements the target interface and internally uses an instance of the adaptee to make it compatible with the target interface. It acts as a bridge, adapting the interface of the adaptee to match the target interface.
- ****Client****: The code that uses the target interface to interact with objects. It remains unaware of the specific implementation details of the adaptee and the adapter. It’s the code that benefits from the integration of the adaptee into the system through the adapter.

الباترن بيتكون من 4 حاجات 
الاول هو ال target الي عايز اتاقلم عليه وهو الي بيتوقعه الكلاينت
التاني هو ال adaptee ودي  هي الانترفيس الي عايز أاقلمها علي الشكل الجديد (هي الي هتتغير)
التالت هو ال adapter وهو الكوبري بين الاتنين (الكلاينت هيستخدم الكلاس ده)
الكلاس ده بimplement التارجت ومن جواه بيأقلم الadaptee بيستخدم منه instance علشان يخليه يشتغل علي التارجت
الرابع هو ال client وهو الكود الي هيستخدم الادابتر من غير ما يعرف التفاصيل وراه او هو شغال ازاي

----
##### Different implementations of Adapter Design Pattern

The Adapter Design Pattern can be applied in various ways depending on the programming language and the specific context. Here are the primary implementations:

عندنا 4 طرق نقدر نعمل بيهم امبلمنتيشن للباترن
###### ****1. Class Adapter (Inheritan****ce-based)

- In this approach, the adapter class inherits from both the target interface (the one the client expects) and the adaptee (the existing class needing adaptation).
- Programming languages that allow multiple inheritance, like C++, are more likely to use this technique.
- However, in languages like Java and C#, which do not support multiple inheritance, this approach is less frequently used.
الاول هو الكلاس ادابتر وبيستخدم في اللغات الي بتدعم ال multiple inheritance

###### ****2. Object Adapter (Composition-based)****

- The object adapter employs composition instead of inheritance. In this implementation, the adapter holds an instance of the adaptee and implements the target interface.
- This approach is more flexible as it allows a single adapter to work with multiple adaptees and does not require the complexities of inheritance.
- The object adapter is widely used in languages like Java and C#.
التاني هو الاوبجكت ادابتر وبنستخدم فيه الكومبوزيشن 
بناخد instance من ال adaptee جوه الادابتر وبنعمل implements للتارجت 
وبنعمل map لكل ميثود بين الاتنين 
###### ****3. Two-way Adapter****

- A two-way adapter can function as both a target and an adaptee, depending on which interface is being invoked.
- This type of adapter is particularly useful when two systems need to work together and require mutual adaptation.

###### ****4. Interface Adapter (Default Adapter)****

- When only a few methods from an interface are necessary, an interface adapter can be employed.
- This is especially useful in cases where the interface contains many methods, and the adapter provides default implementations for those that are not needed.
- This approach is often seen in languages like Java, where abstract classes or default method implementations in interfaces simplify the implementation process.



---
#####



![[Class-Diagram-of-Adapter-Design-Pattern_.webp]]
الlegacyprinter هو الadaptee الي عايزين نخليه يتاقلم عالجديد 
جواه ميثود printDocument 
الكلاينت هيناديها print من الprinter target class 
ف عايزين حد فالنص هو الي ينادي الميثود دي مكان دي
الكلاينت بيستخدم التارجت

