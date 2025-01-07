**Command** is a behavioral design pattern that turns a request into a stand-alone object that contains all information about the request. This transformation lets you pass requests as a method arguments, delay or queue a request’s execution, and support undoable operations.

هو behavioral pattern 
ليه 4 مكونات 
الاول هو receiver وبيكون جواه مجموعه ميثودوز (commands) عايزين نناديها 
وهنبعتله الكوماند ده (بيكون باسم الفانكشن الي جوه) علشان ينفذها

التاني هو ال command class or classes فيه كلاس او مجموعه كلاسات بتعبر عن الكوماندز دي 

التالت هو ال invoker زي الريموت كونترول هو الي هيستخدم ال command علي ال receiver 

الرابع هو executer او main class  هو الشخص الي بيمسك ال invoker (remote) 

