**Prototype** is a creational design pattern that lets you copy existing objects without making your code dependent on their classes.


هو creational pattern 

لو معايا اوبجكت معين ليه خصائص
وعايز اعمل clone ليه بنسخة طبق الاصل 

عندي طريقه اني اعمل اوبجكت جديد واحط جواه نفس الخصائص بتاعت الاوبجكت الي عايزين ننسخه ب اني انادي الget وااعملها set فالتاني
لاكن الطريقه دي مش هتنفع لو عندي برايفت اتريبيوت ملهاش set/get 

ف كده محتاجين طريقه ننسخ بيها من جوه الاوبجكت نفسه
يعني عايزين ميثود clone جوه الكلاس الي عايزين نclone منه 
وترجعلي هي اوبجكت من نفس النوع فيه كل الخصائص بالظبط


![[Pasted image 20250108213625.png]]

###### Pros and Cons

pros:
- You can clone objects without coupling to their concrete classes.
- You can get rid of repeated initialization code in favor of cloning pre-built prototypes.
- You can produce complex objects more conveniently.
- You get an alternative to inheritance when dealing with configuration presets for complex objects.

cons:
- Cloning complex objects that have circular references might be very tricky.