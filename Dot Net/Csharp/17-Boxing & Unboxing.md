البوكسينج هي عمليه تحويل value type

ألي reference type

مثلا هحط int > obj

دي هتحصل implicit

لان الاوبجكت الاب وتقدر تشيل اي حاجه

---

انبوكسينج هي تحويل الريفرنس لفاليو تايب

ودي لازم نعملها صراحةexplicit

لان من اوبجكت لداتا تايب فاليو ممكن تحصل فقد

```C#
int y = 5;
object obj=y;//procces to put value type in reference type is implicit process and called boxing
int x = (int)obj;//explicit, unboxing
```