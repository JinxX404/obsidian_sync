- **Len()**
    
    بتحسب طول الاسترينج
    
    ```Python
    myString = "I Love Python"
    print(len(myString)) # 13
    ```
    
- **Strip()**
    
    الديفولت بتاعها انها بتشيل المسافات لو مبصيتش بارميتر
    
    فيه ليفت ورايت ستريب
    
    ```Python
    myString = "       I Love Python       "
    print(myString.strip())
    print(myString.rstrip())
    print(myString.lstrip())
    ```
    
    الاستريب العاديه بتشيل يمين وشمال
    
    الاستريب رايت بتشيل شمال وتسيب يمين
    
    الاستريب ليفت بتشيل يمين وتسيب شمال
    
    ```Plain
    I Love Python
           I Love Python
    I Love Python
    ```
    
    لو باصيتلها بارميتر هتشيل البارميتر ده
    
    ```Python
    myString = "@@@@@I Love Python@@@@@"
    print(myString.strip("@"))
    print(myString.rstrip("@"))
    print(myString.lstrip("@"))
    \#output
    I Love Python
    @@@@@I Love Python
    I Love Python@@@@@
    ```
    
    ```Python
    myString = "@$@$@$@$@$I Love Python@$@$@$@$@$"
    print(myString.strip("$@")) \#or @$
    print(myString.rstrip("$@"))
    print(myString.lstrip("$@"))
    \#output
    I Love Python
    @$@$@$@$@$I Love Python
    I Love Python@$@$@$@$@$
    ```
    
- **title()**
    
    ```undefined
    myString = "i love 2d graphics and 3g technology and python"
    print(myString.title())
    ```
    
    بتعمل اول حرف من كل كلمه كابيتل والحروف الي بعد الارقام كابيتل
    
    ```Python
    I Love 2D Graphics And 3G Technology And Python
    ```
    
      
    
- **capitalize()**
    
    بتخلي اول حرف فكل كلمه كابتل وملهاش علاقه بالارقام زي التايتل
    
    ```Python
    myString = "i love 2d graphics and 3g technology and python"
    print(myString.capitalize())
    ```
    
- **zfill()**
    
    بتحط اصفار علي الشمال شبه الباد ليفت في السي شارب
    
    ```Python
    a , b , c , d = "1" , "11" , "111" , "1111"
    print(a.zfill(3)) # 001
    print(b.zfill(3)) # 011 
    print(c.zfill(3)) # 111
    print(d.zfill(3)) # 1111
    ```
    
    بنباصيلها بارميتر ونقوله عايزين الاسترينج بتاعنا يكون طوله كام
    
    هو بيشوف الاسترينج الاقل من الطول ده وهيكمله اصفار شمال
    
    لاكن الاسترينج الي نفس الطول بتاع البارميتر او اكبر منه مش هيتاثرو
    
      
    
      
    
- **upper()**
    
    ```Python
    print("abc".upper())
    ```
    
    بتحول الاسترينج لكابتل
    
- **lower()**
    
    بتحول الاسترينج لاسمول
    
    ```Python
    print("ABC".lower())
    ```
    
      
    
- **split()**
    
    بنستخدمها لفصل الاسترينج وبترجع ليست
    
    ديفولت بتفصل بالمسافه
    
    وممكن نباصيلها سيبارتور او سيبارتور وماكس سبليت
    
    وعندنا rsplit
    
    بتعمل نفس الاسبليت لاكن بتبدا من اليمين
    
    ```Python
    a = "I Love Python and PHP and MySQL"
    print(a.split())
    # ['I', 'Love', 'Python', 'and', 'PHP', 'and', 'MySQL']
    ```
    
    ممكن نستخدم سيبارتور غير الاسبيس
    
    ```Python
    a = "I-Love-Python-and-PHP-and-MySQL"
    print(a.split("-"))
    # ['I', 'Love', 'Python', 'and', 'PHP', 'and', 'MySQL']
    ```
    
      
    
    وممكن نقوله عايزين نعمل عدد سبليت معين وبعدين نوقف ونجيب باقي الاسترينج كعنصر واحد
    
    ```Python
    a = "I-Love-Python-and-PHP-and-MySQL"
    print(a.split("-",3))
    # ['I', 'Love', 'Python', 'and-PHP-and-MySQL']
    ```
    
      
    
    كل الي عملناه فوق هتعمله ال rsplit لاكن من اليمين
    
    ```Python
    a = "I-Love-Python-and-PHP-and-MySQL"
    print(a.rsplit("-",3))
    # ['I-Love-Python-and', 'PHP', 'and', 'MySQL']
    ```
    
    هتعمل تلاته سبليت من اليمين وتعامل باقي الاسترينج كعنصر واحد
    
      
    
- **center()**
    
    بترجع الاسترينج قبله وبعده حاجات انا طالبها
    
    بديله بارميتر علي الاقل وبيكون فيه طول الاسترينج الي عايزه يرجع
    
    لو مباصيتش حاجه معينه عايز احطها بيحطها مسافات
    
    والحاجات الي بيحطها بيحطها قبل وبعد الاسترينج
    
    لو الرقم الي باقي يحطه يمين وشمال زوجي بيقسمه علي الاتنين نص يمين ونص شمال
    
    لو الرقم فردي بيحط الاكبر علي الشمال
    
    يعني الاسترينج 6 حروف وقولتله رجعلي 11 هيكون باقي 5 يملاهم
    
    هيحط 3 شمال واتنين يمين
    
    لو زوجي وعايزين 10 يعني باقي 4 هيحط 2 و 2
    
    ```Python
    a = "moataz" 
    print(a.center(10))
    #  moataz  
    ```
    
    او نحط كاركتر معين
    
    ```Python
    a = "moataz" 
    print(a.center(11,"$"))
    
    #  $$$moataz$$
    ```
    
      
    
- **count()**
    
    ممكن تاخد بارميتر واحد الي هو هندور عليه
    
    او هتاخد 3 باريمتر من ضمنهم الاسترينج الي هندور عليه والبدايه والنهايه هندور من فين لفين
    
    ```Python
    a = "i can write with java and python and c# and js"
    print(a.count("and")) \#3
    print(a.count("and",0,10)) \#0
    ```
    
      
    
      
    
      
    
- **swapcase()**
    
    ```Python
    a = "moAtaZ"
    b = "MoAtAz"
    print(a.swapcase())
    print(b.swapcase())
    ```
    
    بتحول الحرف الكابتل لاسمول
    
    والاسمول لكابتل
    
      
    
- **startswith()**
    
    بترجع بوليان تايب
    
    هتتشيك اذا كان الاسترينج الي مديهوله بيبدا بكذا ولا لا
    
    ```Python
    i = "i love python"
    print(i.startswith("i"))
    print(i.startswith("m"))
    print(i.startswith("i",2,6))
    ```
    
    ممكن نحددله بدايه ونهايه يتشيك فيهم
    
    الاندكس بتاع النهايه مش محسوب exclusive
    
      
    
      
    
      
    
- **endswith()**
    
    بنتشيك اذا كان الاسترينج ده بينتهي بحاجه حددناها ولا لا
    
    ```Python
    j = "i love python"
    print(i.endswith("i"))
    print(i.endswith("n"))
    print(i.endswith("e",2,6))
    ```
    
      
    
      
    
      
    
- **index()**
    
    بتدور بيها علي ايندكس سابسترينج
    
    ممكن تاخد السابسترينج كارجومينت لوحده
    
    او نسيرش برينج معين ونديله بدايه ونهايه
    
    ```Python
    a = "i love python"
    print(a.index("o"))
    print(a.index("o",4,7))
    ```
    
    عيب الميثود دي انها بترمي ايرور لو الحاجه الي بدور عليها مش موجوده
    
    سواء مش موجوده في الرينج او في الاسترينج كله
    
      
    
      
    
- **find()**
    
    شبه فانكشن ايندكس في الوظيفه
    
    لاكن الفرق هنا انها مش بترمي ايرور
    
    بترجع سالب واحد لو ملقتش القيمه
    
    ```Python
    a = "i love python"
    print(a.find("o"))
    print(a.find("o",4,7))
    ```
    
- **rjust()**
    
    شبه السنتر لاكن بتحط علي ناحيه واحده
    
    اسمها رايت جاستيفاي يبقي بتخليه ييجي ناحيه اليمين يعني بتحط شمال الاسترينج
    
    الديفولت بيكون مسافات ولو عايز حاجه محدده بنباصيها كبراميتر تاني
    
      
    
- **ljust()**
    
    شبه السنتر لاكن بتحط علي ناحيه واحده
    
    اسمها ليفت جاستيفاي يبقي بتخليه ييجي ناحيه الشمال يعني بتحط يمين الاسترينج
    
    الديفولت بيكون مسافات ولو عايز حاجه محدده بنباصيها كبراميتر تاني
    
      
    
- **splitlines()**
    
    لو عندي سترينج علي كذا سطر بترجعلي كل سطر لوحده في ليست
    
    سواء استخدمت التريبل كوت او سلاش ان وخليتهم ينزلو سطور جديده
    
    هيا هتاخد السطور دي وترجعها فليست
    
- **expandtabs**
    
    التاب بتاعت اللغه لو استخدمنا \t
    
    بتكون عدد مسافات معينه
    
    لو عايزين نتحكم فالعدد ده هنستخدم فانكشن الاكسباند ونقوله عايزين التاب تعتبر ككام مسافه
    
    ```Python
    a = "i\tlove\tpython"
    print(a.expandtabs(10))
    
    # i         love      python
    ```
    
- **IS**
    
    عندنا كذا فانكشن بتتشيك وترجع ترو او فولس
    
    istitle() هتتشيك ده بيلتزم بقواعد التايتل ولا لا
    
    isspace() بتتشييك اذا كانت مسافه ولا لا
    
    islower() بتشوف كله سمول ولا لا
    
    isupper() بتشوف كله كابتل ولا لا
    
    isidentifer بتشوف اذا كان بيلتزم بقواعد تسميه الفاريبلز ولا لا
    
    يعني مثلا لو بيبدا برقم او فيه سبيشيال كاركتر كله هيرجع فولس
    
    isalpha() بتتشيك اذا كان الاسترينج كله حروف انجليزي ولا لا يعني مفيش سبيشيال كاركتر او ارقام a-z
    
    isalnum() بتتشيك اذا كان الاسترينج حروف وارقام فقط ولا لا a-z A-Z 0-9
    
      
    
    isnumeric() Return True if the string is a numeric string, False otherwise. A string is numeric if all characters in the string are numeric and there is at least one character in the string
    
    ```Python
    print("124530".isnumeric()) \#true
    print("1245AG30".isnumeric()) \#false
    ```
    
    isdigit() same as isnumeric() function
    
      
    
    -**we need to search about isdecimal() , isprintable() , isascii()**
    
      
    
      
    
      
    
- **join()**
    
    بتاخد اي حاجه من النوع iterable يعني نقدر نترافيرس عليها
    
    وبتلزق العناصر الي فيه وترجعه كاسترينج
    
    بنحدد السيبارتور الي عايزينه وبعدين دوت الميثود ونباصيلها الليست
    
    ```Python
    myList = ["moataz" , "mohammed" , "mohammed"]
    print(", ".join(myList))
    print(" ".join(myList))
    print("-".join(myList))
    
    \#moataz, mohammed, mohammed
    \#moataz mohammed mohammed
    \#moataz-mohammed-mohammed
    ```
    
      
    
      
    
- **replace()**
    
    ```Python
    # replace(Old Value, New Value, Count)
    
    a = "Hello One Two Three One One"
    print(a.replace("One", "1")) \#replace all occurance of One with 1
    print(a.replace("One", "1", 1)) \#replace only 1 occurance of One
    print(a.replace("One", "1", 2)) \#replace two occurance of One
    ```