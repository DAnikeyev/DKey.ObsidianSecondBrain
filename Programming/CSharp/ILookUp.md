---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Collection Interface](Collection%20Interface.md)
___
 Defines an indexer, size property, and Boolean search method for data structures that map keys to [Generic IEnumerable](Generic%20IEnumerable.md) sequences of values.
 
 ```cs
// Iterate through each value in the ILookup and output the contents.
    foreach (var packageGroup in packageLookup)
    {
        // Print the key value.
        Console.WriteLine(packageGroup.Key);
        // Iterate through each value in the collection.
        foreach (string str in packageGroup)
            Console.WriteLine("    {0}", str);
    }
```

## Properties

|   |   |
|---|---|
|[Count](https://learn.microsoft.com/en-us/dotnet/api/system.linq.ilookup-2.count?view=net-9.0#system-linq-ilookup-2-count)|Gets the number of key/value collection pairs in the [ILookup<TKey,TElement>](https://learn.microsoft.com/en-us/dotnet/api/system.linq.ilookup-2?view=net-9.0).|
|[Item[TKey]](https://learn.microsoft.com/en-us/dotnet/api/system.linq.ilookup-2.item?view=net-9.0#system-linq-ilookup-2-item\(-0\))|Gets the [IEnumerable<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.ienumerable-1?view=net-9.0) sequence of values indexed by a specified key.|

## Methods

|   |   |
|---|---|
|[Contains(TKey)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.ilookup-2.contains?view=net-9.0#system-linq-ilookup-2-contains\(-0\))|Determines whether a specified key exists in the [ILookup<TKey,TElement>](https://learn.microsoft.com/en-us/dotnet/api/system.linq.ilookup-2?view=net-9.0).|
|[GetEnumerator()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable.getenumerator?view=net-9.0#system-collections-ienumerable-getenumerator)|Returns an enumerator that iterates through a collection.<br><br>(Inherited from [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0))|

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
