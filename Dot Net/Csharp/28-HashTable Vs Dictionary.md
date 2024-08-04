In C#, `Hashtable` and `Dictionary<TKey, TValue>` are both collections that store key-value pairs, but they have some key differences:

### `Hashtable`

- **Type Safety**: `Hashtable` is not type-safe. It stores keys and values as `object`, which means you need to cast them to the correct type when retrieving them.
  
  ```csharp
  Hashtable hashtable = new Hashtable();
  hashtable.Add("key1", 1);
  int value = (int)hashtable["key1"];
  ```

- **Performance**: `Hashtable` is generally slower compared to `Dictionary<TKey, TValue>` because it uses boxing and unboxing due to its use of `object`.

- **Order**: It does not guarantee the order of elements.

- **Thread Safety**: `Hashtable` is thread-safe for static methods, but it’s not inherently thread-safe for instance methods. For concurrent access, consider using `ConcurrentDictionary`.

### `Dictionary<TKey, TValue>`

- **Type Safety**: `Dictionary<TKey, TValue>` is type-safe. It enforces the types of keys and values at compile time.

  ```csharp
  Dictionary<string, int> dictionary = new Dictionary<string, int>();
  dictionary.Add("key1", 1);
  int value = dictionary["key1"];
  ```

- **Performance**: `Dictionary<TKey, TValue>` is generally faster because it avoids boxing and unboxing and uses a more optimized hashing algorithm.

- **Order**: It does not guarantee the order of elements. However, if you need an ordered collection, you can use `SortedDictionary<TKey, TValue>`.

- **Thread Safety**: `Dictionary<TKey, TValue>` is not thread-safe. For concurrent scenarios, you can use `ConcurrentDictionary<TKey, TValue>`.

### When to Use Each

- **Use `Hashtable`** if you need to work with legacy code or require a non-generic collection. However, for new development, it is generally recommended to use `Dictionary<TKey, TValue>` due to its type safety and performance benefits.

- **Use `Dictionary<TKey, TValue>`** for most cases where you need a dictionary-like collection. It’s more modern, type-safe, and usually more efficient.


|   |   |
|---|---|
|****Hashtable****|****Dictionary****|
|A [Hashtable](https://www.geeksforgeeks.org/c-sharp-hashtable-with-examples/) is a non-generic collection.|A [Dictionary](https://www.geeksforgeeks.org/c-sharp-dictionary-with-examples/) is a generic collection.|
|Hashtable is defined under System.Collections namespace.|Dictionary is defined under System.Collections.Generic namespace.|
|It doesn’t maintain the order of stored values.|It always maintain the order of stored values.|
|In Hashtable, there is no need to specify the type of the key and value.|In Dictionary, you must specify the type of key and value.|
|The data retrieval is slower than Dictionary due to boxing/ unboxing.|The data retrieval is faster than Hashtable due to no boxing/ unboxing.|
|In Hashtable, if you try to access a key that doesn’t present in the given Hashtable, then it will give null values.|In Dictionary, if you try to access a key that doesn’t present in the given Dictionary, then it will give error.|
|It is thread safe.|The Dictionary<TKey, TValue> class in C# is not inherently thread-safe. For multi-threaded scenarios, it’s recommended to use ConcurrentDictionary<TKey, TValue> which provides thread-safe operations.|

|`Dictionary`|`Hashtable`|
|---|---|
|**Generic**|**Non-Generic**|
|Needs **own thread synchronization**|Offers **thread safe** version through **`Synchronized()`** method|
|Enumerated item: **`KeyValuePair`**|Enumerated item: **`DictionaryEntry`**|
|Newer (> **.NET 2.0**)|Older (since **.NET 1.0**)|
|is in **System.Collections.Generic**|is in **System.Collections**|
|Request to non-existing key **throws exception**|Request to non-existing key **returns null**|
|potentially a bit **faster for value types**|**bit slower** (needs boxing/unboxing) for value types|
الenumerated item يعني كل عنصر جوه الداتا ستراكشر دي (كل pair)
هيكون من نوع KeyValuePair في الdictionary 
ومن نوع DictionaryEntry في hashtable


الdictionary اسرع لانه مش محتاج يعمل boxing&unboxing


## Similarities:

- Both are internally **hashtables** == fast access to many-item data according to key
- Both need **immutable and unique keys**
- Keys of both need own **`GetHashCode()`** method





#
https://stackoverflow.com/questions/301371/why-is-dictionary-preferred-over-hashtable-in-c