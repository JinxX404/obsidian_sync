في الداتابيز عندنا sql بنعمل بيها queries علي الداتابيز علشان نرجع داتا معينه عايزينها

في السي شارب 
عندنا كونتينرز من الداتا (شبه جداول الداتابيز الي هنشتغل عليها sql)
الكونتينيرز دي اي حد عامل امبلمينت ل enumerable 
زي الاراي والليست والديكشنري ......

هنحتاج لغه شبه الsql نرجع بيها داتا من الكونتينرز دي 
هي الlinq

ليها اتنين syntax 
منهم واحد more readable بس مش هنعرف نعمل بيه كل حاجه وبرضو هو في الcompile هيتحول للشكل التاني 

الشكل التاني بنستخدم معاه lambda , delegates ..... وبقوله datasource.where() وبديله الشرط 

نسبه كبيره من الCases الي نعملها بlinq نقدر نعملها بالloops
بس الlinq بتكون فاسطر اقل 


Language-Integrated Query (LINQ) is a powerful set of technologies based on the integration of query capabilities directly into the C# language. LINQ Queries are the first-class language construct in C# .NET, just like classes, methods, events. The LINQ provides a consistent query experience to query objects (LINQ to Objects), relational databases (LINQ to SQL), and XML (LINQ to XML).

LINQ (Language Integrated Query) is uniform query syntax in C# and VB.NET to retrieve data from different sources and formats. It is integrated in C# or VB, thereby eliminating the mismatch between programming languages and databases, as well as providing a single querying interface for different types of data sources.

For example, SQL is a Structured Query Language used to save and retrieve data from a database. In the same way, LINQ is a structured query syntax built in C# and VB.NET to retrieve data from different types of data sources such as collections, ADO.Net DataSet, XML Docs, web service and MS SQL Server and other databases.

[![C# LINQ usage](https://www.tutorialsteacher.com/Content/images/linq/linq-usage.PNG)](https://www.tutorialsteacher.com/Content/images/linq/linq-usage.PNG)

LINQ queries return results as objects. It enables you to uses object-oriented approach on the result set and not to worry about transforming different formats of results into objects.

[![LINQ Query](https://www.tutorialsteacher.com/Content/images/linq/linq-execution.PNG)](https://www.tutorialsteacher.com/Content/images/linq/linq-execution.PNG)


```C#
var result = from number in numbers where number > 5 select number
```
دي هترجعلي الارقام الي اكبر من 5 فالليست numbers

دايما الquery هتبدا ب from وبعدها الفاريبل الي هيشاور علي كل عنصر
وبعدها in بنحط الداتا سورس الي هنشتغل عليه 
وبعدين where ونحط اي شروط هتتطبق علي الارقام 
وبعدين select number


الresult هنا شايله جواها الquery نفسها (مش الناتج) 
الquery بتتنفذ لما اiterate علي الquery 
يعني لما اعمل لووب باشكالها او اقوله result. كذا هيبدا ينفذ الكويري

لو عايزها تتنفذ حالا 
بحط الquery فقوسين واقوله toList مثلا 
كده نفذت الكويري مره واحده والresult هتشيل list



هنستخدم الlinq في الentity framework بشكل اساسي


## Advantages of LINQ

- **Familiar language:** Developers don't have to learn a new query language for each type of data source or data format.
- **Less coding:** It reduces the amount of code to be written as compared with a more traditional approach.
- **Readable code:** LINQ makes the code more readable so other developers can easily understand and maintain it.
- **Standardized way of querying multiple data sources:** The same LINQ syntax can be used to query multiple data sources.
- **Compile time safety of queries:** It provides type checking of objects at compile time.
- **IntelliSense Support:** LINQ provides IntelliSense for generic collections.
- **Shaping data:** You can retrieve data in different shapes.