البروجكت فولدر هو كونتينر كامل لكل الapps الي جواه وبيحتوي علي settings and configurations وبتتطبق علي البروجكت كله 

لاكن الابب فولدر هو يعتبر موديول واحد بيهندل جزء من البروجكت او وظيفة مخصصو جوه البروجكت 


مش هنستخدم فولدر البروجكت في كود للابلكيشن هنستخدمه فقط للكونفجريشن

### Difference Between Project and App Folders:

1. **Project Folder**:
    - It's the **overall container** for your entire project.
    - Contains global settings, main URL configurations, and files for interacting with servers.
    - **Purpose**: Manages the entire project configuration.
2. **App Folder**:
    - Each app is a **specific module** of your project (e.g., books, users, reviews).
    - Contains the code (models, views, migrations) related to one piece of functionality.
    - **Purpose**: Implements individual features within the project.

---

### How They Work Together:

- The **project folder** ties everything together (global settings, URLs, etc.).
- The **apps** inside the project handle specific functionalities (like managing books, users, etc.).



### 1. **Project Folder** (Main Project Directory)

The **project folder** is the overall container for your Django project. It contains settings and configurations that apply to the entire project. When you create a Django project, this folder is created automatically.

#### What's Inside the Project Folder:

- **`settings.py`**: Configuration file for your entire project. It contains settings like database configuration, allowed hosts, installed apps, etc.
- **`urls.py`**: The global URL router for your project. It maps high-level URLs to the individual **apps**.
- **`wsgi.py`** and **`asgi.py`**: These are the files that help Django interact with the web server. You usually don’t touch these unless deploying.
- **`manage.py`**: A script that lets you run various Django commands, like `runserver`, `migrate`, etc.

#### Example:

If your project is named **GoodreadsAlt**, your project folder structure might look like this:
```markdown
GoodreadsAlt/
    manage.py
    GoodreadsAlt/
        __init__.py
        settings.py
        urls.py
        wsgi.py
        asgi.py

```
### 2. **Apps Folder** (Individual Apps)

An **app** in Django is a module that handles one specific part of your project’s functionality. It’s a self-contained component that you can use to build part of your project (like a **Books** app for managing books or a **Users** app for managing users).

You can have multiple apps inside one Django project. Each app focuses on one specific feature or function. Apps are reusable, meaning you can use them across different projects if needed.

#### What's Inside the Apps Folder:

- **`models.py`**: Contains the data models (blueprints for database tables).
- **`views.py`**: Handles logic for responding to user requests and returning data (or templates).
- **`urls.py`** (optional): Handles URL routing for that specific app.
- **`admin.py`**: Allows you to register models for the admin panel.
- **`migrations/`**: Contains migration files for the app’s models.

#### Example:
```markdown
books/
    __init__.py
    admin.py
    apps.py
    models.py
    views.py
    urls.py
    migrations/
```
