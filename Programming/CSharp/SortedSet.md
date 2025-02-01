---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [[Collection]]
___

## Usage

uses Red-black tree for effecient operations. takes an [IComparer](IComparer.md) as a parameter.


 ```csharp
 using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Create and initialize a SortedSet
        SortedSet<int> numbers = new SortedSet<int> { 5, 1, 3, 2, 4 };

        // Display elements (automatically sorted)
        Console.WriteLine("SortedSet elements:");
        foreach (int number in numbers)
            Console.WriteLine(number);

        // Perform set operations
        SortedSet<int> otherNumbers = new SortedSet<int> { 3, 4, 5, 6, 7 };
        numbers.UnionWith(otherNumbers);
        Console.WriteLine("\nAfter union with {3, 4, 5, 6, 7}:");
        foreach (int number in numbers)
            Console.WriteLine(number);

        numbers.IntersectWith(new SortedSet<int> { 4, 5, 6 });
        Console.WriteLine("\nAfter intersection with {4, 5, 6}:");
        foreach (int number in numbers)
            Console.WriteLine(number);
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
