![[Pasted image 20240623215936.png]]
This principle states that “****A class should have only one reason to change****” which means every class should have a single responsibility or single job or single purpose. In other words, a class should have only one job or purpose within the software system.

Let’s understand Single Responsibility Principle using an example:

> Imagine a baker who is responsible for baking bread. The baker’s role is to focus on the task of baking bread, ensuring that the bread is of high quality, properly baked, and meets the bakery’s standards.

- However, if the baker is also responsible for managing the inventory, ordering supplies, serving customers, and cleaning the bakery, this would violate the SRP.
- Each of these tasks represents a separate responsibility, and by combining them, the baker’s focus and effectiveness in baking bread could be compromised.
- To adhere to the SRP, the bakery could assign different roles to different individuals or teams. For example, there could be a separate person or team responsible for managing the inventory, another for ordering supplies, another for serving customers, and another for cleaning the bakery.

اول مبدا 
هو انه لازم الكلاس يكون ليه غرض واحد بيعمله 
وكل الميثودز الي جواه بتخدم عالغرض ده يعني ما بينهم high coherince

***A Class should only have one responsibility. Furthermore
it should only have one reason to change***
لازم الكلاس يعمل وظيفة واحدة بس 
ويكون فيه سبب واحد بس لتغييره (يعني بيعمل حاجه واحده فهيكون سبب واحد علشان اغير في وظيفة الحاجه دي)
لو بيعمل اكتر من حاجه , فهيكون عندي اكتر من سبب يخليني اغير فالكلاس ده

مش مهم عدد الميثودز الي جوه الكلاس طلاما بيخدمو نفس الغرض
لاكن لو فيه ميثودز متخصش الكلاس ده هنفصلها فكلاس تاني خاص بيها

advantages 
	lower coupling
	easier to test
	organized
	easier to understand
لما يكون الكلاس ليه وظيفة واحده بس كده سهل عندي اني اتيست وهيكون كله يخص لوجيك واحد علشان يحقق حاجه معينه 
يعني كل الميثودز بيخدمو الفكره دي



