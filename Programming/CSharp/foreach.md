---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Iteration statement](Iteration%20statement.md)
___
 The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the [IEnumerable](IEnumerable.md) or [Generic IEnumerable](Generic%20IEnumerable.md) interface, as the following example shows:
 ```cs
 List<int> fibNumbers = new() { 0, 1, 1, 2, 3, 5, 8, 13 };
foreach (int element in fibNumbers)
{
    Console.Write($"{element} ");
}
// Output:
// 0 1 1 2 3 5 8 13
```

The `foreach` statement isn't limited to those types. You can use it with an instance of any type that satisfies the following conditions:

- A type has the public parameterless `GetEnumerator` method. The `GetEnumerator` can be an [Extension method](Extension%20method.md), not the direct implementation of [IEnumerable](IEnumerable.md)
- The return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is `bool`.
For example [Span T](Span%20T.md) does not implement that interface.

```cs
Span<int> numbers = [3, 14, 15, 92, 6];
foreach (int number in numbers)
{
    Console.Write($"{number} ");
}
// Output:
// 3 14 15 92 6
```

If Enumerator returns [[ref return]] or [[readonly]] value, variable in foreach statement must have the same type.

```cs
Span<int> storage = stackalloc int[10];
int num = 0;
foreach (ref int item in storage)
{
    item = num++;
}
foreach (ref readonly var item in storage)
{
    Console.Write($"{item} ");
}
// Output:
// 0 1 2 3 4 5 6 7 8 9
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
