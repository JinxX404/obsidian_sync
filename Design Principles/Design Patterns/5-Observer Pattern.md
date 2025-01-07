هو behavioral design pattern بيركز علي العلاقة والcommunication بين الاوبجكتس 
بيكون فيه subject بيحصل فيه تغييرات 
والتغييرات دي لازم يعرف بيها او يسمع عنها اوبجكتس تانيه (يحصلها notify)
هي دي فكرة ال observer pattern 

مثلا فيه online marketplace بيتضاف فيه منتجات او خصومات 
عايزين كل ما يتضاف حاجه جديده نروح نبعت notification لليوزر الي مهتمين 

او فيه newsletter في الblogs مثلا 
وبيكون فيه users مهتمين بنوع معين 
بنكون عايزين نعملهم notify ان فيه حاجه جديده نزلت

او subscribers اليوتيوب 
بيتعملهم notification لما فيديو جديد ينزل في قناه معينه 


الي هيغير فالstate بتاعته هيكون اسمه subject or publisher
والي هيستني نوتيفكشن اسمه observer او subscriber 

![[solution1-en-2x.png]]

الpublisher هيكون شايل مجموعة ال subscribers الي مهتمين يحصلهم notify 
وشويه ميثودز بتشتغل علي ال subscribers دول 

لما يحصل ايفينت معين عند الpublisher هو بيروح ينادي ميثود معينه عند الobservers تخليه يعمل notify 

![[Pasted image 20250107173238.png]]

![[Pasted image 20250107180902.png]]

ال Subscriber interface هيكون تحتها كل ال subscribers بتوعنا هنسميهم concrete subscribers
كل سببسكرايبر منهم هيoverride الفانكشن بالطريقه بتاعته (ممكن يكون اكشن هيعمله بعد ما يجيله نوتيفيكيشن معين) 

ال publisher بيكون عنده list من ال subscribers الي مهتمين في ايفينت معين
ولما الايفينت يحصل بنعملهم notify ب اننا ننادي الفانكشن بتاعتهم الي موجوده فالSubscriber interface 

---

Use the Observer pattern when changes to the state of one object may require changing other objects, and the actual set of objects is unknown beforehand or changes dynamically.

You can often experience this problem when working with classes of the graphical user interface. For example, you created custom button classes, and you want to let the clients hook some custom code to your buttons so that it fires whenever a user presses a button.

The Observer pattern lets any object that implements the subscriber interface subscribe for event notifications in publisher objects. You can add the subscription mechanism to your buttons, letting the clients hook up their custom code via custom subscriber classes.

Use the pattern when some objects in your app must observe others, but only for a limited time or in specific cases.

The subscription list is dynamic, so subscribers can join or leave the list whenever they need to.

---
