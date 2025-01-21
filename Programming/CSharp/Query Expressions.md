---
date_added: 2025-01-21
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___
 ```cs
int[] scores = { 90, 97, 78, 68, 85 };
IEnumerable<int> highScoresQuery =
    from score in scores
    where score > 80
    orderby score descending
    select score;
Console.WriteLine(string.Join(" ", highScoresQuery));
// Output:
// 97 90 85
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
