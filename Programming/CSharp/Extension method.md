---
date_added: 2025-01-24
tags:
  - csharp
---
Up: [Method](Method.md)
___
 Extension methods enable you to "add" methods to existing types without creating a new derived type, recompiling, or otherwise modifying the original type. Extension method are declared as static method using `this` keyword before the first parameter of the method. The type of the first parameter will be the type that is extended.

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

```cs
using ExtensionMethods

string s = "Hello Extension Methods";
int i = s.WordCount();
```

>[!Info]
> Instance method has a priority over extension method during compilation.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
