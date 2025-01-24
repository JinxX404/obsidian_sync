عندنا فايلين للurl واحد بيتعمله كرييت مع الفولدر بتاع البروجكت 
والتاني احنا بنعمله لكل app عندنا

الفرق بينهم ان الurl بتاع البروجكت بيعمل routing للapps بتاعت البروجكت ك high level
مثلا البروجكت هيروح لكذا app منهم users books home admin 
ف بنعملهم routing جوه الurl للبروجكت نفسه

لاكن التاني بتاع الapp بنعمل فيه routing للurls بتاعت الapp ده بس 
الي هو مسئول عنهم
ده بيدي امكانيه للapp انه يكون reusable علشان هو شايل كل الurls بتاعته ومش معتمد علي الrouting للبروجكت الكامل 


### 1. **Main `urls.py` in the Project Folder**

The main **urls.py** file in the project folder is the **central routing hub** for your entire Django project. It maps high-level URLs to individual app URLs. You can think of it as the project's main traffic controller.

#### Example:

In your Goodreads alternative project, this file is likely located at:

```
GoodreadsAlt/urls.py
```

This file usually includes:

- A path for **admin** (e.g., `admin/`).
- A path to include **app URLs** using `include()`.
- High-level routes for the entire project.

#### Why Do We Need It?

- It directs requests to different apps.
- If you have multiple apps (like `books`, `users`, `reviews`), you want a single place to organize and route them.

#### Example:
```python
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('books.urls')),  # Sends URLs starting with 'books/' to books/urls.py
]
```

### 2. **`urls.py` in the App Folder**

The **urls.py** file in each app is **specific to that app**. It defines **internal routing** within the app and maps URLs to views specific to that app’s functionality.

#### Why Do We Need It?

- It **keeps app routing separate** from the main project routing. This makes it easier to organize and maintain code.
- Each app can handle its own URLs without cluttering up the main project `urls.py`.
- If you need to reuse the app in another project, the URLs are already set up and easily portable.

#### Example:

In the `books` app, you might have a **urls.py** file that defines specific routes for book-related views:

```python
from django.urls import path
from . import views

urlpatterns = [
    path('books/', views.book_list_view, name='book_list'),
    path('books/<int:id>/', views.book_detail_view, name='book_detail'),  # URL to view a specific book by ID
]
```
This lets you set URLs like:

- `/books/` – for the **book list view**
- `/books/1/` – for viewing **details of a book** with ID 1

### Difference Between the Two:

- **Project `urls.py`**:
    - Connects the entire project’s URLs.
    - Routes high-level URLs to specific apps.
- **App `urls.py`**:
    - Connects the URLs specific to that app.
    - Organizes URLs for specific functionality (like viewing books) within the app.

By having both, you get a clean, modular structure where each app is responsible for its own URLs, while the main project `urls.py` brings everything together.


### What is a Route?

In web development, a **route** (or URL route) is a path that determines which **functionality** (or **view**) to execute based on the URL the user visits.

For example:

- When you go to `www.example.com/books/`, the **route** tells Django to execute the view that shows a list of books.
- When you go to `www.example.com/books/1/`, the **route** tells Django to execute a view that shows details for the book with ID 1.

In Django, we define these routes in **`urls.py`** files.

#### How Routes Work in Django

1. Django receives a URL request.
2. It looks for a **matching route** in the `urls.py` files.
3. Once it finds a match, it directs the request to the **view** specified for that route.
4. The view function then processes the request and sends back a response (like a webpage or data).

### Connecting URLs in Django

To connect URLs in Django, we use the `urls.py` files in both the **project** and **app** folders.

#### 1. **Main `urls.py` in the Project Folder**

The main **urls.py** file in the project folder acts as a central point to route high-level URLs to specific app URLs. This is how Django knows which app to send a request to.

#### Example:

Let’s say your **project** is called `GoodreadsAlt`. In the project folder, there is a `urls.py` file where you include paths to each app:

```python
#GoodreadsAlt/urls.py
from django.contrib import admin 
from django.urls import include, path  
urlpatterns = [ 
path('admin/', admin.site.urls), # Admin route
path('books/', include('books.urls')), # Routes URLs starting with 'books/' to books app 
]
```
In this code:

- `path('books/', include('books.urls'))` says: “Send any URL that starts with `books/` to the **`urls.py`** in the `books` app.”
بقوله لو جالي فالurl الadmin هوديه للادمن 
لو جه books/ دي تعتبر app وحدها ف هعمل route للurls بتاعت الapp ده 
هيروح للapp نفسه ويجيب الصفحه الي هناك فيها empty string الي تعتبر الهوم بتاع الbooks


#### 2. **App `urls.py` for Specific Routes**

Inside the **`urls.py`** of the `books` app, we define the routes for book-specific views. Here’s how it looks:

```python
# books/urls.py
from django.urls import path
from . import views

urlpatterns = [
path('', views.book_list_view, name='book_list'),# Shows all books
path('<int:id>/', views.book_detail_view, name='book_detail'),
# Shows details of a specific book by ID
]

```
In this code:

- `path('', views.book_list_view, name='book_list')`: When you go to `/books/`, it triggers the `book_list_view` function in `views.py` to show the list of books.
- `path('<int:id>/', views.book_detail_view, name='book_detail')`: When you go to `/books/1/`, it triggers the `book_detail_view` function, passing `1` as the `id` parameter to show details for the book with that ID.

بقوله لو جالك ' ' يعني انت فاتح الapp ده اول صفحه تعتبر الهوم ليك 
هحوله للفيو بتاع الbook list 
لو جاله كتاب معين هحوله للفانكشن الي بتجيب معلومات كتاب معين 

### How Django Matches Routes

1. If you go to `/books/`, Django first checks the **project `urls.py`** and sees that any URL starting with `books/` goes to `books/urls.py`.
2. Then, in `books/urls.py`, it matches `''` (the empty string) to `views.book_list_view`, meaning you get the **list view**.
3. If you go to `/books/1/`, Django matches `<int:id>/` and calls `views.book_detail_view` with `id=1`, displaying details for that book.



بنعمل الapps الي عايزينها 
ونروح نربطها في فايل الsettings للبروجكت جوه installed apps بنحطها فالديكشنري 
بنحط اسم الapp بين ' ' 
وبعدين بنمسك فايل الurl بتاع البروجكت 
ونعمل route للapps 
نقوله لو جالك كذا وديه لكذا 
بنستخدم هنا include function علشان نباصي جواها فايل الurls بتاع الapp 
```python
    path('member', include('members.urls')),
```
بحط الpath جوه الليست الي اسمها urlpatterns 
بيتحط فيها كل الRoutes 
الpath بيتباصي فيه اتنين ارجومنت 
الاول هو الroute الي هو بيكون فاللينك مثلا 127.0.0.1/member 
هنا هياخد الmember ويعرف انه رايح للapp الي اسمه member 
والارجومنت التاني بنعمل فيها include للurls بتاعت الابب ده
يعني معناها لو جالك route للapp الي اسمه member وديه للurls بتاعت mmebers يروح يدور جواها عالماتشينج بتاعه 

ممكن من هنا معملش include واباصيله view 
حسب الcase 

ولما بروح الurls بتاع الapp بنعمل import للviews علشان هنستخدمها جواه 
```python
    path('', views.members, name='members'),
```
هنا جوه الurl للapp بقوله لو جالك Route وديه للviews.members 
يعني هبعته لview ده جوه فايل Views (قولنا ان الview هو فانكشن)
وبديله اسم هحتاجه بعدين 

