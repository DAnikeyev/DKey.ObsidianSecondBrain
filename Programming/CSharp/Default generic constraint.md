---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Generic Constraint](Generic%20Constraint.md)
___
  ```csharp
 public abstract class B
{
    public void M<T>(T? item) where T : struct { }
    public abstract void M<T>(T? item);

}

public class D : B
{
    // Without the "default" constraint, the compiler tries to override the first method in B
    public override void M<T>(T? item) where T : default { }
}
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
