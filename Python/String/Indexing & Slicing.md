1 - All Data in python is Object

2 - Object Contain Elements

3 - Every Element Has its Own Index

4 - Python Use Zero Based Indexing

5 - Use Square Brackets To Access Elements

6 - Enable Accessing Parts Of Strings , Tuples or Lists

---

```Python
myString = "I Love Python"
print(myString[0]) # Index 0 => I
print(myString[9]) # Index 9 => t

# minus indices used for access elements from end 
print(myString[-1]) # Index -1 => n First Char from End 
print(myString[-6]) # Index -6 => P  6th Char from End
```

في البايثون الانديكسينج نقدر نوصل لعنصر من الاخر او من الاول

في الاول هنوصله بالاندكس زيرو … طبيعي

والاخر هيبدا من سالب واحد

---

**Slicing**

**Syntax is [Start : End] or [Start : End : Steps] , End is exclusive (not included)**

```Python
myString = "I Love Python"
print(myString[2:6]) # Love
print(myString[6:]) # if end is not exist will go until end of string
print(myString[:6]) # if start is not exist will start from zero
print(myString[:]) # if there is no start or end will print whole string
```

```Python
myString = "I Love Python"
print(myString[0::1]) # whole string
print(myString[::1])  # whole string
print(myString[::2])  # ILv yhn
print(myString[::3])  # Io tn
اول برينت حددنا البدايه وسيبنا النهايه فهيوصل للاخر والاتسيب واحد يعني هيمشي خطوه واحده
تاني برينت نفس الاولي محددناش بدايه ولا نهايه فهياخد الاسترينج كله وباستيب واحده
التالته هناخد الاسترينج كله لاكن باتنين ستيب يعني بيمشي خطوتين كل مره ياخد واحده ويسيب واحده
رابع بر ينت بيمشي تلت خطوات يعني بياخد واحده ويسكيب اتنين
```