---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
Is implemented using a balanced binary search tree, like red-black tree.
>[!Info] See [SortedList](SortedList.md)
> - [SortedList<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2?view=net-9.0) uses less memory than [SortedDictionary<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2?view=net-9.0).
> - [SortedDictionary<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2?view=net-9.0) has faster insertion and removal operations for unsorted data, O(log `n`) as opposed to O(`n`) for [SortedList<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2?view=net-9.0). 
> - If the list is populated all at once from sorted data, [SortedList<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2?view=net-9.0) is faster than [SortedDictionary<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2?view=net-9.0).


## Properties

| [Comparer](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.comparer?view=net-9.0#system-collections-generic-sorteddictionary-2-comparer) | Gets the [IComparer<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icomparer-1?view=net-9.0) used to order the elements of the [SortedDictionary<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2?view=net-9.0). |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Count](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.count?view=net-9.0#system-collections-generic-sorteddictionary-2-count)          | Gets the number of key/value pairs contained in the [SortedDictionary<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2?view=net-9.0).                                                                                                         |
| [Item[TKey]](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.item?view=net-9.0#system-collections-generic-sorteddictionary-2-item(-0))   | Gets or sets the value associated with the specified key.                                                                                                                                                                                                                                             |
| [Keys](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.keys?view=net-9.0#system-collections-generic-sorteddictionary-2-keys)             | Gets a collection containing the keys in the [SortedDictionary<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2?view=net-9.0).                                                                                                                |
| [Values](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.values?view=net-9.0#system-collections-generic-sorteddictionary-2-values)       | Gets a collectio                                                                                                                                                                                                                                                                                      |
## Important:

• SortedList<TKey, TValue> often uses less memory for smaller collections and allows indexed access, but insertion and removal in the middle can get expensive (O(n)).
  
• SortedDictionary<TKey, TValue> performs insertions and removals in O(log n), making it more predictable for larger or frequently modified collections, but it does not support index-based operations.
## Example

 ```csharp
 using System;
using System.Collections.Generic;

class SortedDictionaryExample
{
    static void Main()
    {
        var sortedDict = new SortedDictionary<int, string>();
        sortedDict.Add(2, "Second");
        sortedDict.Add(1, "First");
        sortedDict.Add(3, "Third");

        // Iterating over the sorted dictionary
        foreach (var kvp in sortedDict)
        {
            Console.WriteLine($"Key: {kvp.Key}, Value: {kvp.Value}");
        }
    }
}
 ```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
