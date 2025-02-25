---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
Returns the last element of a sequence.
Or
Returns the last element of a sequence that satisfies a specified condition.
```cs
int[] numbers = { 9, 34, 65, 92, 87, 435, 3, 54,
                    83, 23, 87, 67, 12, 19 };

int last = numbers.Last(num => num > 80);

Console.WriteLine(last);

/*
 This code produces the following output:

 87
*/
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
