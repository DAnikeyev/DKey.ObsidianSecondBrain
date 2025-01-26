---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [String](String.md)
___
 Object has overridable ToString() method that use specific formats for in-build types
 
 ```cs
 int integerValue = 60312;
Console.WriteLine(integerValue.ToString("X"));   // Displays EB98.

double cost = 1632.54;
Console.WriteLine(cost.ToString("C",
                  new System.Globalization.CultureInfo("en-US")));
// The example displays the following output:
//       $1,632.54
 ```


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
