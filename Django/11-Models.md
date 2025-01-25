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

