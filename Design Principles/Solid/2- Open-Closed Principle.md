سهل اني ازود عليها من غير ما اغير فيها

![[Pasted image 20240623220007.png]]


 “***Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification****”

which means you should be able to extend a class behavior, without modifying it.



معناها انه السوفتوير انتتي ده اقدر اضيف عليه بدون ما احتاج اعدل علي حاجه تاني فالسيستم 
يعني ينفع أاextend السيستم لاكن مينفعش اعدل علي الموجود 
(الاضافه بتاعتي متجبرنيش اعدل علي الكود الموجود)


> Imagine you have a class called `PaymentProcessor` that processes payments for an online store. Initially, the `PaymentProcessor` class only supports processing payments using credit cards. However, you want to extend its functionality to also support processing payments using PayPal.

Instead of modifying the existing `PaymentProcessor` class to add PayPal support, you can create a new class called `PayPalPaymentProcessor` that extends the `PaymentProcessor` class. This way, the `PaymentProcessor` class remains closed for modification but open for extension, adhering to the Open-Closed Principle

---
If you want the Class to perform more functions, the ideal approach is to add to the functions that already exist NOT change them.

**Goal**
This principle aims to extend a Class’s behaviour without changing the existing behaviour of that Class. This is to avoid causing bugs wherever the Class is being used.