Sass keeps the CSS code DRY (Don't Repeat Yourself). One way to write DRY code is to keep related code in separate files.

You can create small files with CSS snippets to include in other Sass files. Examples of such files can be: reset file, variables, colors, fonts, font-sizes, etc.

ممكن يكون عندنا فايل نعمل بيه ريسيت لخواص معينه 
ف هعمله لوحده ولما احتاجه هعمله import فالبروجكت بتاعي
كده انا بحافظ علي اني اطبق DRY Principle لاني عملت الكود reusable 

بستخدم @Import  

the CSS `@import` directive has a major drawback due to performance issues; it creates an extra HTTP request each time you call it. However, the Sass `@import` directive includes the file in the CSS; so no extra HTTP call is required at runtime!

**Tip:** You do not need to specify a file extension, Sass automatically assumes that you mean a .sass or .scss file. You can also import CSS files. The `@import` directive imports the file and any variables or mixins defined in the imported file can then be used in the main file.

فيه في الcss كيوورد import لاكن فيها عيب فالبيرفورمنس 
بتحتاج extra http requests كل مره احتاج الفايل هيروح ينادي معاه الفايل التاني ف بيحتاج ريكوستات اكتر
لاكن الsass حلت المشكله بالكيوورد بتاعتها ب انها بتاخد الكلام الي هعمله امبورت وتحطه مع الCss فنفس الفايل ف مش هيحتاج ريكويست زياده 

لما نعمل transpile للsass file هنلاقي انه جاب كود الimported file وتحته كود الsass نفسه وحولهم لcss


```scss
#reset.scss
html,  
body,  
ul,  
ol { 
  margin: 0;  
  padding: 0;
  }
```

```scss
@import "reset";  
  
body {  
  font-family: Helvetica, sans-serif;  
  font-size: 18px;  
  color: red;
  }
```


هيتحولو لكده فالCss
```css
html, body, ul, ol {
  margin: 0;  
  padding: 0;
  }  
  
body { 
  font-family: Helvetica, sans-serif;  
  font-size: 18px;  
  color: red;
  }
```