---
aliases:
  - 4- Interface Segregation Principle
---
ISP splits interfaces that are very large into smaller and more specific ones so that client will only have to know about the methods that are of interest to them
بنقسم الانترفيس الكبيره لانترفيسيس اصغر بحيث تكون كل واحده مخصصه ومحدده

![[Pasted image 20241031213903.png]]
الworker حطينا فيه eat , work 
لاكن لو معانا روبوت وعايزينه يامبلمينت worker
الروبوت مش بياكل 

الحل اننا نفصل الميثود بتاعت work عن eat 
في اتنين انترفيس 
والي هيحتاج اي واحده منهم يعمل امبلمينت 

![[Pasted image 20241031214049.png]]

