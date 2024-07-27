**Syntax ⇒ variableName = value**

we don’t need to set data type explicity

**Name Convention and Rules:**

1- Can Start With (a-z A-Z) or Underscore

2- You cannot start with Num Or Special Character

3- Can Include (0-9) Or Underscore inside variable

4- Cannot include special character

5- Python is Case sensitive

---

**Python is Dynamically Types Language**

we can change variable type during run tim**e**

---

**help(”keywords”) is a line display reserved words in python**

```Python
False               break               for                 not
None                class               from                or
True                continue            global              pass
__peg_parser__      def                 if                  raise
and                 del                 import              return
as                  elif                in                  try
assert              else                is                  while
async               except              lambda              with
await               finally             nonlocal            yield
```

The `help()` function in Python is used to display documentation about built-in Python objects, modules, functions, and methods. It can be used to get information about how to use a particular object or function, what arguments it takes, and what it returns. You can also use it to get information about modules and their contents.

The syntax for using the `help()` function in Python is:

help([object])

Where `object` is the object, module, function, or method that you want to get help for. If you don't specify an object, the `help()` function will start an interactive help session.

---

assign multiple values in same line

```Python
a, b, c = 1, 2, 3
print(a) //1
print(b) //2
print(c) //3
```