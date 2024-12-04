The JSON syntax is a subset of the JavaScript syntax.

JSON syntax is derived from JavaScript object notation syntax:
- Data is in name/value pairs
- Data is separated by commas
- Curly braces hold objects
- Square brackets hold arrays

بتكون في شكل key value pairs 
وبين كل key value بنفصل ب comma 

نقدر نشيل اراي او اوبجكت ك value 
 الاراي ب [ ]  
 الاوبجكت ب { }


A name/value pair consists of a field name (in double quotes), followed by a colon, followed by a value:  
```JSON
"name":"John"
```
JSON names require double quotes.
لازم ال key او name يكون في double quotes " "

الفرق في ال key بين ال json وال js
ان الkey فالjson بيكون سترينج دايما وبنحطه في double quotes 
لاكن ال key فالjs ممكن يكون سترينج او رقم او اي اسم معرف 
```json
{"name":"John"}
```

```js
{name:"John"}
```


## JSON Values

In **JSON**, _values_ must be one of the following data types:

- a string
- a number
- an object
- an array
- a boolean
- null
ال value ممكن تكون سترينج او رقم او اوبجكت او اراي او بوليان او null

In **JavaScript** values can be all of the above, plus any other valid JavaScript expression, including:

- a function
- a date
- undefined
ال js ممكن احطلها نفس الjson + فانكشن او date او undefined 


In JSON, _string values_ must be written with double quotes:

```JSON
{"name":"John"}
```

In JavaScript, you can write string values with double _or_ single quotes:

```JavaScript
{name:'John'}
```
