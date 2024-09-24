في ال css كنت بستخدم الطريقه العاديه علشان اقدر اكسس اي element جوه parent
```css
  nav ul {
	  margin: 0;  
	  padding: 0;  
	  list-style: none;
	  }  
  nav li {
    display: inline-block;
    }  
  nav a { 
	  display: block;  
	  padding: 6px 12px;  
	  text-decoration: none;
  }
```
علشان اوصل للul الي جوه الnav كنت هعمل كده nav ul

لاكن مع الsass هقدر اعمل النيستينج زي الhtml
هحط الul جوه البلوك بتاع الnav 

```scss
nav { 
	ul {    
		margin: 0;  
		padding: 0;  
	    list-style: none; 
	  }  
	li {
	    display: inline-block;  
	   }  
	a {   
		display: block;  
		padding: 6px 12px;  
		text-decoration: none; 
	 }
 }
```
كده هيعرف اني عايز كل عناصر ال ul li a الي جوه الnav

-------


```css
font-family: Helvetica, sans-serif;  
font-size: 18px;  
font-weight: bold;  
  
text-align: center;  
text-transform: lowercase;  
text-overflow: hidden;
```
لو عندي بروبرتي زي كده كلهم للفونت وتحتهم حاجات زي family , size , weight 
اقدر استخدم sass nested property

```scss
font: {  
  family: Helvetica, sans-serif;  
  size: 18px;  
  weight: bold;
  }  
  
text: {
  align: center;  
  transform: lowercase;  
  overflow: hidden;
  }
```
كده هتتقري font-family و font-size و font-weight 