* If S is a subtype of T, then objects of type T in a program may be replaced with objects with type S without altering any of the desirable properties of that program. 
* If the father is not found that the son can take the place of the father and perform the same action of the father.

لو معايا base class وليه كذا child class
الprinciple بيقول انه لازم لو شيلت الbase وحطيت مكانه اي واحد من الchilds بتوعه 
اكون متوقع الاوتبوت بتاعهم وميحصلش اي behavior غريب

![[Pasted image 20241031204749.png]]
هنا ال bird فيه اتنين فانكشن layEggs و fly 
وعندي child class اسمه penguin 
كده الchild اخد خصائص الbird الي هي fly , layEggs بس هو كده مش بيطير ف كده الابن ميقدرش يحل محل الاب 
فهنفصل اللوجيك بتاع الfly بره الbird 
والchild الي هيكون فيه fly بس هو الي هيعمل منه implement 
علشان يكون كل الي فالbird فالابناء والعكس واقدر استخدم الابن مكان الاب 

هعمل انترفيس flyable واحط فيها فيتشر الfly وهخلي الي بيطير بس هو الي يورث منها 
