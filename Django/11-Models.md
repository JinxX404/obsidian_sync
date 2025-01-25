Django models are the backbone of Django's **Object-Relational Mapping (ORM)** system. They act as a bridge between Python code and relational databases, allowing you to interact with databases using Python classes instead of writing raw SQL.


#### **What is a Model?**

- A Django model is a Python class that **subclasses `django.db.models.Model`**.
- Each model represents a **database table**, and each attribute of the model represents a **database column**.
كل مودل بيعبر عن جدول فالداتابيز 
وكل اتريبيوت جوه المودل عباره عن columns فالداتابيز 

```python
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=200)
    author = models.CharField(max_length=100)
```

-----

### **Model Fields**

Fields define the **type of data** stored in the database. Django provides over **30 built-in field types** to handle common data types.

#### **Common Field Types**

|Field Type|Description|
|---|---|
|`CharField`|For short-to-medium strings (e.g., titles, names). Requires `max_length`.|
|`TextField`|For large blocks of text (e.g., descriptions).|
|`IntegerField`|Stores integers.|
|`BooleanField`|True/False values.|
|`DateField`/`DateTimeField`|Dates or timestamps. Use `auto_now_add` for creation timestamps.|
|`EmailField`|Validates email format.|
|`ForeignKey`|Defines a many-to-one relationship (e.g., `Book` belongs to an `Author`).|
|`FileField`/`ImageField`|Handles file uploads (requires `Pillow` for images).|

#### **Field Options**

- `null=True`: Allows `NULL` values in the database (default: `False`).
- `blank=True`: Allows empty values in forms (default: `False`).
- `default`: Sets a default value (e.g., `default=0`).
- `unique=True`: Ensures the field’s value is unique across the table.
- `choices`: Restricts values to a list of predefined choices:
```python
STATUS_CHOICES = [('draft', 'Draft'), ('published', 'Published')]
status = models.CharField(max_length=10, choices=STATUS_CHOICES, default='draft')
```

-----
### **Relationships**

Django models support three types of relationships:

#### **1. Many-to-One (`ForeignKey`)**

- Links one model to another (e.g., a `Book` belongs to an `Author`):
```python
class Author(models.Model):
    name = models.CharField(max_length=100)

class Book(models.Model):
    author = models.ForeignKey(Author, on_delete=models.CASCADE)
```

#### **2. Many-to-Many (`ManyToManyField`)**

- Allows multiple relationships (e.g., a `Student` can enroll in multiple `Course`s):
```python
class Course(models.Model):
    name = models.CharField(max_length=100)

class Student(models.Model):
    courses = models.ManyToManyField(Course)
```

#### **One-to-One (`OneToOneField`)**

- Used when one object extends another (e.g., a `Profile` extends a `User`):
```python
class User(models.Model):
    username = models.CharField(max_length=100)

class Profile(models.Model):
    user = models.OneToOneField(User, on_delete=models.CASCADE)
    bio = models.TextField()
```


---
### **The `Meta` Class**

The `Meta` class configures **model-level settings**:
```python
class Book(models.Model):
    title = models.CharField(max_length=200)
    
    class Meta:
        ordering = ['-title']          # Default ordering for queries
        db_table = 'custom_book_table' # Custom database table name
        verbose_name_plural = 'Books'  # Human-readable plural name
        constraints = [                # Database constraints
            models.UniqueConstraint(fields=['title'], name='unique_title')
        ]
```


-----
### **Managers & QuerySets**

- **Managers** are interfaces for database operations (e.g., `objects`).
- **QuerySets** are collections of database records returned by a query.
#### **Custom Managers**
```python
class ActiveBookManager(models.Manager):
    def get_queryset(self):
        return super().get_queryset().filter(is_active=True)

class Book(models.Model):
    is_active = models.BooleanField(default=True)
    objects = models.Manager()          # Default manager
    active_books = ActiveBookManager()  # Custom manager
```

#### **QuerySet Examples**
```python
# Fetch all books:
Book.objects.all()

# Filter books by author:
Book.objects.filter(author__name='J.K. Rowling')

# Aggregations:
from django.db.models import Avg
Book.objects.aggregate(Avg('price'))
```

A QuerySet is a collection of data from a database.
A QuerySet is built up as a list of objects.
QuerySets makes it easier to get the data you actually need, by allowing you to filter and order the data at an early stage.
كولكشن من الداتا تعتبر list of objects بنجيبها من المودل 
```python
  mydata = Member.objects.all()
```
الMember هو المودل وبعدين هنجيب الاوبجكتس الي جواه .all()
هترجعلي كل الداتا الي فالجدول  

ممكن نستخدم Values() علشان نجيب الداتا في ديكشنري كل row فصيغه key-value pairs 
```jsx
  mydata = Member.objects.all().values()
```

```
<QuerySet [
{'id': 1, 'firstname': 'Emil', 'lastname': 'Refsnes', 'phone': 5551234, 'joined_date': datetime.date(2022, 1, 5)}, {'id': 2, 'firstname': 'Tobias', 'lastname': 'Refsnes', 'phone': 5557777, 'joined_date': datetime.date(2022, 4, 1)}, {'id': 3, 'firstname': 'Linus', 'lastname': 'Refsnes', 'phone': 5554321, 'joined_date': datetime.date(2021, 12, 24)}, {'id': 4, 'firstname': 'Lene', 'lastname': 'Refsnes', 'phone': 5551234, 'joined_date': datetime.date(2021, 5, 5)}, {'id': 5, 'firstname': 'Stalikken', 'lastname': 'Refsnes', 'phone': 5559876, 'joined_date': datetime.date(2022, 9, 29)}
]>
```


بنستخدم values_list() علشان نرجع columns محدده 
```jsx
  mydata = Member.objects.values_list('firstname')
```

بنستخدم filter لو عايزين نرجع row معين حسب شرط معين 
```jsx
  mydata = Member.objects.filter(firstname='Emil').values()
```
هاتلي الrow  الي فيه الفيرست نيم ب Emil وبعدين رجعلي الاوبجكت ك dictionary

لو عايز افلتر علي اكتر من كونديشن AND 
هستخدم كل كوندشن ك argument جوه الفلتر 
```jsx
mydata = Member.objects.filter(lastname='Refsnes', id=2).values()
```

لو عايز اعمل OR 
```jsx
mydata = Member.objects.filter(firstname='Emil').values() | Member.objects.filter(firstname='Tobias').values()
```
هيحقق كل جمله لوحدها ويرجع اوتبوت وبعدين هيتعملهم merge في نفس الفاريبل


***Field Lookups****

Django has its own way of specifying SQL statements and WHERE clauses.
To make specific where clauses in Django, use "Field lookups".
Field lookups are keywords that represents specific SQL keywords.

Use the `__startswith` keyword:
```jsx
.filter(firstname__startswith='L');
```

Is the same as the SQL statement:
```sql
WHERE firstname LIKE 'L%'
```
The above statement will return records where firstname starts with 'L'.

**Field Lookups Syntax**
السينتاكس بتاعها بيكون اسم الcolumn وبعده اتنين -- وبعدين ال field lookup بتاعنا 

A list of all field look up keywords:

|Keyword|Description|
|---|---|
|[contains](https://www.w3schools.com/django/ref_lookups_contains.php)|Contains the phrase|
|[icontains](https://www.w3schools.com/django/ref_lookups_icontains.php)|Same as contains, but case-insensitive|
|date|Matches a date|
|day|Matches a date (day of month, 1-31) (for dates)|
|[endswith](https://www.w3schools.com/django/ref_lookups_endswith.php)|Ends with|
|[iendswith](https://www.w3schools.com/django/ref_lookups_iendswith.php)|Same as endswidth, but case-insensitive|
|[exact](https://www.w3schools.com/django/ref_lookups_exact.php)|An exact match|
|[iexact](https://www.w3schools.com/django/ref_lookups_iexact.php)|Same as exact, but case-insensitive|
|[in](https://www.w3schools.com/django/ref_lookups_in.php)|Matches one of the values|
|isnull|Matches NULL values|
|[gt](https://www.w3schools.com/django/ref_lookups_gt.php)|Greater than|
|[gte](https://www.w3schools.com/django/ref_lookups_gte.php)|Greater than, or equal to|
|hour|Matches an hour (for datetimes)|
|[lt](https://www.w3schools.com/django/ref_lookups_lt.php)|Less than|
|[lte](https://www.w3schools.com/django/ref_lookups_lte.php)|Less than, or equal to|
|minute|Matches a minute (for datetimes)|
|month|Matches a month (for dates)|
|quarter|Matches a quarter of the year (1-4) (for dates)|
|[range](https://www.w3schools.com/django/ref_lookups_range.php)|Match between|
|regex|Matches a regular expression|
|iregex|Same as regex, but case-insensitive|
|second|Matches a second (for datetimes)|
|[startswith](https://www.w3schools.com/django/ref_lookups_startswith.php)|Starts with|
|[istartswith](https://www.w3schools.com/django/ref_lookups_istartswith.php)|Same as startswith, but case-insensitive|
|time|Matches a time (for datetimes)|
|week|Matches a week number (1-53) (for dates)|
|week_day|Matches a day of week (1-7) 1 is sunday|
|iso_week_day|Matches a ISO 8601 day of week (1-7) 1 is monday|
|year|Matches a year (for dates)|
|iso_year|Matches an ISO 8601 year (for dates)|

لو عايزين نعمل ordering للداتا الي راجعه بنستخدم order_by() وبنديله اسم ال column الي هنرتب علي اساسه
```jsx
mydata = Member.objects.all().order_by('firstname').values()
```
ديفولت بيرتب تصاعديا asec 

لو عايزين نرتب تنازليا desc 
هنستخدم - قبل اسم العمود
```jsx
mydata = Member.objects.all().order_by('-firstname').values()
```

لو هنعمل اوردر علي اكتر من col بنباصيهم جوه الميثود ك arguments
```jsx
mydata = Member.objects.all().order_by('lastname', '-id').values()
```
هنا هيرتب فالاول علي ال lastname تصاعديا وبعدين id تنازليا
