A **view** in Django is a function (or a class) that takes a request and returns a response. It’s the logic layer of your application, where you decide what data to show and how to process a request.

Django views are Python functions that take http requests and return http response, like HTML documents.

A web page that uses Django is full of views with different tasks and missions.
البروجكت بالدجانغو بيكون مجموعه من الفيوز وكل واحد بيعمل تاسك او وظيفه معينه

Views are usually put in a file called `views.py` located on your app's folder.

الفيو هي ميثود بتاخد ريكويست وترجع ريسبونس زي الhtml doc وبترجعه للتيمبلت

**But how can we execute the view? Well, we must call the view via a URL.**

ازاي نشغل الفيو ده؟
بنروحله عن طريق url


#### Types of Views:

1. **Function-based Views (FBVs)**: Simple functions that handle a request and return a response.
2. **Class-based Views (CBVs)**: More advanced views where each request method (like GET or POST) is a method in the class.


