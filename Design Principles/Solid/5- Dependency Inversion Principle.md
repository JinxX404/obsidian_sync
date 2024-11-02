---
aliases:
  - 5- Dependency Inversion Principle
---
* High-level modules should not depend on low-level modules. Both depend on abstractions.
يعني لازم الكلاس الhigh level ميعتمدش علي low level 
كلاس الhigh هو الي هيعمل كرييت لاوبجكت جواه 
الاوبجكت الي جوه ده بيكون من الlow level 

الهدف اننا منعملش الحته دي يعني مناخدش اوبجكت جوه الكلاس 
ونطبق الinversion يعني هنعكس الاعتماديه 
بدل من انهم يعتمدو علي بعض
هنخليهم هما الاتنين يعتمدو علي abstraction 

*  Abstraction should not depend on details. Details (concrete class (basic known class)) should depend on abstractions.

![[Pasted image 20241031232409.png]]
اليمين فيه الhigh level module الي هو OrderManagmentServices بيعتمد علي ال low level الي هو OrderDatabase 
وده بيكسر مبدا ال dependency inversion 

الشمال بيطبق المبدا
عمل طبقه ابستراكشن بين ال2 classes 
وبقيو هما بيعتمدو علي ال abstraction 
يعني عملنا عكس للاعتماديه (dependency inversion)
والاتنين دول هيعملو امبلمينت للانترفيس

