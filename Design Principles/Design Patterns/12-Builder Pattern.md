**Builder** is a creational design pattern that lets you construct complex objects step by step. The pattern allows you to produce different types and representations of an object using the same construction code.

![[Pasted image 20250109203622.png]]

لما بيكون عندي كونستراكتور كبير ومش محتاج منه كل البرامترز ف بحطهم null وكده بعمل ugly constructor وده الي عايزين نتجنبه

هننقل الكونستراكشن في كلاس جديد اسمه builder 
بيكون كل الكونفجريشن بره الكلاس وبختار بس الproperites الي عايزها للاوبجكت بتاعي 
والباقي بيتحط بالديفولت بتاعه
