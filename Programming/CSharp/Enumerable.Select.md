---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 Projects each element of a sequence into a new form.
 
This method is implemented by using deferred execution.
 ```cs
IEnumerable<int> squares =
    Enumerable.Range(1, 10).Select(x => x * x);

foreach (int num in squares)
{
    Console.WriteLine(num);
}
```

Has overload that uses index:

```cs
var query =
    fruits.Select((fruit, index) =>
                      new { index, str = fruit.Substring(0, index) });
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
