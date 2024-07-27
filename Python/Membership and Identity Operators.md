[Python Membership and Identity Operators - GeeksforGeeks](https://www.geeksforgeeks.org/python-membership-identity-operators-not-not/)

Python offers two membership operators to check or validate the membership of a value. It tests for membership in a sequence, such as strings, lists, or tuples. 

**in operator:** The ‘in’ operator is used to check if a character/ substring/ element exists in a sequence or not. Evaluate to True if it finds the specified element in a sequence otherwise False.

**The average time complexity of the ‘in’ operator for lists is O(n). It becomes slower as the number of elements increases.**

**The average time complexity of the ‘in’ operator for sets is O(1). It does not depend on the number of elements.**

**For dictionaries, the keys in the dictionary are unique values like set. So the execution is same as the set. Whereas the dictionary values can be repeated as in a list. So the execution of ‘in’ for values() is same as lists.**


**‘not in’ operator-** Evaluates to true if it does not finds a variable in the specified sequence and false otherwise.


----
### **Identity operators**

Identity operators are used to compare the objects if both the objects are actually of the same data type and share the same memory location.  
There are different identity operators such as 

**‘is’ operator –** Evaluates to True if the variables on either side of the operator point to the same object and false otherwise.

**‘is not’ operator:** Evaluates True if both variables are not the same object.

```python
x = ["Geeks", "for", "Geeks"]
y = ["Geeks", "for", "Geeks"]
z = x

# Returns False because z is the same object as x
print(x is not z)

# Returns True because x is not the same object as y,
# even if they have the same content
print(x is not y)

# To demonstrate the difference between "is not" and "!=":
# This comparison returns False because x is equal to y
print(x != y)

```

