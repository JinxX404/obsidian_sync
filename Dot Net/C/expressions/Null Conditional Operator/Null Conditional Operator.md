null معناها حجزت ادينتفاير في الاستاك لاكن مشاورتش علي حاجه

وتفرق عن ان الاسترينج فاضي

لان معني انه فاضي يعني محجوزله مكان لاكن محطيناش حاجه لاكن محجوزه

لاكن النل مش محجوزه اصلا

![[/Untitled 4.png|Untitled 4.png]]

---

The null conditional operator (`?.`) is a convenient feature introduced in C# 6.0 that allows you to safely access properties, methods, and indexers on an object without worrying about potential null reference exceptions. It provides a concise way to perform a null check and access a member in a single operation.

Here's how the null conditional operator works:

1. **Accessing Properties or Fields:**  
    You can use the  
    `?.` operator to access properties or fields of an object safely. If the object is `null`, the expression returns `null` instead of throwing a `NullReferenceException`. If the object is not `null`, it accesses the property or field as usual.
    
    ```C#
    string name = person?.Name;
    ```
    
    In this example, if `person` is `null`, `name` will be assigned `null`, and if `person` is not `null`, it will assign the value of the `Name` property.
    
2. **Invoking Methods:**  
    The null conditional operator can also be used to invoke methods on an object. If the object is  
    `null`, the method call is skipped, and the result is `null`.
    
    ```C#
    int? length = text?.Length;
    ```
    
    Here, if `text` is `null`, `length` will be assigned `null`, and if `text` is not `null`, it will assign the length of the string.
    
3. **Indexing Arrays or Collections:**  
    You can use the null conditional operator with arrays, collections, or indexers in the same way.  
    
    ```C#
    int? element = numbers?[0];
    ```
    
    If `numbers` is `null`, `element` will be assigned `null`, and if `numbers` is not `null`, it will assign the first element of the array.
    

The null conditional operator is particularly useful when you're dealing with complex object hierarchies, and you want to avoid writing multiple nested null checks. It simplifies code and makes it more robust by gracefully handling null references.

Here's a full example:

```C#
Person person = GetPerson(); // GetPerson() may return null

// Using the null conditional operator to access properties
string name = person?.Name; // Safe access to Name property

// Using the null conditional operator to invoke a method
int? age = person?.GetAge(); // Safe method invocation, age can be null

// Using the null conditional operator with indexing
int? firstNumber = person?.Numbers?[0]; // Safe access to the first element
```

In this example, if `GetPerson()` returns `null`, the null conditional operator ensures that no exceptions are thrown, and the variables are assigned `null`.

بتتشيك الاول اذا كان نل ولا لا

لو ايوه هترجع نل لو لا هترجع القيمه

علشان منخليهوش يرمي اكسبشن

---

The usage of `int?` is to declare a **nullable integer**, and it is directly related to the concept of the null conditional operator (`?.`). Let me explain:

In C#, most value types like `int`, `double`, `bool`, etc., cannot be assigned the value `null`. They must always have a valid value. However, there are scenarios where you want to represent the absence of a value, and that's where nullable value types come into play.

Here's how it works:

1. `**int?**` **(Nullable Integers):**
    - `int?` is a shorthand for `Nullable<int>`. It's a way to declare an integer variable that can have either a valid integer value or be `null`.
    - For example, `int? age = null;` declares a nullable integer `age` with no initial value, meaning it's null by default.
2. **Usage with Null Conditional Operator:**
    - The null conditional operator (`?.`) returns `null` if any part of the expression evaluates to `null`.
    - When you use the null conditional operator with a nullable integer, it ensures that if any part of the expression results in `null`, the whole expression will be `null`.

Here's an example:

```C#
int? length = text?.Length;
```

In this line, `text?.Length` uses the null conditional operator to check if `text` is `null`. If `text` is `null`, then `length` will be assigned `null` because it's a nullable integer.

Using `int?` in this context allows you to handle situations where you might not have a valid integer value (e.g., when accessing the `Length` property of a null string), and you can safely represent the absence of a value as `null`. This is especially useful when dealing with database records, user input, or other cases where data may or may not be present.