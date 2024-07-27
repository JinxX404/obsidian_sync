# [1] Tuple Items Are Enclosed in Parentheses

# [2] You Can Remove The Parentheses If You Want

# [3] Tuple Are Ordered, To Use Index To Access Item

# [4] Tuple Are Immutable => You Can’t Add or Delete

# [5] Tuple Items Is Not Unique can have repeated values

# [6] Tuple Can Have Different Data Types

# [7] Operators Used in Strings and Lists Available In Tuples

  

```Java
# Tuple Syntax & Type Test
# with or without ( )
myAwesomeTupleOne = ("Osama", "Ahmed")
myAwesomeTupleTwo = "Osama", "Ahmed" 

print(myAwesomeTupleOne)
print(myAwesomeTupleTwo)

print(type(myAwesomeTupleOne)) \#tuple
print(type(myAwesomeTupleTwo)) \#tuple

# Tuple Indexing

myAwesomeTupleThree = (1, 2, 3, 4, 5)
print(myAwesomeTupleThree[0])
print(myAwesomeTupleThree[-1])
print(myAwesomeTupleThree[-3])

# Tuple Assign Values

myAwesomeTupleFour = (1, 2, 3, 4, 5)

# myAwesomeTupleFour[2] = "Three" # we cannot assign because tuple is immutable

# print(myAwesomeTupleFour) # 'tuple' object does not support item assignment

# Tuple Data

myAwesomeTupleFive = ("Osama", "Osama", 1, 2, 3, 100.5, True)
print(myAwesomeTupleFive[1])
print(myAwesomeTupleFive[-1])
```

لو هنعرف التابل بعنصر واحد هيشوفه كانه سترينج

```Python
myTuple1 = ("Osama")
myTuple2 = "Osama"

print(type(myTuple1)) \#Str
print(type(myTuple2)) \#Str
```

علشان نعرفه انه تابل بنحط بعده ,

```Python
myTuple1 = ("Osama",)
myTuple2 = "Osama",

print(type(myTuple1)) \#tuple
print(type(myTuple2)) \#tuple
```

---

## Concatenation

```Python
mytuple = ("apple", "banana", "cherry")
mytuple2 = ("orange", "mango", "grapes")
c = mytuple +("5","6")+ mytuple2
print(c)
```

  

---

ممكن نضرب الليست فرقم فهيكرر الليست ده بالي جواها

تنفع ليست او سترينج او تابل

```Python
# Tuple, List, String Repeat (*)

myString = "Osama"
myList = [1, 2]
myTuple = ("A", "B")

print(myString * 6)\#OsamaOsamaOsamaOsamaOsamaOsama
print(myList * 6)#[1, 2, 1, 2, 1, 2, 1, 2, 1, 2, 1, 2]
print(myTuple * 6)#('A', 'B', 'A', 'B', 'A', 'B', 'A', 'B', 'A', 'B', 'A', 'B')
```

---

ممكن نوزع تابل علي فاريبلز

الاندرسكور معناها هياجنور الرقم التالت

لو 3 عناصر نقسمهم علي 3

4 علي 4 وهكذا

```Python
# Tuple Destruct

a = ("A", "B", 4, "C")

x, y, _, z = a

print(x)\#A
print(y)\#B
print(z)\#C
```