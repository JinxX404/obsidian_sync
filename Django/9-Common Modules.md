### 1. **django.urls**
   This module is essential for URL routing. Here are some key functions from `django.urls`:
   
   - **`path`**: Used to define URL routes. It matches URL patterns and maps them to views.
     ```python
     from django.urls import path
     ```

   - **`include`**: Used in the main `urls.py` file to include other URL configurations from your apps. It helps you organize and keep each app’s URLs in separate files.
     ```python
     from django.urls import include
     ```

#### Example:
```python
from django.urls import path, include

urlpatterns = [
    path('books/', include('books.urls')),  # Includes URLs from books app
]
```

### 2. **django.shortcuts**
This module provides helper functions to make common tasks easier, like rendering templates or redirecting users.

   - **`render`**: Renders an HTML template and returns an HTTP response. It’s used to pass data to templates and display them.
     ```python
     from django.shortcuts import render
     ```

   - **`redirect`**: Redirects the user to a different URL. Often used after a form submission to redirect the user to another page.
     ```python
     from django.shortcuts import redirect
     ```

   - **`get_object_or_404`**: Fetches an object from the database by primary key or raises a `404 Not Found` error if the object doesn’t exist. This is useful when trying to retrieve specific items.
     ```python
     from django.shortcuts import get_object_or_404
     ```

#### Example:
```python
from django.shortcuts import render, get_object_or_404
from .models import Book

def book_detail_view(request, id):
    book = get_object_or_404(Book, pk=id)
    return render(request, 'books/book_detail.html', {'book': book})
```

### 3. **django.http**
This module is useful for dealing with HTTP requests and responses directly.

   - **`HttpResponse`**: Sends raw HTML or text back to the client. Useful for testing or sending simple responses.
     ```python
     from django.http import HttpResponse
     ```

   - **`HttpResponseRedirect`**: Redirects the user to a different page. This is commonly used in forms or after some user actions.
     ```python
     from django.http import HttpResponseRedirect
     ```

#### Example:
```python
from django.http import HttpResponse

def hello_view(request):
    return HttpResponse("Hello, World!")
```

### 4. **django.conf**
This module contains **project configuration** settings. You’ll often use it to import settings or access media files.

   - **`settings`**: Allows access to your project’s settings. Commonly used when working with file uploads, static files, or other configuration settings.
     ```python
     from django.conf import settings
     ```

   - **`urls.static`**: Helper function for handling static and media files during development.
     ```python
     from django.conf.urls.static import static
     ```

#### Example:
```python
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    # other URL patterns
] + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

### 5. **django.contrib**
Django has a built-in `contrib` module that contains various helpful apps and modules like `auth`, `admin`, and more.

   - **`admin`**: Registers the admin site in your project and allows configuration of admin settings.
     ```python
     from django.contrib import admin
     ```
   - **`auth`**: Django’s authentication system, which manages users, permissions, and more.
   - **`messages`**: A messaging framework for storing and displaying messages to users.
     ```python
     from django.contrib import messages
     ```

#### Example:
```python
from django.contrib import admin

urlpatterns = [
    path('admin/', admin.site.urls),
]
```

### 6. **django.db**
This module allows you to interact with the database. It includes model-related features.

   - **`models`**: This is where you define the structure of your data. It’s used to create tables in the database.
     ```python
     from django.db import models
     ```

   - **`migrations`**: Handles database migrations and keeps track of changes made to the models.
     ```python
     from django.db import migrations
     ```

#### Example:
```python
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=200)
    author = models.CharField(max_length=100)
```

### Summary:
These modules and functions are your basic building blocks in Django. Here’s a quick recap:
- **`django.urls`**: Routes and connects URLs with `path` and `include`.
- **`django.shortcuts`**: Provides convenient functions like `render`, `redirect`, and `get_object_or_404`.
- **`django.http`**: Manages HTTP responses with `HttpResponse` and `HttpResponseRedirect`.
- **`django.conf`**: Accesses configuration settings.
- **`django.contrib`**: Manages built-in Django features like `admin`, `auth`, and `messages`.
- **`django.db`**: Works with the database, models, and migrations.

