Each app represents a specific feature or section of your website (like "blog", "users", etc.).
كل بروجكت بيتكون من Applications مختلفه 
او كل سكشن فالبروجكت يعتبر applications

مثلا لو هعمل blog website ف هيكون فيه كذا سكشن جواه 
مثلا سكشن للblog وسكشن لل users 
ف كل واحد هيكون app 

علشان اعمل app هستخدم الكوماند ده ولازم اكون فنفس الفولدر الي فيه manage.py
```
python manage.py startapp bookhub
```

This creates a new folder structure for your app:
```
bookhub/ 
	migrations/ 
	__init__.py
	admin.py 
	apps.py
	models.py 
	tests.py
	views.py
```
