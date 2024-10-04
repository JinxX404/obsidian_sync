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

#### **The Inner `myproject/` Folder**

Inside this folder are critical configuration files that dictate how your project behaves. Each file has a specific role:

##### **`settings.py`**

- **What it is**: This file holds your project’s configuration—everything from database settings to which apps are installed.
    
- **Real-world analogy**: `settings.py` is like the control panel in a spaceship where you set the environment (debug mode), location (database connection), and installed features (Django apps).
    
- **Key settings**:
    
    - **`DEBUG = True`**: This should be set to `True` during development to display detailed error messages.
    - **`INSTALLED_APPS`**: Lists all the apps that are active in your project (like "blog", "users", etc.).
    - **`DATABASES`**: Configuration for connecting to a database (SQLite by default, but you can switch to PostgreSQL, etc.).
- **Real-world example**:
    
    - You might work on a **blog website**. In your `INSTALLED_APPS`, you’ll add `blog`, `users`, and other apps you create. If you switch to a production environment, you change the `DEBUG` setting to `False` and update the `DATABASES` to use your production server.

##### **`urls.py`**

- **What it is**: This file maps URLs to views. It defines how your Django project routes requests.
    بيقرر كل url هيودي علي انهي view 
    كل ريكويست هيوجهه علي انهي صفحه؟
- **Real-world analogy**: Think of `urls.py` as the directory at the entrance of a building, telling people which room to go to depending on what they're looking for (e.g., `/about` for the about page).
    
- **How it works**:
    - When someone visits `mywebsite.com/about`, `urls.py` figures out which **view** should be used to handle the request.
    
- **Real-world example**:
    - You could set up routes for a website:
        - `/books` → Shows a list of all books.
        - `/books/<int:id>` → Shows details for a specific book (e.g., `/books/5` shows the book with ID 5).

##### **`asgi.py` and `wsgi.py`**

- **What they are**: These files are responsible for connecting your Django app to web servers.
    
- **Real-world analogy**: `asgi.py` and `wsgi.py` are like adapters that allow your Django app to communicate with web servers such as Apache, Nginx, or other deployment services.
    
- **Difference**:
    
    - **WSGI** is for traditional, synchronous web applications.
    - **ASGI** is for handling asynchronous capabilities, such as websockets or real-time data streams.

###### **`__init__.py`**

- **What it is**: This file tells Python that this directory is a package, allowing you to import things between different files within the project.









# To Run The Server
```
python manage.py runserver
```
هيعملي لوكال سيرفر اشوف عليه الشغل بتاعي 
وهيديلي الip بتاعه
هيكون شغال طلاما بروسيس الرن بتاعت الcmd شغاله 
لو عايز اقفل السيرفر هوقف الكوماند

![[Pasted image 20241004191844.png]]
