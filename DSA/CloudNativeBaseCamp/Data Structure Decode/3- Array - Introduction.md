
لما بعمل اراي 
بحددلها السايز بتاعها والداتا تايب علشان بيحجز الاماكن ورا بعض فالميموري حسب الداتا تايب بيحتاج كام بايت 
![[Pasted image 20240731143807.png]]
يعني هنا الint هيكون 32 بت يعني 4 بايت , يعني كل عنصر هيتمثل في 4 blocks فالميموري

احتجت 3 اماكن ل3 عناصر 
وكل عنصر بيتمثل في 4 اماكن يعني 12 بلوك 


![[Pasted image 20240731144010.png]]

الريفرنس بتاع الاراي هيكون هو اول ادريس 0x5040E8
وباقي العناصر بنوصلهم بمعادلة 
اول عنصر هيساوي الarray base add يعني ده اول حاجه محجوزه فالميموري للاراي

تاني عنصر في اندكس 1 هنجيبه من المعادله 
Array Base Add + (Single Value Stores Count * Index)

ال single value stores count بتعبر عن طول التايب 
يعني الint هيكون 32 بت يعني 4 اماكن فالميموري
تبقي الفاريبل ده هنعوضه ب4

لو عايزين عنوان العنصر الي في اندكس 1 
هنحطه فالمعادله 
هنحول 0x5040E8 لديسمل 5259496 
add of data at index 1 = 5259496 + (4 * 1) = 5259500 = 0x5040EC
يبقي الناتج ده هو عنوان الاندكس الاول

كل مره بحرك نفسي عن عنوان اول عنصر حسب كل عنصر بيتخزن فكام بايت
المعادلة هتنفع مع الzero based
لو هيبدا من 1 ف بنعدل فالمعادله ونطرح من 1 

كل لغه حسب الديزاين بتاعها 

----
مفيش حاجه اسمها Dynamic array 
هي الاراي يعني اراي 
بتحجز مجموعه عناصر ورا بعض

لاكن الdynamic array بتشتغل علي الاراي برضو 
لاكن حسب لغة البرمجه 
بتعدل علي سايز الاراي كل مره 
بتاخد الاراي القديمه وتنسخها فمكان جديد بيشيل الحجم المناسب 

لاكن مفيش dynamic arr زي ما احنا عايزينها تكون dynamic

----

### Array Types

![[Pasted image 20240731145549.png]]
وعندنا رابع اسمه jagged array 

الregular دي الي بنستخدمها دايما

ال2d عباره عن مجموعه صفوف واعمده 

ال3d تعتبر مجموعه 2d ورا بعض
كل مجموعه تعتبر page 
يعني هي متكونه من 3 من 2d arr ورا بعض وكل واحده اسمها page

الانواع دول هيتصنفو تحت Multidimensional Array ولازم يكون عدد الصفوف والاعمده نفس الطول 
وممكن نلاقي 4d,5d ... حسب اللغه

![[Pasted image 20240731145958.png]]
ال2d عدد العناصر هيكون num of col * num of rows 
وكل عنصر هيشاور عليه اتنين اندكس 

بنخزنهم ازاي فالميموري؟
بناخد كل row بنفرده فالميموري وبعده الrow التاني وهكذا


![[Pasted image 20240731150238.png]]
في ال3d عندنا بعد تالت اسمه page 

بنمسك كل page نفرده فالميموري كانه 2d arr 
وبعده الpage التانيه وهكذا

مسكنا الpage الي ناحيتنا (الي شايفينها)
كانها 2d وفردناها 
وبعده الpage التانيه


![[Pasted image 20240731151532.png]]
الJagged Array هو يعتبر Array of Arrays
بنحدد طول الاراي الاب  (عايز جواه كام arr)
وهيكون جواه عدد arrays بس لسه معرفش طولهم كام 
عكس الMulti dim بيكون كلهم نفس الطول

![[Pasted image 20240731151722.png]]
هحتاج stack , heap (حسب اللغه , ممكن الاراي كلها فالهيب او كلها فالاستاك او جزء وجزء)

السي شارب هتحجز فالاستاك عدد بلوك حسب عدد الارايز الي عايزاه جواها
وهتشيل جواهم add لكل array من الي جواها 
والarray الي جواها هتتخزن فالهيب





---------
-----
----

![[Pasted image 20240731152118.png]]
يعني ايه داتا ستراكشر؟؟ 
بتتكون من حاجتين 
ال infrastructure وهي مجموعه address فالميموري ممكن يكونو متصلين او منفصلين حسب نوع الداتا ستراكشر 
والمكون التاني هو الoperations وهو الي بيحدد الفرق ما بين داتا ستراكشر والتاني

حسب الoperations المختلفه الي بعملها علي الinfrastructures بتبني characteristics لكل داتا ستراكشر 

![[Pasted image 20240731152355.png]]
الاراي هتكون الinfra بتاعتها مجموعه متصله من الmemory units 

الoperations ممكن نقسمها اتنين 
الاولي static ودي مش هتاثر علي الinfrastructure 
يعني هعمل traverse او هجيب او هحط عنصر مكان عنصر موجود 
يبقي انا كده مغيرتش في الinfra نفسها 
يعني مزودتش او قللت مكان 

الdynamic يعني حاجه بتاثر علي الinfra 
يعني ممكن ازود او اقلل طولها 
او هننقلها فمكان تاني لو هنعمل resize


![[Pasted image 20240731152915.png]]
الinfra هي تخص الكومبايلر
بنطلب منه يحجز كذا او يعمل كذا عالميموري وبيكون بينا وبينها الاف الاسطر من الاكواد علشان تعمل كده (سواء فلغه البرمجه , كومبايلر , CPU)
لاكن منقدرش نقرب منها

جزء الoperations ميعتبرش مسئوليتنا كامله 
لاكن نقدر نشتغل عليه 
كل داتا ستراكشر بيكون فيه operations جاي بيها
لاكن احنا نقدر نضيف حاجات تخصنا , ممكن ازود operations جديده 


