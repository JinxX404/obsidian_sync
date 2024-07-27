زي الجافا بالظبط

بحددلها الداتا تايب والطول 
او الداتا تايب والعناصر الي جواها 

``` Csharp
int[] oneDimArr = { }; // length = 0  
int[] oneDimArr2 = {1, 2, 3, 4}; // length = 4  
int[] oneDimArr3 = new int[] { 1, 2, 3, 4 }; // same as previous one  
int[] oneDimArr4 = new int[5]; // initialize arr of len 5 , all zeros
```

الاولي بحط فيها العناصر علطول وهتكون فاضيه 
او هعمل زي التالته هستخدم الnew keyword واديلها العناصر
او new واديلها الطول وهتملاها اصفار 

لازم تاخد size عند الintialization


---
ممكن استخدم var مكان int 
لاكن مش هينفع في الاولي والتانيه 
لاني لازم احدد الداتا تايب بتاعتنا 
ف هتنفع فالتالته والرابعه
```C#
var oneDimArr5 = new int[] { 1, 2, 3, 4 };
var oneDimArr6 = new int[5]; // initialize arr of len 5 , all zeros
```


لاكن دول ايرور 
```C#
var oneDimArr7 = { }; // length = 0  
var oneDimArr8 = {1, 2, 3, 4}; // length = 4
```
لازم احدد الداتا تايب الي هترجع علشان var يعرفها 




-----
لو عملت كده 
```C#
int[] originalArr = { 1, 2, 3, 4, 5 };  
int[] copiedArr = originalArr;
```
يعني خزنت ريفرنس الاراي الاولي جوه التانيه 
يعني الاتنين بيشاورو علي نفس المكان فالميموري

لو بعدهم عدلت علي الاوريجنال وطبعت الكوبي هلاقي الكوبي برضو متعدله