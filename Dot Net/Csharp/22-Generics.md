_**Generic**_ is a class which allows the user to define classes and methods with the placeholder. Generics were added to version 2.0 of the C# language. The basic idea behind using Generic is to allow type (Integer, String, … etc and user-defined types) to be a parameter to methods, classes, and interfaces. A primary limitation of collections is the absence of effective type checking. This means that you can put any object in a collection because all classes in the C# programming language extend from the object base class. This compromises type safety and contradicts the basic definition of C# as a type-safe language. In addition, using collections involves a significant performance overhead in the form of implicit and explicit type casting that is required to add or retrieve objects from a collection. To address the type safety issue, the [**.NET**](https://www.geeksforgeeks.org/c-net-framework-basic-architecture-component-stack/) framework provides generics to create classes, structures, interfaces, and methods that have placeholders for the types they use. Generics are commonly used to create type-safe collections for both reference and value types. The [**.NET**](https://www.geeksforgeeks.org/c-net-framework-basic-architecture-component-stack/) framework provides an extensive set of interfaces and classes in the System.Collections.Generic namespace for implementing generic collections.

هي فيتشر اتضافت من اول سي شارب 2

فالاول كان عندنا مشكله ان الكوليكشنز كانت بتقبل اي نوع يعني اوبجكتس بما انها الbase class ليهم كلهم 
كانت بتسبب مشكله لانها تعتبر not type safe 
وبتاثر فالبيرفورمنس لانها بتحتاج تعمل type casting(boxing&unboxing) لما اضيف او اشيل من الكوليكشنز 

فجات الgenerics حلت المشكله دي 
وعملو generic collections علشان تكون type safe
يعني بنحددلها التايب قبل ما نشتغل عليها 


Generics in C# is its most powerful feature. It allows you to define the type-safe data structures. This out-turn in a remarkable performance boost and high-grade code, because it helps to reuse data processing algorithms without replicating type-specific code. Generics are similar to templates in C++ but are different in implementation and capabilities. Generics introduces the concept of type parameters, because of which it is possible to create methods and classes that defers the framing of data type until the class or method is declared and is instantiated by client code. Generic types perform better than normal system types because they reduce the need for boxing, unboxing, and type casting the variables or objects. Parameter types are specified in generic class creation.

نقدر نعمل generic class , method , interface , delegate ....

بنحدد التايب في < > بعد اسم الكلاس او الميثود 
وبنعتبره داتا تايب جوه الكلاس 
بحيث ان لما اخد منه اوبجكت بباصيله التايب ده 
فبيروح جوه الكلاس يستخدم التايب ده كداتا تايب ليه
وبالتالي انا الي حددت الداتا تايب

ومع كل اوبجكت اخده اقدر اباصي داتا تايب مختلف بنفس الكود الي اتكتب للكلاس
بدلا من اننا نعمل كود جديد لكل داتا تايب

```C#
// C# program to show working of 
// user defined Generic classes
using System;

// We use < > to specify Parameter type
public class GFG<T> {
	
	// private data members
	private T data;
	
	// using properties
	public T value
	{
		
		// using accessors
		get
		{
			return this.data;
		}
		set
		{
			this.data = value;
		}
	}
}

// Driver class
class Test {
	
	// Main method
	static void Main(string[] args)
	{
		
		// instance of string type
		GFG<string> name = new GFG<string>();
		name.value = "GeeksforGeeks";
		
		// instance of float type
		GFG<float> version = new GFG<float>();
		version.value = 5.0F;
		
		// display GeeksforGeeks
		Console.WriteLine(name.value); 
		
		// display 5
		Console.WriteLine(version.value); 
	}
}

```
حطينا البرامتر T بعد اسم الكلاس (حرف شائع بيدل علي type)
ولما عملنا field جوه الكلاس عملناه من النوع T الي لسه هنباصيه
ف لو اخدنا اوبجكت من الكلاس وقولنا انه int ف الfield ده هيكون int 

```C#
// C# program to show multiple
// type parameters in Generics
using System;

public class GFG {
	
	// Generics method
	public void Display<TypeOfValue>(string msg, TypeOfValue value)
	{
		Console.WriteLine("{0}:{1}", msg, value);
	}
}

// Driver class
public class Example {
	
	// Main Method
	public static int Main()
	{
		
		// creating object of class GFG
		GFG p = new GFG();
		
		// calling Generics method
		p.Display<int>("Integer", 122);
		p.Display<char>("Character", 'H');
		p.Display<double>("Decimal", 255.67);
		return 0;
	}
}

```
ممكن نعمل generic method 
حطينا التايب بعد اسم الميثود 
والميثود هتاخد التايب الي اتحدد ده