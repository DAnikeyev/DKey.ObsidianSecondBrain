---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [[Enumerable]]
___
## Without predicate
Returns `false` if the source sequence is empty; otherwise, `true`.

## With predicate
Returns `true` if every element of the source sequence passes the test in the specified predicate, or if the sequence is empty; otherwise, `false`.
 ```csharp
 public static bool Any<TSource>(this System.Collections.Generic.IEnumerable<TSource> source);

  public static bool Any<TSource>(this System.Collections.Generic.IEnumerable<TSource> source, Func<TSource,bool> predicate);
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
