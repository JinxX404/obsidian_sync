The `Dictionary<TKey, TValue>` is a generic collection that stores key-value pairs in no particular order.

## Dictionary Characteristics

- `Dictionary<TKey, TValue>` stores key-value pairs.
- Comes under `System.Collections.Generic` namespace.
- Implements [IDictionary<TKey, TValue>](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.idictionary-2?view=netframework-4.8) interface.
- Keys must be unique and cannot be null.
- Values can be null or duplicate.
- Values can be accessed by passing associated key in the indexer e.g. `myDictionary[key]`
- Elements are stored as [KeyValuePair<TKey, TValue>](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.keyvaluepair-2?view=netframework-4.8) objects.


```C#
IDictionary<int, string> numberNames = new Dictionary<int, string>();
		numberNames.Add(1,"One"); //adding key/value using the Add() method
		numberNames.Add(3,"Three");
		numberNames.Add(2,"Two");
		
		foreach(KeyValuePair<int, string> kvp in numberNames)
			Console.WriteLine("Key: {0}, Value: {1}", kvp.Key, kvp.Value);
		
		//creating a dictionary using collection-initializer syntax
		var cities = new Dictionary<string, string>(){
			{"UK","London, Manchester, Birmingham"},
			{"USA","Chicago, New York, Washington"},
			{"India","Mumbai, New Delhi, Pune"}
		};
		
		foreach(var kvp in cities)
			Console.WriteLine("Key: {0}, Value: {1}", kvp.Key, kvp.Value);
```


![[Pasted image 20240730233907.png]]