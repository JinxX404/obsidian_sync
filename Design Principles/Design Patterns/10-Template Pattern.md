**Template Method** is a behavioral design pattern that defines the skeleton of an algorithm in the superclass but lets subclasses override specific steps of the algorithm without changing its structure.

هو behavioral pattern 

لما يكون عندي كلاس جواه الجوريزم معين مجموعة خطوات لانشاء بيتزا مثلا
جواه شويه ميثودز وفيه ميثود بتناديهم علشان تmake pizza
لو عايزين نعمل نوع بيتزا منهم بطريقه مختلفه (لاكن فيه خطوات متشابهة بين الاتنين)
يعني عندي تشابه فالالجوريزم لاكن فيه ميثود فيهم بتتعمل بطريقه مختلفه

الحل الاول اني اعمل كلاسين مختلفين للنوعين بتوع البيتزا وكل واحد يطبق اللوجيك بتاعه 
لاكن العيب فالحل ده انه فيه تكرار فالكود 
لانه فيه خطوات متشابهة كررتها فالكلاسين

الحل التاني هو ال template pattern 
بعمل abstract class فيه الخطوات بتاعت الالجوريزم 
والميثود الي بيكون فيها اختلاف بين الانواع المختلفه 
بعملها abstract واسيبها للانواع المختلفه هي الي تطبق اللوجيك بتاعها 

