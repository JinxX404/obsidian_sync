![[Pasted image 20240730215656.png]]

Collections standardize the way of which the objects are handled by your program. In other words, it contains a set of classes to contain elements in a generalized manner. With the help of collections, the user can perform several operations on objects like the store, update, delete, retrieve, search, sort etc.

متقسمين تقريبا 3 انواع 
كلهم في system namesapce
الsystem.collection ده non-generic type 
الcollection.generic ده النسخه الgeneric من الcollection العادي 
الي موجودين هنا فيه شبههم هنا لاكن type safe 

#### System.Collections.Generic Classes

Generic collection in C# is defined in `System.Collection.Generic` namespace. It provides a generic implementation of standard data structure like linked lists, stacks, queues, and dictionaries. These collections are type-safe because they are generic means only those items that are type-compatible with the type of the collection can be stored in a generic collection, it eliminates accidental type mismatches. Generic collections are defined by the set of interfaces and classes.

| Class name                                                                   | Description                                                                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Dictionary<TKey,TValue>**                                                  | It stores key/value pairs and provides functionality similar to that found in the non-generic Hashtable class.               |
| **[List<T>](https://www.geeksforgeeks.org/c-list-class/)**                   | It is a dynamic array that provides functionality similar to that found in the non-generic ArrayList class.                  |
| **Queue<T>**                                                                 | A first-in, first-out list and provides functionality similar to that found in the non-generic Queue class.                  |
| **SortedList<TKey,TValue>**                                                  | It is a sorted list of key/value pairs and provides functionality similar to that found in the non-generic SortedList class. |
| **Stack<T>**                                                                 | It is a first-in, last-out list and provides functionality similar to that found in the non-generic Stack class.             |
| **[HashSet<T>](https://www.geeksforgeeks.org/c-sharp-hashset-class/)**       | It is an unordered collection of the unique elements. It prevent duplicates from being inserted in the collection.           |
| **[LinkedList<T>](https://www.geeksforgeeks.org/c-sharp-linkedlist-class/)** | It allows fast inserting and removing of elements. It implements a classic linked list.                                      |


#### System.Collections Classes

Non-Generic collection in C# is defined in `System.Collections` namespace. It is a general-purpose data structure that works on object references, so it can handle any type of object, but not in a safe-type manner. Non-generic collections are defined by the set of interfaces and classes.

|Class name|Description|
|---|---|
|**[ArrayList](https://www.geeksforgeeks.org/c-arraylist-class/)**|It is a dynamic array means the size of the array is not fixed, it can increase and decrease at runtime.|
|**[Hashtable](https://www.geeksforgeeks.org/c-hashtable-class/)**|It represents a collection of key-and-value pairs that are organized based on the hash code of the key.|
|**Queue**|It represents a first-in, first out collection of objects. It is used when you need a first-in, first-out access of items.|
|**Stack**|It is a linear data structure. It follows LIFO(Last In, First Out) pattern for Input/output.|


#### System.Collections.Concurrent

It came in `.NET Framework Version 4` and onwards. It provides various threads-safe collection classes that are used in the place of the corresponding types in the `System.Collections` and `System.Collections.Generic` namespaces, when multiple threads are accessing the collection simultaneously. The classes present in this collection are:

|Class name|Description|
|---|---|
|**BlockingCollection**|It provides blocking and bounding capabilities for thread-safe collections that implement  <br>IProducerConsumerCollection.|
|**ConcurrentBag**|It represents a thread-safe, an unordered collection of objects.|
|**ConcurrentDictionary**|It represents a thread-safe collection of key/value pairs that can be accessed by multiple threads concurrently.|
|**ConcurrentQueue**|It represents a thread-safe first in-first out (FIFO) collection.|
|**ConcurrentStack**|It represents a thread-safe last in-first out (LIFO) collection.|
|**OrderablePartitioner**|It represents a particular manner of splitting an orderable data source into multiple partitions.|
|**Partitioner**|It provides common partitioning strategies for arrays, lists, and enumerables.|
|**Partitioner**|It represents a particular manner of splitting a data source into multiple partitions.|


![[Pasted image 20240730221758.png]]
