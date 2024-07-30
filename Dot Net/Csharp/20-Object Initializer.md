> [!info] Object and Collection Initializer in C# - GeeksforGeeks  
> A Computer Science portal for geeks.  
> [https://www.geeksforgeeks.org/object-and-collection-initializer-in-c-sharp/](https://www.geeksforgeeks.org/object-and-collection-initializer-in-c-sharp/)  

In object initializer, you can initialize the value to the fields or properties of a class at the time of creating an object without calling a [constructor](https://www.geeksforgeeks.org/c-sharp-constructors/)

بيسمحلي ادي قيم ابتدائيه للفيلد بتاعتي من غير ما استخدم الكونستراكتور ولحظه ما بعمل الاوبجكت بقدر اديله القيم

  

```C#
Type instance = new Type
{
    Property1 = value1,
    Property2 = value2,
    // ...
};
```

```C#
public class Person
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
}

// Create and initialize a Person object using an object initializer
Person person = new Person
{
    FirstName = "John",
    LastName = "Doe"
};
```

Object initializers are particularly useful when you need to create objects with a significant number of properties or fields that need to be set to specific values, as they help improve code readability and reduce the number of lines of code required.



```C#
// C# program to illustrate
// object initializer syntax
using System;

class Geeks {

	public string author_name
	{
		get;
		set;
	}
	public int author_id
	{
		get;
		set;
	}
	public int total_article
	{
		get;
		set;
	}
}

class GFG {

	// Main method
	static public void Main()
	{

		// Initialize fields using 
		// an object initializer
		Geeks obj = new Geeks() {
			author_name = "Ankita Saini",
			author_id = 102,
			total_article = 178};
		
		Console.WriteLine("Author Name: {0}", obj.author_name);

		Console.WriteLine("Author Id: {0}", obj.author_id);

		Console.WriteLine("Total no of articles: {0}",
								obj.total_article);
	}
}

```

