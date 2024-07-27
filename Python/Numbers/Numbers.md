**we have three types of numbers in python**

1- Int

2- Float

3- Complex (imge-real)

---

we can convert from int to float or complex

and from float to int or complex

we cannot convert complex to any type

---

complex number we can separate between img and real parts

```Python
myComplexNumber = 5+6j
print("The Whole Number {}".format(myComplexNumber))
print("The Real Part {}".format(myComplexNumber.real))
print("The Imaginary Number {}".format(myComplexNumber.imag))

The Whole Number (5+6j)
The Real Part 5.0
The Imaginary Number 6.0
```

---

convert from int to float and complex

```Python
i = 5;
print(float(i))
print(complex(i))

5.0
(5+0j)
```

convert from float to int and complex

```Python
j = 8.5;
print(int(j))
print(complex(j))

8
(8.5+0j)
```

---

[[Arithmetic Operators]]