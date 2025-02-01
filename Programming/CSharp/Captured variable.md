---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Enclosing scope](Enclosing%20scope.md)
___
 ```cs
 int x = 10;
Func<int, int> addX = y => x + y;
```

### Captured Variable: `x`

- **`x`** is defined outside the lambda expression, in the enclosing scope. The lambda captures `x` because it uses `x` within its body (`x + y`)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
