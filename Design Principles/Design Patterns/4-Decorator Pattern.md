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

