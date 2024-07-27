```Python
{:s} => String
{:d} => Number
{:f} => Float
```

في الطرق الجديده للفورمات بنستخدم ميثود فورمات

```Python
name = "moataz"
age = 20
print("my name is {} and i am {} years old".format(name,age))
\#my name is moataz and i am 20 years old
```

ال { } يعتبرو كانهم بليسهولدر

وبعدين دوت فورمات واباصيله القيم

لو عايز الديسمل يظهر كانه فلوت بستخدم الكولون اف جوه الكيرلي بريسيس

ونقدر نحدد عايزين كام ديجيت بعد العلامه

```Python
name = "moataz"
age = 20
print("my name is {} and i am {:f} years old".format(name,age))
print("my name is {:.3s} and i am {:0.2f} years old".format(name,age))
\#my name is moataz and i am 20.000000 years old
\#my name is moa and i am 20.00 years old
```

---

---

---

**numeric format**

```Python
price = 655215689231
print("the price is {:d}".format(price))
print("the price is {:_d}".format(price))
print("the price is {:,d}".format(price))

the price is 655215689231
the price is 655_215_689_231
the price is 655,215,689,231
```

بعد الكولون نقدر نحدد عايزين ايه نعمل بيه فورمات للرقم

هيروح بعد كل 3 ارقام ويحط بينهم العلامه

---

لو عايز احدد انا عايز اطبع انهي عناصر في انهي مكان من ال{ }

نقدر نحط جواهم اندكس

```Python
one , two , three = 1 , 2 , 3
print("first one is {} second one is {} third one is {}".format(one,two,three))
print("first one is {0} second one is {2} third one is {1}".format(one,two,three))
print("first one is {2} second one is {1} third one is {0}".format(one,two,three))
print("first one is {2} second one is {0} third one is {1}".format(one,two,three))
first one is 1 second one is 2 third one is 3
first one is 1 second one is 3 third one is 2
first one is 3 second one is 2 third one is 1
first one is 3 second one is 1 third one is 2
```

ف هحدد جوه القوسين الاندكس الي عايزه يتطبع هنا

ولو عايز اكمل فورماتينج سواء هحط ديسمل او فلوت هحط الكولون واكمل فورمات

```Python
print("first one is {0:.2f} second one is {2:.3f} third one is {1:d}".format(one,two,three))
first one is 1.00 second one is 3.000 third one is 2
```

---

---

فيه طريقه جديده في البايثون ما بعد 3.6

نقدر نفورمات بيها

```Python
name = "moataz"
age = 20
print("my name is {name} and i am {age} years old") 
print(f"my name is {name} and i am {age} years old")
my name is {name} and i am {age} years old
my name is moataz and i am 20 years old
```

اول برينت هتعتبرها سترينج عادي وتطبعها

تاني واحده هنضيف الf قبل الاسترينج علشان نحدد انه فورماتينج