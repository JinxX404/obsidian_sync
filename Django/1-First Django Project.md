بعد ما بنعمل الفولدر بتاع البروجكت وبنعمل اكتيف للvirtual environment 
هنعمل create للدجانغو بروجكت 
```shell 
django-admin startproject myproject
```
هيعملنا فايل وفولدر وجواه كذا فايل 
After running `django-admin startproject`, your folder will look like this:
```markdown
myproject/ 
	manage.py 
	myproject/ 
		__init__.py 
		settings.py 
		urls.py 
		asgi.py 
		wsgi.py
```

#### **`manage.py`**

- **What it is**: This file is like your project’s command center. It helps you interact with your Django project via the command line (e.g., running the server, migrating the database).
    
- **Real-world analogy**: Think of `manage.py` as the remote control for your Django app. You press buttons (run commands) to start the app, interact with the database, or create new features.
    
- **Common commands**:
    
    - `python manage.py runserver`: Starts your development server.
    - `python manage.py migrate`: Applies database migrations.
    - `python manage.py createsuperuser`: Creates an admin user for your site.

