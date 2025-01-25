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
