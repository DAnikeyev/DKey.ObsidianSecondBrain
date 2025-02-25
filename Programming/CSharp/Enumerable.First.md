---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 Returns the first element of a sequence.
 or
 Returns the first element in a sequence that satisfies a specified condition.
### Example
  ```csharp
int[] numbers = { 9, 34, 65, 92, 87, 435, 3, 54,
                    83, 23, 87, 435, 67, 12, 19 };

int first = numbers.First(number => number > 80);

Console.WriteLine(first);

/*
 This code produces the following output:

 92
*/
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
