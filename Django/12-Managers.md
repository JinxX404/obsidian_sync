Django manager is a class that acts as an interface through which Django models interact with databases. Every model has at least one manager object. It has a lot of methods, attributes to ease working with databases.
المانجر هو كلاس يعتبر واجهة بين المودل والداتابيز
كل مودل فيه عالاقل  مانجر اوبجكت واحد وبيكون جواه كل الي يساعد في التواصل مع الداتابيز
الاوبجكت الديفولت الي بيكون فالمودل هو اسمه objects 

السينتاكس بتاعته 
```python
model_name.objects.method
```

اقدر اغير اسم الديفولت مانجر اوبجكت عن طريق 
```python
students = models.Manager() //now the default manager is named as students
```
جوه المودل بعمل override للقيمه عن طريق اني باخد اوبجكت من مانجر 
وكده اقدر استخدم students بدلا من objects 

Manager objects have many in-build methods to ease the operations on the database. Some of the most popular methods are described here – 

|   |   |
|---|---|
|all()|returns a query set containing all objects created so far|
|filter(**kwargs)|returns a query set containing a list of objects that match with the given arguments. If no matched object is found, it returns an empty query set.|
|exclude(**kwargs)|it does exactly the opposite of filter() method i.e. returns a queryset containing objects that does not match with given arguments.|
|get(**kwargs)|returns a single object that match with given argument. If multiple objects found it will throw an Model.MultipleObjectsReturned  error. If get() doesn’t find any object, it raises a Model.DoesNotExist exception.|
|create(**kwargs)|create a new object with given arguments.|
|order_by(*fields)|sets the ordering of the previously returned queryset according to the arguments passed in it.|

----
نقدر نعمل custom manager بالميثودز الزياده او الفانكشنز الزياده الي محتاجين نضيفها
ممكن نعمل override علي ميثود موجوده قبل كده علشان تتصرف بطريقه مختلفه

There are two reasons you might want to customize a `Manager`: to add extra `Manager` methods, and/or to modify the initial `QuerySet` the `Manager` returns.

هنعمل مانجر جديد وهيورث من المانجر الbase 
وبعدين هنحط جواه الميثودز 
وهنروح نربطه بالمودل 
