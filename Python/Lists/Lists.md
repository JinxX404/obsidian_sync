الليست هيا شبه الاراي في لغات تاني

والليست في البايثون مش هيا الاراي

لان عندنا اراي لاكن بتحتاج مكتبات

ونقدر نحط فيها اي نوع داتا تايب وممكن تشيل انواع مختلفه فنفس الوقت

الليست نقدر نعدل عليها

**ونقدر نعمل عليها كل عمليات الاسترينج (كلها)**

```Java
# -----------------------------
# -- Lists --
# -----------
# [1] List Items Are Enclosed in Square Brackets
# [2] List Are Ordered, To Use Index To Access Item
# [3] List Are Mutable => Add, Delete, Edit
# [4] List Items Is Not Unique
# [5] List Can Have Different Data Types
# -----------------------------

myAwesomeList = ["One", "Two", "One", 1, 100.5, True]

print(myAwesomeList)  # Whole List
print(myAwesomeList[1])  # "Two"
print(myAwesomeList[-1])  # True
print(myAwesomeList[-3])  # 1

print(myAwesomeList[1:4])  # ['Two', 'One', 1]
print(myAwesomeList[:4])  # ['One', 'Two', 'One', 1]
print(myAwesomeList[1:])  # ['Two', 'One', 1, 100.5, True]

print(myAwesomeList[::1])  # ['One', 'Two', 'One', 1, 100.5, True]
print(myAwesomeList[::2])  # ['One', 'One', 100.5]

print(myAwesomeList)
# myAwesomeList[1] = 2
# myAwesomeList[-1] = False
myAwesomeList[0:3] = ["A"] #هيشيل من 0ل2 وهيحط عنصر واحد فقط,يعني يعتبر مسح منها عنصرين وضايف عنصر
print(myAwesomeList)
```

---

---

[[Python/Lists/Methods|Methods]]