اللغه بتعتبر الباك سلاش \ سبيشيال كاركتر

فبنستخدمه فاكتر من حاجه

```Python
# ----------------------------
# Escape Sequences Characters
# \b => Back Space
# \newline => Escape New Line + \
# \\ => Escape Back Slash
# \' => Escape Single Quotes
# \" => Escape Double Quotes
# \n => Line Feed
# \r => Carriage Return
# \t => Horizontal Tab
# \xhh => Character Hex Value
# ----------------------------

# Back Space
print("Hello\bWorld")  # Will Remove o 

# Escape New Line + Back Slash
print("Hello \
I Love \
Python")

# Escape Back Slash
print("I Love Back Slash \\")

# Escape Single Quote
print('I Love Single Quote \'Test\' ')

# Escape Double Quotes
print("I Love Double Quotes \"Test\" ")

# Line Feed
print("Hello World\nSecond Line")

# Carriage Return
print("123456\rAbcde")

# Horizontal Tab
print("Hello\tPython")

# Character Hex Value
print("\x4F\x73")
```

\b بتمسح الحرف الي قبلها

مثلا hello\b world هتمسح اخر حرف قبلها

---

لو عايز انزل سطر جديد بالاسترينج بستخدم الباك سلاش

يعني في تاني مثال لو نزلت بالاسترينج كل كلمه علي سطر جديد هو بيعامل كل سطر كانه ستيتمنت جديده

ف الباك سلاش بتلزقهم فبعض وتعاملهم كسطر واحد

---

تالت كيز

لو انا عايز اطبع الباك سلاش كباك سلاش في الجمله بتاعتي بستخدمها مرتين علشان اعرفه اني عايز اطبعها

لان الباك سلاش واحده بتدل علي سبيشيال كاركتر

---

رابع وخامس كيز

لو عايز استخدم ال” “ او ‘ ‘ في الكود بستخدم قبل كل واحده باك سلاش علشان اعرفه اني عايز اطبعها

---

سادس كيز بستخدم \n علشان انزل سطر جديد

---

سابع كيز carriage return

"123456\rAbcde"

بتشوف العدد الي بعد السلاس أر

وتمسح من الي قبله نفس العدد

يعني الي بعده 5 كاركتر فهتمسح من الي قبله 5 كاركتر وتحط ال5 دول مكانهم

```Python
print("123456\rA") \#A23456
print("123456\rAb") \#Ab3456
print("123456\rAbc") \#Abc456
print("123456\rAbcd") \#Abcd56
print("123456\rAbcde") \#Abcde6
print("123456\rAbcdef") \#Abcdef
print("123456\rAbcdefg") \#Abcdefg
print("123456\rAbcdefgh") \#Abcdefgh
```

---

\t بيسيب مسافه قد التاب بتاعت الجهاز

تقريبا 4 مسافات من بتوع السبيس الي في الكيبورد

---

اخر كيز

بنحط سلاش اكس وبعده الهكساديسمل بتاعت رقم فهتطبعه