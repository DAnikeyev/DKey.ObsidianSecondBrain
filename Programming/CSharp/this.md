---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Access keyword](Access%20keyword.md)
___
## Name clarification

```cs
public class Employee
{
    private string alias;
    private string name;

    public Employee(string name, string alias)
    {
        // Use this to qualify the members of the class
        // instead of the constructor parameters.
        this.name = name;
        this.alias = alias;
    }
}
```

## Passing current object as a parameter

 ```csharp
 CalcTax(this);
 ```

## Declaring indexers

 ```csharp
 public int this[int param]
{
    get { return array[param]; }
    set { array[param] = value; }
}
 ```

## [Extension method](Extension%20method.md)

```cs
namespace ExtensionMethods
{
    public static class MyExtensions
    {
        public static int WordCount(this string str)
        {
            return str.Split(new char[] { ' ', '.', '?' },
                             StringSplitOptions.RemoveEmptyEntries).Length;
        }
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
