الباكدج هي مجموعة موديولز مع بعض بالفايل بتاعتها 

both modules and packages organize and structure the code but serve different purposes. In simple terms, **a module is a single file containing Python code, whereas a package is a collection of modules that are organized in a directory hierarchy**




```python
# -- Modules => Install External Packages --
# ------------------------------------------
# [1] Module vs Package
# [2] External Packages Downloaded From The Internet
# [3] You Can Install Packages With Python Package Manager PIP
# [4] PIP Install the Package and Its Dependencies
# [5] Modules List "https://docs.python.org/3/py-modindex.html"
# [6] Packages and Modules Directory "https://pypi.org/"
# [7] PIP Manual "https://pip.pypa.io/en/stable/reference/pip_install/"
```
الpip هي الباكدج مانجر الي بتحمل الباكدج والdependencies بتاعتها 
ديبيندسي الي هي الفايلات او المكتبات الي محتاجاها المكتبه بتاعتنا علشان تشتغل
مثلا لو هحمل مكتبه x 
ف x دي علشان تشتغل محتاجه تحمل معاها y , z
الy,z دول يعتبرو depenencies


الpip تقدر تحمل باكدج معينه او اكتر من بكدج (بسيب ما بينهم مسافه)
او تحمل اصدار معين مثلا pypdf=1.2 
لما بكتب يساوي بقوله هات الاصدار ده
ممكن اقوله  pypdf>=1.2 يعني الاصدار ده او اعلي منه 


لو هعمل ابجريد لبكدج بستخدم pip install packagename --upgrade


---


## What is Module in Python?

**The module is a simple Python file that contains collections of functions and global variables and with having a .py extension file.** It is an executable file and to organize all the modules we have the concept called Package in Python. 

### Examples of modules:

1. [Datetime](https://www.geeksforgeeks.org/python-datetime-module/)
2. [Regex](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)
3. [Random](https://www.geeksforgeeks.org/python-random-function/) etc.



---


## **What is Package in Python?**

**The package is a simple directory having collections of modules.** This directory contains Python modules and also having [__init__.py](https://www.geeksforgeeks.org/__init__-in-python/) file by which the interpreter interprets it as a Package. The package is simply a namespace. The package also contains sub-packages inside it. 

### Examples of Packages: 

1. [Numpy](https://www.geeksforgeeks.org/numpy-in-python-set-1-introduction/) 
2. [Pandas](https://www.geeksforgeeks.org/creating-a-pandas-series/)




---

## **What is Library in Python**

The **library** is having a collection of related functionality of codes that allows you to perform many tasks without writing your code. **It is a reusable chunk of code that we can use by importing it into our program**, we can just use it by importing that library and calling the method of that library with a period(.). However, **==it is often assumed that while a package is a collection of modules, a library is a collection of packages.==**

### Examples of Libraries: 

1. [Matplotlib](https://www.geeksforgeeks.org/python-introduction-matplotlib/)
2. [Pytorch](https://www.geeksforgeeks.org/understanding-pytorch-lightning-datamodules/)
3. [Pygame](https://www.geeksforgeeks.org/pygame-import-and-initialize/)
4. [Seaborn](https://www.geeksforgeeks.org/introduction-to-seaborn-python/) etc.

[What is the difference between Python's Module, Package and Library? - GeeksforGeeks](https://www.geeksforgeeks.org/what-is-the-difference-between-pythons-module-package-and-library/)

[Scripts, Modules, Packages, and Libraries – Real Python](https://realpython.com/lessons/scripts-modules-packages-and-libraries/)


- Any Python file is a [_module_](http://docs.python.org/tutorial/modules.html), its name being the file's base name without the `.py` extension.
- A [_package_](http://docs.python.org/tutorial/modules.html#packages) is a _collection_ of Python modules: while a module is a single Python file, a package is a directory of Python modules containing an additional `__init__.py` file, to distinguish a package from a directory that just happens to contain a bunch of Python scripts. Packages can be nested to any depth, provided that the corresponding directories contain their own `__init__.py` file.
