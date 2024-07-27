دي ال2d array تعتبر اراي جوه اراي ولازم كل الاراي الي جوه يكونو نفس الطول


```C#
int[,] matrix = new int[3, 3]; // A 3x3 2D array
```

```C#
int[,] arr = { {1,2,3,4}, {4,5,6,7}, {8,9,10,11}};
var twoDimArr2 = new int[,] {{1, 2 ,3} , {1 , 2 , 3},{1 , 1 , 1}};
```


```C#
int[,] twoDimArr = { {1, 2 ,3} , {1 , 2 , 3},{1 , 1 , 1}};  
Console.WriteLine(twoDimArr.Length); // len = 9
```

```C#
for (int i = 0; i < 3; i++)  
{  
    for (int j = 0; j < 3; j++)  
    {     Console.Write(twoDimArr[i,j]);     
    }  
    Console.WriteLine();  
}
```

كده اقدر اترافيرس علي العناصر
كل مره اقدر اaccess الاراي باتنين برامتر 
الاول للrow والتاني للcolumn

