زي الmulti dim array

لاكن احسن كبيرفورمنس

تعتبر ارايز داخل اراي واحده

ومش لازم يكونو كلهم نفس الطول

  

```C#
//var jagged = new int [] [] {};  
int[][] jagged = new int[][] 
{ new int[] {4,5,6,7},
  new int[] {3,2,1},
  new int[] {10}
};
```
مش لازم يكونو نفس الطول وكده هنوفر عن المالتي اراي لانه لازم كل الصفوف يكونو نفس الطول


ممكن استخدم var في الارايز
لاكن لازم اكون محدد النوع بتاع الاراي باستخدام new

```C#
int[][] jaggedArray = new int[][] { new int[]{1,2}, new int[]{1} };  
  
Console.WriteLine(jaggedArray[0][0]); // first arr first element  
Console.WriteLine(jaggedArray[0][1]); // first arr second element  
Console.WriteLine(jaggedArray[1][0]); // second arr first element
```


---

A jagged array, also known as an "array of arrays," is a multi-dimensional array in C# where each element of the array is itself an array. Unlike a multidimensional array, jagged arrays have variable-length arrays as their elements, which can have different lengths. This flexibility allows jagged arrays to represent irregular data structures more efficiently.

```C#
// Declare a jagged array of integers
int[][] jaggedArray = new int[3][];

// Initialize the inner arrays with different lengths
jaggedArray[0] = new int[] { 1, 2, 3 };
jaggedArray[1] = new int[] { 4, 5, 6, 7 };
jaggedArray[2] = new int[] { 8, 9 };

// Accessing elements
int element = jaggedArray[1][2]; // Accesses the element at row 1, column 2 (6)
```

- We declare a jagged array `jaggedArray` with three rows. However, we do not specify the length of the inner arrays (columns) at this point.
- We initialize each row with its own array of integers, and each of these inner arrays can have a different length. This allows for irregular structures where different rows can have different numbers of columns.
- You can access elements of the jagged array using two sets of square brackets. The first set of brackets specifies the row index, and the second set specifies the column index within that row.

Jagged arrays are useful when you need to work with data structures that have varying lengths for different elements or when you want to allocate memory dynamically for each element in the array. They are often used in scenarios where you need more flexibility than a regular rectangular (multidimensional) array can provide.