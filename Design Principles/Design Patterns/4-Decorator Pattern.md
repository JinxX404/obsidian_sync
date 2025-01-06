•It is one of the structural design patterns. It sometimes it is called Wrapper because to cover or protect the object. It extends or modifies its behavior dynamically, without changing its underlying class. We add a dynamic behavior to the code. It is one of the most important patterns that can help in achieving the software principle: closed for modification and open for extension.

•This pattern starts with a concrete class that implements a specific interface component. To perform changes in this concrete class we implement an abstract class called Decorator. We perform the required changes using several decorators (Decorator1, Decorator2, and so on). These changes are presented on the original concrete class.

**Decorator** is a structural design pattern that lets you attach new behaviors to objects by placing these objects inside special wrapper objects that contain the behaviors.



هو structural design pattern 
بنستخدمه علشان نحافظ علي حالة اوبجكت معين من الاضافات الجديده الي ممكن نضيفها
يعني لو فيه كلاس معين عنده behaviors معينه 
وعايزين نضيف ميثودز تاني بس فنفس الوقت مش عايزين نعدل عالكلاس ده علشان نحقق ال OCP 

هنستخدم ال decorator pattern 
هو ابستراكت كلاس بيكون نسخه من الconcrete class الي كنا عايزين نضيف عليه 
وبعدين بنعمل تحته الكلاسات الباقيه الي فيها التعديلات الجديده 

![[Pasted image 20250106180039.png]]

الconcrete class وال decorator class هيورثو من نفس الinterface يعني بينهم حاجات مشتركه 

وكلاسات ال concreteDecorator فيهم الميثودز الجديده الي كنا عايزين نضيفها علي الكونكريت كلاس



![[Pasted image 20250106194525.png]]



-----
Use the Decorator pattern when you need to be able to assign extra behaviors to objects at runtime without breaking the code that uses these objects.

The Decorator lets you structure your business logic into layers, create a decorator for each layer and compose objects with various combinations of this logic at runtime. The client code can treat all these objects in the same way, since they all follow a common interface.

Use the pattern when it’s awkward or not possible to extend an object’s behavior using inheritance.

Many programming languages have the `final` keyword that can be used to prevent further extension of a class. For a final class, the only way to reuse the existing behavior would be to wrap the class with your own wrapper, using the Decorator pattern.


----

الديكوراتور معناه زينه او ديكور
بنستخدمه لاضافه او تزيين اوبجكت 
الزينه هنا بتكون فيتشر جديده علي الاوبجكت الاساسي الي معانا

وبرضو بنسميه wrapper 
يعني غلاف 
بنغلف الاوبجكت بتاعنا بغلاف بيضيف فيتشر جديده 

يعني كل decorator class هو عباره عن الاوبحكت الاساسي بتاعنا الmain component + خاصيه جديده بيضيفها الديكوراتور ده 
كل decorator class يعتبر component منفصل عن الbase وبنضيفه عليه (وبرضو هو من نفس النوع بتاع الbase)
كده نقدر نضيف behaviors dynamically at run time بدل من اني استخدم ال static inheritance 
الinheritance يعتبر static لانه بعمل parent class وتحته كل ال combinations المختلفه للابناء وكل ما احتاج اضافه جديده لازم اعمل كلاس جديد 
ولو عايز اعمل كلاس فيه اتنين فيتشرز مع بعض من الي عندنا
لازم اعمل كلاس جديد feature1+feature2 

فالاول بنعمل الانترفيس بتاعتنا الي هيكون فيها الbasic behaviors
وبيكون عندنا كلاسين تحتها 
اول كلاس هو ال basic component بتاعنا الي هنستخدمه علشان نضيف عليه components جديده ونزينه*
تاني كلاس هو ابستراكت كلاس وهيكون decorator class بيكون فيه نفس ال behaviors بتاعت ال basic component class 

اي اضافات عايزين نضيفها علي ال basic component هنمثلها بكلاس تحت الdecorator يعني هيورثو منه 
كده اي اضافه هتكون علي الdecorator وليست علي الbasic class 
يبقا كده عرفت احمي الاوبجكت بتاع ال basic من اي اضافات وحققت ال OCP 

الdecorator بيطبق ال composition جواه ب انه ياخد اوبجكت من الbasic class (الي عايزين نضيف عليه)
ونعمله inject فالكونستراكتور بنوع الinterface الكبيره 

![[Pasted image 20250106205409.png]]
![[Pasted image 20250106205415.png]]![[Pasted image 20250106205424.png]]

الdecorator هو identical لل basic component

