 الموديفايرز بتطبق علي كل الانواع class , enum , interface , property .....
 ممكن يكون فيه استثناءات لكل واحده فيهم ويستخدم بطريقه مختلفه


### Private
**Members with this modifier are only accessible within the same class or struct.**
"منقدرش نعمل كلاس برايفت غير لما يكون nested class"

### Public
Members (classes, methods, fields, etc.) with this modifier are accessible from any code within the same assembly or from other assemblies.

من اي مكان من اي حته نقدر نشوفه

### Internal 
**Internal Member Is public Within the Assembly**

**Members are accessible within the same assembly. This is similar to package-private in Java.**

بيكون ديفولت لو محطيناش اي موديفاير غيره

زي الجافا بيكون نقدر نشوفه جوه نفس الباكدج بتاعتنا بس منقدرش نشوفه بره

---

الكلاس او الميثود الي بتكون انترنال بتكون تعتبر بابلك بداخل الاسيمبلي بتاعها (البروجكت الي هيا فيه ,الاسيمبلي جزء من السوليوشن يعني السوليوشن ممكن نحط فيه اكتر من بروجكت والبروجكت هنا نقدر نسميه اسيمبلي)

**لاكن الموديفاير البابلك هو يقدر يتشاف من اي حد جوه السوليوشن بكل الاسيمبلي بتوعه (محتاجين بس نعمل ايمبورت للنيمسبيس بتاعته)**


----
بيتشاف جوه نفس البروجكت فقط (بغض النظر عن الnamespace)