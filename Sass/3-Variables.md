Variables are a way to store information that you can re-use later.

With Sass, you can store information in variables, like:

- strings
- numbers
- colors
- booleans
- lists
- nulls

Sass uses the $ symbol, followed by a name, to declare variables:

```scss
$_variablename_: _value_;
```


```scss
$myFont: Helvetica, sans-serif;  
$myColor: red;  
$myFontSize: 18px;  
$myWidth: 680px;  
  
body { 
font-family: $myFont;  
font-size: $myFontSize;  
color: $myColor;
}  
  
#container {
width: $myWidth;
}
```
لما الفايل بتاع الsass يتعمله transpile علشان يتحول css 
هياخد قيمه الفاريبل ويعمل replace بيه مكان استخدام الفاريبل


Sass variables are only available at the level of nesting where they are defined.
الاسكوب بتاعهم هيكون متاح مكان ما اتعملو 
يعني لو اتعملو جوه { } مش هيكونو متاحين بره

```Scss
$myColor: red;  
  
h1 {
$myColor: green;  
color: $myColor;
}  
  
p {
color: $myColor;
}
```
لو الفاريبل جلوبال واتغير جوه  { } مش هيتغير فالجلوبال ولو استخدمته بعدها هياخد من الجلوبال
يعني فالمثال ده غيرته جوه h1 ولما اجي استخدمه جوه p هيشوف الجلوبال بس ده الديفولت 

لو عايز اغير الديفولت واعمل اوفررايد علي القيمه بتاعت الفاريبل الجلوبال من جوه بلوك؟ 
هستخدم كيوورد !global
The default behavior for variable scope can be overridden by using the `!global` switch.
`!global` indicates that a variable is global, which means that it is accessible on all levels.
```Scss
$myColor: red;  
  
h1 {
$myColor: green !global;  
color: $myColor;
}  
  
p { 
color: $myColor;
}
```
كده الكيوورد هتعمل override علي قيمه الmycolor الي كانت بره 
واللون هيتغير green
لو استخدمت الفاريبل تاني هيشوف الgreen



**Tip: Global variables should be defined outside any rules. It could be wise to define all global variables in its own file, named "_globals.scss", and include the file with the [@include](https://www.w3schools.com/sass/sass_mixin_include.php) keyword.**

الافضل نعمل الجلوبال فاريبلز ففايل خارجي 
ونبقي نستدعيه لما نحتاجه بinclude
