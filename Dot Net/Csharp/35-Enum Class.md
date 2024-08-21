هو base class كل الenums الي بنعملها بتورث منه 
بيوفر شويه ميثودز تسهل علينا استخدام الuser defined enums
Provides utility methods to work with any enum type. It allows you to interact with enums more generically, such as retrieving all possible values or checking if a value is defined.

### `Enum.GetValues`

- **Purpose**: Retrieves an array of the values of the constants in a specified enumeration.
- **Return Type**: `Array` (an array of the enum type's underlying type).
- **Usage**: Use this method when you need to get the actual values of the constants in the enum (e.g., `int` values) rather than their names.

 ميثود زي GetValues() بترجع Array من الconstant بتاعت الenum
يعني بيرجع جواها الenum members 
واقدر اiterate عليه 
```C#
Array values = Enum.GetValues(typeof(DayOfWeek));  
  
foreach (var VARIABLE in values)  
{  
    Console.WriteLine($"Enum Memeber {VARIABLE} num {(int)VARIABLE}");  
}
```
الvalues شايله array of constants 
لما هطبعهم اقدر اطبع اسم كل constant لوحده واعمل cast برضو للرقم بتاعه
```
Enum Memeber sat num 0
Enum Memeber sun num 1
Enum Memeber mon num 2
Enum Memeber thu num 3
Enum Memeber wed num 4
Enum Memeber thr num 5
Enum Memeber fri num 6
```

نقدر نخزن الريتيرن بتاعت getvalues في array of that enum type , or list

```c#
DayOfWeek[] days =   (DayOfWeek[])Enum.GetValues(typeof(DayOfWeek));


List<DayOfWeek> dayList = Enum.GetValues(typeof(DayOfWeek)).Cast<DayOfWeek>().ToList();
```



### `Enum.GetNames`

- **Purpose**: Retrieves an array of strings representing the names of the constants in a specified enumeration.
- **Return Type**: `string[]` (an array of strings).
- **Usage**: Use this method when you need to get the names of the constants in the enum as strings.
فانكشن GetNames() بترجع array of strings للقيم الconstant دي 
يعني اخري اطبعهم مقدرش أأaccess الرقم الي وراهم(الي متخزنيين بيه)
```C#
string[] names = Enum.GetNames(typeof(DayOfWeek));
foreach (string name in names)
{ 
Console.WriteLine(name);
}
```