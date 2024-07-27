**First class** objects in a language are handled uniformly throughout. They may be stored in data structures, passed as arguments, or used in control structures. A programming language is said to support first-class functions if it treats functions as first-class objects. Python supports the concept of First Class functions.

**Properties of first class functions:**

- A function is an instance of the Object type. 
- You can store the function in a variable.
- You can pass the function as a parameter to another function.
- You can return the function from a function.
- You can store them in data structures such as hash tables, lists, …

 **1. Functions are objects:** Python functions are first class objects. In the example below, we are assigning function to a variable. This assignment doesn’t call the function. It takes the function object referenced by shout and creates a second name pointing to it, yell.

```python
# Python program to illustrate functions 
# can be treated as objects 
def shout(text): 
     return text.upper() 

print (shout('Hello')) 

yell = shout 

print (yell('Hello')) 
```

الفانكشن لما بحطها جوه فاريبل انا كده مش بناديها
لاكن بحط الريفرنس بتاع الفانكشن جوه الفاريبل ده
يعني لما اسندت فانكشن shout 
جوه yell
معناها ان الادريس بتاع الفانكشن shout 
بقي متخزن في yell 
يعني yell حاليا بيشاور علي الفانكشن زيه زي الفانكشن الاصليه
وبالتالي اقدر انادي الفانكشن من الفاريبل لانه فالاصل بيشاور علي نفس الفانكشن



2 -Functions can be passed as arguments to other functions: Because functions are objects we can pass them as arguments to other functions. Functions that can accept other functions as arguments are also called higher-order functions. In the example below, we have created a function **greet** which takes a function as an argument.
```python
# Python program to illustrate functions 
# can be passed as arguments to other functions 
def shout(text): 
	return text.upper() 

def whisper(text): 
	return text.lower() 

def greet(func): 
	# storing the function in a variable 
	greeting = func("""Hi, I am created by a function 
					passed as an argument.""") 
	print (greeting) 

greet(shout) 
greet(whisper) 
```
يعني اقدر اباصي الفانكشن ك اريجومنت لفانكشن تانيه 
هنا فانكشن الجرييت بتستقبل فانكشن وبتخزنها في فاريبل 
الفاريبل ده هيكون فيه الريتيرن بتاع الفانكشن الي هتتنفذ

يعني لما انادي الجرييت ب شاوت هيروح ياخد الشاوت وينفذها ويحط الريتيرن في فاريبل جرييتينج

- Use `greeting = shout("something")` when you want to immediately execute the `shout` function with a specific argument and store the result (uppercase text) for later use.
- Use `yall = shout` when you want to refer to the `shout` function itself for later execution. You might then call `yall("something else")` to use the function with a different argument.
الفرق بين المثالين 
انه فالمثال الاول انا منفذتش الفانكشن لاني مباصتش حاجه 
لاكن عملت ريفرنس للفانكشن جوه الفاريبل

المثال التاني انا نفذت الفانكشن والريتيرن فاليو شيلتها ففاريبل تاني وبعدين طبعته


**3. Functions can return another function:** Because functions are objects we can return a function from another function. In the below example, the create_adder function returns adder function.
```python
# Python program to illustrate functions

# Functions can return another function

  

def create_adder(x):

    def adder(y):
        return x+y
        
    return adder

  
add_15 = create_adder(15)
print (add_15(10))
```

الفانكشن تقدر تعمل ريتيرن لفانكشن تاني
فانكشن كرييت اددر بتاخد فاريبل فاول مره اناديها وبتشيله جواها
 وبتعمل فانكشن تاني اسمها اددر والفانكشن دي بتعمل وظيفة لاكن مش هستخدمها لاني مناديتهاش 
 فاخر الكرييت اددر هعمل ريتيرن للادر فانكشن (الي لسه مستخدمتهاش)
كده الريتيرن الي هيتخزن في add15 
هو اصلا الريفرنس بتاع فانشكن ادر يعني اقدر اناديها من خلال ادد15 فاريبل

لما ناديتها وباصيت ليها قيمه 10 
هتاخدها كارجومنت للاددر فانكشن 
هتكون فاكره القيمه القديمه من اخر مره ناديت فيها الكرييت اددر  
وهتاخد القيمتين وتجمعهم وترجعهم

نفس فكرة المثال ده لاكن استخدم الفانكشن الي جوه ك لامدا اكسبريشن مش بلوك كامل 
```python
def myfunc(n):
  return lambda a : a * n

mydoubler = myfunc(2)
mytripler = myfunc(3)

print(mydoubler(11)) 
print(mytripler(11))
```
فالاول هنادي الفانكشن بقيمه معينه وهتخزنها جواها
تاني مره لما اجي استخدم mydoubler 
واباصيله اي حاجه هيستخدم القيمه القديمه الي باصيتها من الي فاتت ويعمل بيها العمليه 

دي شكل الفانكشن بعد ما عدلنها للشكل البلوك 
```python
def myfunc(n):
  def mult(a):
    return a*n

  return mult

mydoubler = myfunc(2)
mytripler = myfunc(3)

print(mydoubler(11))
print(mytripler(11))
```

[First Class functions in Python - GeeksforGeeks](https://www.geeksforgeeks.org/first-class-functions-python/)
[Python Inner Functions - GeeksforGeeks](https://www.geeksforgeeks.org/python-inner-functions/)
