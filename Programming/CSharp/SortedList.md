---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [[Collection]]
___
Under the sorted list are 2 parallel arrays for key and value, because of that the insertion and deletion are O(n) and the search is O(log n).



>[!Info] See [SortedDictionary](SortedDictionary)
> - [SortedList<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2?view=net-9.0) uses less memory than [SortedDictionary<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2?view=net-9.0).
> - [SortedDictionary<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2?view=net-9.0) has faster insertion and removal operations for unsorted data, O(log `n`) as opposed to O(`n`) for [SortedList<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2?view=net-9.0). 
> - If the list is populated all at once from sorted data, [SortedList<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2?view=net-9.0) is faster than [SortedDictionary<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2?view=net-9.0).

## Properties

| [Capacity](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2.capacity?view=net-9.0#system-collections-generic-sortedlist-2-capacity) | Gets or sets the number of elements that the [SortedList<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2?view=net-9.0) can contain.      |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Comparer](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2.comparer?view=net-9.0#system-collections-generic-sortedlist-2-comparer) | Gets the [IComparer<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icomparer-1?view=net-9.0) for the sorted list.                                              |
| [Count](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2.count?view=net-9.0#system-collections-generic-sortedlist-2-count)          | Gets the number of key/value pairs contained in the [SortedList<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2?view=net-9.0).           |
| [Item[TKey]](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2.item?view=net-9.0#system-collections-generic-sortedlist-2-item(-0))   | Gets or sets the value associated with the specified key.                                                                                                                                   |
| [Keys](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2.keys?view=net-9.0#system-collections-generic-sortedlist-2-keys)             | Gets a collection containing the keys in the [SortedList<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2?view=net-9.0), in sorted order. |
| [Values](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2.values?view=net-9.0#system-collections-generic-sortedlist-2-values)       | Gets a collection containing the values in the [SortedList<TKey,TValue>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2?view=net-9.0).                |

## Important:

• SortedList<TKey, TValue> often uses less memory for smaller collections and allows indexed access, but insertion and removal in the middle can get expensive (O(n)).
  
• SortedDictionary<TKey, TValue> performs insertions and removals in O(log n), making it more predictable for larger or frequently modified collections, but it does not support index-based operations.

## Example

 ```csharp
 using System;
using System.Collections.Generic;

class SortedListExample
{
    static void Main()
    {
        var sortedList = new SortedList<int, string>();
        sortedList.Add(2, "Second");
        sortedList.Add(1, "First");
        sortedList.Add(3, "Third");
        
        // Index-based retrieval
        Console.WriteLine($"Key at index 0: {sortedList.GetKey(0)}");
        Console.WriteLine($"Value at index 0: {sortedList.GetByIndex(0)}");
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


>[!Info]
> Non-generic type is not recommended to use in new code. Use generic types instead.
