we use plus “+” symbol to concat two strings or more

we can use single or double quote for string

---

if we don’t need to use escape sequences char to escape single quote in string we use opposite one

```Python
print("this is single quote 'test'") \#this is single quote 'test'
print('this is single quote "test"') \#this is single quote "test"
```

---

we can print on multiple lines without using escape sequences , using triple single or multiple quotes

triple single or multiple makes escape for special char \ or “ “ or ‘ ‘

only escapes \ if there is strings after it , if there is no string (in last of line) will ignore that new line

```Python
print("""this is
multiple
lines 
code
""")
print('''this is
multiple
lines 
code
''')

\#output
this is
multiple
lines
code

this is
multiple
lines
code
#############################################
print("""this is
multiple \
lines 
code
""")
\#output is , because \ ignored that new line beacuse it place in last of line
this is
multiple lines
code
```

---

---

[[Indexing & Slicing]]

[[Python/String/Methods]]

[[Formatting Old]]

[[Formatting New]]