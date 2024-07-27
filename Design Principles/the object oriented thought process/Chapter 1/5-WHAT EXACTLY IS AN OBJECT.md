**Objects** are the **building blocks** of an OO program. A program that uses OO technology is basically a collection of objects. To illustrate, let’s consider that a corporate system contains objects that represent employees of that company. Each of these objects is made up of the data and behavior

**Object Data**
	The data stored within an object **represents the state of the object**. In OO programming terminology, this data is called attributes.
	-employee attributes could be Social Security numbers, date of birth, gender, phone number, and so on.
	-The attributes contain the information that differentiates between the various objects.

---

**Object Behaviors**
	The behavior of an object represents what the object can do.
	In procedural languages the behavior is defined by procedures, functions, and subroutines. In OO programming terminology, these behaviors are contained in methods, and you invoke a method by sending a message to it. In our employee example, consider that one of the behaviors required of an employee object is to set and return the values of the various attributes. Thus, each attribute would have corresponding methods, such as setGender() and getGender(). In this case, when another object needs this information, it can send a message to an employee object and ask it what its gender is.


**Getters and Setters** 
	The concept of getters and setters supports the concept of data hiding. Because other objects should not directly manipulate data within another object, the getters and setters provide controlled access to an object's data. Getters and setters are sometimes called accessor methods and mutator methods, respectively.