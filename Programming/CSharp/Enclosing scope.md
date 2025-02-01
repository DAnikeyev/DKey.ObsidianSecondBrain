---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Method](Method.md)
___
 Enclosing (or nonlocal) scope is **a special scope that only exists for nested functions** including [Lambda Expressions](Lambda%20Expressions.md) or [Delegate](Delegate.md) 
 ```cs
 int x = 10;
Func<int, int> addX = y => x + y;
```
n this example, the enclosing scope for the lambda expression `y => x + y` is the method or block where `x` is defined. The lambda has access to `x` because it is within its enclosing scope.
 `x` is called [Captured variable](Captured%20variable.md)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
