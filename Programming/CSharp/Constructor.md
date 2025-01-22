---
date_added: 2025-01-13
tags:
  - csharp
---
Up: [[Class]]
___
 Is a syntax to create an instance of a class:
 
 ```csharp
 public class Container
{
    private int _capacity;

    public Container(int capacity) => _capacity = capacity;
}
 ```

Primary constructors are available in C# 12:
```cs
public class NamedItem(string name)
{
    public string Name => name;
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
