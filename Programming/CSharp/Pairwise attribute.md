---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 Using the [Combinatorial attribute](Combinatorial%20attribute.md) the following test would be executed 12 (3x2x2) times. With **Pairwise** it is executed only enough times so that each possible pair is covered.
```csharp
[Test, Pairwise]
public void MyTest(
    [Values("a", "b", "c")] string a,
    [Values("+", "-")] string b,
    [Values("x", "y")] string c)
{
    Console.WriteLine("{0} {1} {2}", a, b, c);
}
```

For this test, NUnit currently calls the method six times, producing the following output:

```
a - x
a + y
b - y
b + x
c - x
c + y
```

Note that this is not the optimal output.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
