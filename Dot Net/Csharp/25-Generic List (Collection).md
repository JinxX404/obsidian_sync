
الList  هي النسخه الgeneric من ال arraylist
وهي Strongly Typed
واخده ميزه الاراي ليست في انها dynamic
وميزه الاراي في انها Strong typed

الlist هي type safe
بنحدد الداتا تايب قبل ما نستخدمها 
ومش مضطرين نعمل boxing&unboxing زي الاراي ليست 
لانها مش بتخزنهم كاوبجكت 
لاكن بتخزنهم بالداتا تايب الي حددتها

 `List<T>` equivalent of the [ArrayList](https://www.tutorialsteacher.com/csharp/csharp-arraylist), which implements IList<T>
- It comes under `System.Collections.Generic` namespace.
- `List<T>` can contain elements of the specified type. It provides compile-time type checking and doesn't perform boxing-unboxing because it is generic.
- Elements can be added using the `Add()`, `` `AddRange()` `` methods or collection-initializer syntax.
- Elements can be accessed by passing an index e.g. `myList[0]`. Indexes start from zero.
- `List<T>` performs faster and less error-prone than the `ArrayList`.

