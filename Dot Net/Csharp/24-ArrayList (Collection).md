weak typed collection
اي كلاس ب implement انترفيس زي iCollection او iEnumerable يعني نقدر نعمل عليها لووب (زي الاراي ليست والاراي والليست)

داتا ستراكشر دايناميك اراي 
يعتبر array of objects
كل عنصر جواه اوبجكت
ف يقدر يشيل اي نوع نضيفه ليه (علي عكس الاراي بيشيل نوع واحد)
لان الاوبجكت هو الparent بتاع كل الداتا تايب ف هو يقدر يشيل كل الانواع
ولما بنضيف عنصر بيطبق الboxing ف انه يحول الvalue type ل ref type اوبجكت ويضيفه

لو ضفنا int ف هو هيحولهم اوبجكتس
لو رجعنا نلووب عليهم تاني هيكونو لسه اوبجكتس (لو عايزين ندخلهم فعمليات حسابيه مش هنعرف) 
ف هنعمل unboxing (explicit casting)


**ArrayList** represents an ordered collection of an object that can be indexed individually. It is basically an alternative to an array. It also allows dynamic memory allocation, adding, searching and sorting items in the list.

**Properties of ArrayList Class:**

- Elements can be added or removed from the Array List collection at any point in time.
- The ArrayList is not guaranteed to be sorted.
- The capacity of an ArrayList is the number of elements the ArrayList can hold.
- Elements in this collection can be accessed using an integer index. Indexes in this collection are zero-based.
- It also allows duplicate elements.
- Using multidimensional arrays as elements in an ArrayList collection is not supported.

![[Pasted image 20240730204720.png]]