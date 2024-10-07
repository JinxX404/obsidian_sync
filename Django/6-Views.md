A **view** in Django is a function (or a class) that takes a request and returns a response. It’s the logic layer of your application, where you decide what data to show and how to process a request.

Django views are Python functions that take http requests and return http response, like HTML documents.

A web page that uses Django is full of views with different tasks and missions.
البروجكت بالدجانغو بيكون مجموعه من الفيوز وكل واحد بيعمل تاسك او وظيفه معينه

Views are usually put in a file called `views.py` located on your app's folder.

الفيو هي ميثود بتاخد ريكويست وترجع ريسبونس زي الhtml doc وبترجعه للتيمبلت

**But how can we execute the view? Well, we must call the view via a URL.**

ازاي نشغل الفيو ده؟
بنروحله عن طريق url


الفيو بيجيله ريكويست وبيبقي عايز يبعت ريسبونس 
فبيستخدم الموديول بتاع django.http بستخدم من جواها فانكشن HttpResponse وببعت فيها ريسبونس 
ممكن يكون جمله زي 
```python
def members(request):
    return HttpResponse("Hello world!")
```

الurl هيبعتنا للفانكشن دي هيبعتلها ريكويست وهي هترجع ريسبونس


او الفيو بدل ما يبعت جمله يقدر يبعت تيمبلت كامل فيه كلام زي فايل html مثلا
هنا هيحتاج يعمل render ف هيستخدم موديول django.shortcuts ويستخدم من جواه render
```python
def members(request):
    return render(request , 'index.html')
```
او 
علشان نستخدم التيمبلت فالview هنحتاج موديول django.template ومن جواه فانكشن loader ومعاه موديول django.http من جواه HttpResponse

```python
from django.http import HttpResponse
from django.template import loader

def members(request):
  template = loader.get_template('index.html')
  return HttpResponse(template.render())
```
فالاول بنستخدم ال loader علشان نعمل لوود للتيمبلت 
وبنرجع response جواها التيمبلت معموله ريندر


فالفيو بيكون عندنا فاريبلز وبنبعتها في ديكشنري مع الريندر بتاع التيمبلت 
واقدر استخدم الفاريبلز دي فالتيمبلت 
هباصيها فالارجومنت بتاع context 
```python
def members(request):
    variables = {
        'name' : 'Moataz Mohammed',

        'age' : 21

    }

    return render(request , 'index.html' , variables)
```


###### Types of Views:

1. **Function-based Views (FBVs)**: Simple functions that handle a request and return a response.
2. **Class-based Views (CBVs)**: More advanced views where each request method (like GET or POST) is a method in the class.



