Expression-bodied members provide a minimal and concise syntax to define properties and methods. It helps to eliminate boilerplate code and helps writing code that is more readable. The expression-bodied syntax can be used when a member’s body consists only of one expression. It  
uses the  
**=>**(f_at arrow_) operator to define the body of the method or property and allows getting rid of curly braces and the _return_ keyword. The feature was first introduced in C# 6.

---

**Expression-bodied Members**: Expression-bodied members  
are used for defining members (methods or properties) of a class, and  
they are particularly useful for defining simple, one-liner methods or  
properties in a more concise way.  

---

  

> [!info] Expression-Bodied Members in C# - GeeksforGeeks  
> A Computer Science portal for geeks.  
> [https://www.geeksforgeeks.org/expression-bodied-members-in-c-sharp/](https://www.geeksforgeeks.org/expression-bodied-members-in-c-sharp/)  

> [!info] Expression-bodied members - C# Programming Guide - C#  
> Learn about expression-bodied members.  
> [https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members)  

---

The code snippet `int GetAge(Person person) => person.Age;` is using a concise and modern syntax available in C# called expression-bodied members. This syntax is used to define methods and properties with a single expression that returns a value. Here's why this style of method definition can be beneficial:

1. **Conciseness**: Expression-bodied members allow you to define simple methods in a compact and clear manner. The code is more concise and easier to read, especially for short methods that consist of just a single expression.
2. **Readability**: For straightforward methods like property getters, accessors, or simple transformations, the expression-bodied syntax can improve code readability by making the purpose of the method more obvious and reducing unnecessary boilerplate code.
3. **Saves Typing**: It reduces the amount of code you need to write compared to traditional method definitions, saving keystrokes and making your code more efficient to write and maintain.
4. **Consistency**: It provides a consistent way to define methods and properties, aligning with C#'s focus on making code more expressive and less verbose.
5. **Maintainability**: For methods that don't have complex logic, the concise syntax can make the code easier to maintain because there are fewer lines to review and understand.

However, it's important to note that expression-bodied members are most suitable for short, simple methods that can be expressed in a single line. For more complex methods with multiple statements or branching logic, the traditional method syntax (using curly braces `{ ... }`) is typically more appropriate.

In summary, the use of expression-bodied members like `int GetAge(Person person) => person.Age;` is a matter of code style and preference. It can be particularly beneficial for small, straightforward methods, improving code readability and maintainability.

---