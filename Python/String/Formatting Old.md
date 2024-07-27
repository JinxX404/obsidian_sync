لما كنا بنعمل كونكاتينيشن بعلامه ال+ مكنش بينفع نلزق معاهم انتجر

كانت البلس بتلزق سترينج مع بعض مينفعش اي داتا تايب تاني

دي كانت اول طريقه للكونكاتينيشن

  

تاني طريقه بنستخدم ال placeholder

```Python
%d => number
%s => string
$f => float
```

```Python
name = "moataz"
age = 20

print("my name is %s and i am %d years old" %(name , age))
print("my name is %s and i am %d years old" %("moataz" , age))
print("my name is %s and i am %d years old" %(name , 20))
```

بعد الاسترينج بتاعنا ما يتقفل هنضيف القيم الي هتكون مكان البليسهولدرز

كل الطرق هتنفع سواء هنعوض عنهم بقيم عاديه او بفاريبلز شايله القيم

لو عندنا بليسهولدر واحد مش لازم اقواس

---

لو اتعاملنا مع البليسهولدر كفلوت نامبر

هيطبع 6 اصفار بعد العلامه العشريه

```Python
name = "moataz"
age = 20

print("my name is %s and i am %f years old" %(name , age))
# my name is moataz and i am 20.000000 years old
```

لو عايزين نتحكم فعدد العلامات العشريه هنستخدم الدوت ورقم بعد علامه ال$ زكده هنحدد كام رقم بعد العلامه

```Python
name = "moataz"
age = 20

print("my name is %s and i am %f years old" %(name , age)) 
print("my name is %s and i am %0.1f years old" %(name , age)) 
print("my name is %s and i am %.2f years old" %(name , age)) 
print("my name is %s and i am %.3f years old" %(name , age))

\#my name is moataz and i am 20.000000 years old
\#my name is moataz and i am 20.0 years old
\#my name is moataz and i am 20.00 years old
\#my name is moataz and i am 20.000 years old
```

  

---

بنفس طريقه الفلوت نقدر نحدد عايزين كام حرف من الاسترينج في علامه البليسهولدر

```Python
name = "moataz"
age = 20
print("my name is %0.3s and i am %0.3f years old" %(name , age))
\#my name is moa and i am 20.000 years old
```