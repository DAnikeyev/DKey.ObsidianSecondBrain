---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 Filters the elementsbased on a specified type.
```cs
System.Collections.ArrayList fruits = new()
{
    "Mango",
    "Orange",
    null,
    "Apple",
    3.0,
    "Banana"
};

// Apply OfType() to the ArrayList.
IEnumerable<string> query1 = fruits.OfType<string>();

Console.WriteLine("Elements of type 'string' are:");
foreach (string fruit in query1)
{
    Console.WriteLine(fruit);
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
