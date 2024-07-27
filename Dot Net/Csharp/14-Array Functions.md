عندنا كلاس Array جواه كام فانكشن مفيده 
زي sort 
بتاخد الاراي الي هترتبها

``` C#
int[] nonSorted = new[] {5 , 0 , 1 , 3 };  
Array.Sort(nonSorted);  
foreach (var VARIABLE in nonSorted)  
{  
    Console.WriteLine(VARIABLE); // 0 1 3 5  
}
```
----

او copy 
بتاخد  3 برامتر 
الاول هو الاراي الاصليه الي عايز انسخها فمكان تاني
التاني هو الاراي الي هنسخ جواها العناصر
التالت هو الlength
 لو عايز انسخ الاراي كلها هستخدم طول الاراي كبرامتر 

```c#
int[] originalArr = { 1, 2, 3, 4, 5 };  
int[] copiedArr = new int[5];  
  
Array.Copy(originalArr,copiedArr,originalArr.Length);
```
لازم يكون اللينث الي هحطه يكون نفس طول الdestination array او اقصر منه
لو طول الdes , original مش بيساوو بعض هيطلع ايرور

لو عملت الكوبي اراي طولها 5 يعني 5 عناصر كلهم اصفار كقيمه ابتدائيه
وعملت برامتر الlength مثلا 3 
يعني هاخد اول 3 عناصر من الoriginal وهحطهم في اول 3 اماكن في الcopied وهيكون باقيها اصفار



---
عندي فانكشن reverse 
بتاخد الاراي وتعكسها

---
