---
date_added: 2024-10-15
tags:
  - design
---
Up: [Design pattern](Design%20pattern.md)
___
Opposite of Dependency Injection, Dependency Construction is when the class creates its own dependencies. This is not recommended as it makes the class harder to test and maintain. It also makes the class harder to reuse in other contexts.

```C#
public class MyClass
{
    private readonly MyDependency _dependency;

    public MyClass()
    {
        _dependency = new MyDependency(); // Dependency is constructed internally
    }
}

```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
