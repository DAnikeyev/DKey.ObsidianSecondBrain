---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 Returns the count of elements in the source sequence grouped by key.
 Returns`IEnumerable<System.Collections.Generic.KeyValuePair<TKey,int>>` 
```
 ```csharp
 using System;
using System.Collections.Generic;
using System.Linq;

class Program
{
    static void Main()
    {
        // Sample data
        var fruits = new List<string> { "apple", "banana", "apple", "orange", "banana", "apple" };

        // CountBy operation using LINQ
        var fruitCounts = fruits
            .GroupBy(fruit => fruit)
            .Select(group => new { Fruit = group.Key, Count = group.Count() });

        // Display the results
        foreach (var fruitCount in fruitCounts)
        {
            Console.WriteLine($"{fruitCount.Fruit}: {fruitCount.Count}");
        }
    }
}
 ```
## Arguments

source:
A sequence that contains elements to be counted.

keySelector:
A function to extract the key for each element.

keyComparer:
An IEqualityComparer to compare keys with.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
