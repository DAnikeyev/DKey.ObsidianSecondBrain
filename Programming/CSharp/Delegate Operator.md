---
date_added: 2025-01-22
tags:
  - csharp
sr-due: 2025-04-05
sr-interval: 4
sr-ease: 275
---
Up: [CSharp Operator](CSharp%20Operator.md) [keyword](keyword.md)
___
 The `delegate` operator creates an anonymous method that can be converted to a delegate type. An anonymous method can be converted to types such as [System.Action](https://learn.microsoft.com/en-us/dotnet/api/system.action) and [System.Func\< T Result>](https://learn.microsoft.com/en-us/dotnet/api/system.func-1) types used as arguments to many methods.
 ```cs
 Func<int, int, int> sum = delegate (int a, int b) { return a + b; };
Console.WriteLine(sum(3, 4));  // output: 7
```

Is equivalent to:
```cs
Func<int, int, int> sum = (a, b) => a + b;
Console.WriteLine(sum(3, 4));  // output: 7
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
