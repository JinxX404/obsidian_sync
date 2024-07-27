classes are entities that solve a single problem of perform a specific job or role
الكلاس يعتبر حاجه بتعمل وظيفة معينه (من خصائص الsingle responsibility principle ان الكلاس ميعملش غير وظيفة واحده وكل الي جواه يخدم علي الحاجه دي)

مثلا وظيفة الConsole class انه interact with the console window 
بستخدمه في اني اقرا واكتب (يبقي كل الميثودز الي جواه بتساعدني استخدم الخدمة الي بيقدمها)

classes are primarily composed of two things :
	1- the data they need to do their job.
	2- tasks they can perform.



**All methods live in container like a class**
**most classes lives in container called a namespace**
يبقي namespace هو كونتينر بيشيل جواه كلاسات (مرتبطه ببعض نوعا ما او بتخدم علي حاجه معينه)

**Namespace is purely code organization tool , they are valuable when dealing with hundreds or thousands of classes**



مثلا كلاس console موجود جوه System Namespace 

فالاول كنت محتاج استخدم using keyword علشان احدد للكومبايلر انه يستخدم الnamesapce دي علشان يلاقي فيها الكلاسات الي انا مستخدمها فالكود 

لاكن مع C# 10 مش محتاج احددله الnamespace 
الكومبايلر هيروح يسيرش في   System and a handful of other extremely common namespaces without you needing to call it out



----
