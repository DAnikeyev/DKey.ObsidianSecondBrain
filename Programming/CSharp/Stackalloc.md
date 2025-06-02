---
date_added: 2024-10-08
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___
# Content

You can allocate memory in a block on the stack explicitly by using the stackalloc
keyword. Because it is allocated on the stack, its lifetime is limited to the execution
of the method, just as with any other local variable

```cs
int* a = stackalloc int [10];
for (int i = 0; i < 10; ++i)
	Console.WriteLine (a[i]);
```

using [Span T](Span%20T.md) you can manage allocated memory in a more type-safe way, without [unsafe](unsafe.md) keyword.
```cs
Span<int> a = stackalloc int [10];
for (int i = 0; i < 10; ++i)
Console.WriteLine (a[i]);
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
