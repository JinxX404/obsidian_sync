مش كل الداتا تايب اقدر اكسس جزء معين منهم بايندكس

اقدر اعمل كده مع الاسترينج مثلا لانه اراي اوف كاركتر

لاكن مقدرش اعمل كده مع الاسترينج واقوله هاتلي اندكس رقم معين

  

بنستخدم الاندكسر امتي؟

لما يكون عندي اي كائن بيتكون من اجزاء بقدر استخدم عليه الاندكسر

  

An indexer allows an instance of a class or struct to  
be indexed as an array. If the user will define an indexer for a class, then the class will behave like a virtual array. Array access operator i.e (  
**[ ]**) is used to access the  
instance of the class which uses an indexer. A user can retrieve or set the indexed value without pointing an instance or a type member.  
Indexers are almost similar to the  
[**Properties**](https://www.geeksforgeeks.org/c-properties/).

_The main difference between Indexers and_ [_Properties_](https://www.geeksforgeeks.org/c-properties/) is that the [accessors](https://www.geeksforgeeks.org/c-properties/) of the Indexers will take parameters.

---

**an indexer allows you to access elements of a class or struct using an index, similar to how you access elements of an array. Indexers are useful when you want to provide custom access to the elements of your class, such as a collection of objects.**

---

[https://www.geeksforgeeks.org/c-sharp-indexers/](https://www.geeksforgeeks.org/c-sharp-indexers/)

---

اقدر اعمل انديكسر علي **One Dimensional Indexer** & [**MultiDimensional Indexers**](https://www.geeksforgeeks.org/c-multidimensional-indexers/)

---

types:

1. **Multiple Index Parameters**: Indexers can have multiple parameters, allowing for more complex  
    indexing scenarios. You can define an indexer with multiple parameters  
    to access elements based on different criteria.  
    
2. **Indexer Overloading:** Similar to methods, indexers can be overloaded in C#. This means you  
    can define multiple indexers with different parameter types or counts,  
    providing different ways to access elements in the class or struct.  
    
3. **Read-Only Indexers:** By omitting the set accessor in the indexer declaration, you can create read-only indexers. This restricts the ability to modify elements  
    through the indexer, allowing only the retrieval of values.  
    
4. **Implicit vs. Explicit Interface Implementation:** Indexers can be implemented implicitly or explicitly when defined as  
    part of an interface. Implicit implementation is used when the indexer  
    is defined within the class itself, while explicit implementation is  
    used when the indexer is implemented explicitly to resolve any naming  
    conflicts.  
    
5. **Indexers in Collections:** Indexers are commonly used in collection classes, such as dictionaries, lists,  
    and arrays. They provide a convenient way to access and manipulate  
    elements within these collections based on an index or key.  
    
6. **Indexers in Custom Classes:** Indexers can be implemented in custom classes to provide customized  
    access to class members based on an index. This allows for more  
    intuitive and expressive interaction with instances of the class.