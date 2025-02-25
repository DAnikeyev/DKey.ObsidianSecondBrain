---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 Filters a sequence of values based on a predicate. 
```cs
List<string> fruits =
    new List<string> { "apple", "passionfruit", "banana", "mango",
                    "orange", "blueberry", "grape", "strawberry" };

IEnumerable<string> query = fruits.Where(fruit => fruit.Length < 6);

foreach (string fruit in query)
{
    Console.WriteLine(fruit);
}
/*
 This code produces the following output:

 apple
 mango
 grape
*/
```

Has overload that uses index:
```cs
IEnumerable<int> query =
    numbers.Where((number, index) => number <= index * 10);
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
