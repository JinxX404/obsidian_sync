---
aliases:
  - 0-How Does Django Works?
---
Django follows the MVT design pattern (Model View Template).

- Model - The data you want to present, usually data from a database. 
الداتا الي هنعرضها 
- View - A request handler that returns the relevant template and content - based on the request from the user.
الفيو بيجيله ريكويست وهو بيهندله بالتيمبلت المناسب حسب ريكويست اليوزر
- Template - A text file (like an HTML file) containing the layout of the web page, with logic on how to display the data.
هو فايل فيه حاجات هنعرضها لليوزر 


## Model

The model provides data from the database.

In Django, the data is delivered as an Object Relational Mapping (ORM), which is a technique designed to make it easier to work with databases.

The most common way to extract data from a database is SQL. One problem with SQL is that you have to have a pretty good understanding of the database structure to be able to work with it.

Django, with ORM, makes it easier to communicate with the database, without having to write complex SQL statements.

The models are usually located in a file called `models.py`.
الدجانغو بتتعامل مع ORM علشان يسهل التعامل مع الداتابيز بدون ما نحتاج complex sql queries 


## View

A view is a function or method that takes http requests as arguments, imports the relevant model(s), and finds out what data to send to the template, and returns the final result.

The views are usually located in a file called `views.py`.
فانكشن بتاخد ريكويست كارجومنت وبتجيب المودلز الي محتاجاها وتبعت للتيمبلت 


## Template

A template is a file where you describe how the result should be represented.

Templates are often .html files, with HTML code describing the layout of a web page, but it can also be in other file formats to present other results, but we will concentrate on .html files.

Django uses standard HTML to describe the layout, but uses Django tags to add logic:

```django
<h1>My Homepage</h1>

<p>My name is {{ firstname }}.</p>
```

The templates of an application is located in a folder named `templates`.