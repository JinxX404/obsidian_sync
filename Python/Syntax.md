**python file extension is .py**

-if we need to run python file from terminal we use `python filename`

---

if we have more than statement in the same line then we need to use semicolon

```Python
print("Hello"); print("World")
```

if each line have one statement then we don’t need to semicolon

```Python
print("Hello")
print("World")
```

---

python syntax depend on indentation to detect bloacks

بيتعامل مع الاندينتايشن ويحدد بيها البلوكس

يعني لو فيه جمله والجمله الي بعدها معمولها مسافه يعتبر الجمله التانيه تشايلد للاولي

```C#
print("Hello") 
  print("World")
```

هيعتبر التانيه ابن الاولي

---
```python
score = int(input("Score: "))

  if 90 <= score <= 100:
      print("Grade: A")
  elif 80 <= score < 90:
      print("Grade: B")
  elif 70 <= score < 80:
      print("Grade: C")
  elif 60 <= score < 70:
      print("Grade: D")
  else:
      print("Grade: F")
```نقدر نعمل كده لو عندنا رينج عايزين نتشيك فيه بدلا من الاند والاور