---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [String Formating](String%20Formating.md)
___
```cs
Console.WriteLine(((DayOfWeek)7).ToString("G"));      // 7
Console.WriteLine(ConsoleColor.Red.ToString("G"));    // Red

var attributes = FileAttributes.Hidden | FileAttributes.Archive;
Console.WriteLine(attributes.ToString("G"));          // Hidden, Archive


Console.WriteLine(((DayOfWeek)7).ToString("F"));       // Monday, Saturday
Console.WriteLine(ConsoleColor.Blue.ToString("F"));    // Blue

var attributes = FileAttributes.Hidden | FileAttributes.Archive;
Console.WriteLine(attributes.ToString("F"));           // Hidden, Archive


Console.WriteLine(((DayOfWeek)7).ToString("D"));       // 7
Console.WriteLine(ConsoleColor.Cyan.ToString("D"));    // 11

var attributes = FileAttributes.Hidden | FileAttributes.Archive;
Console.WriteLine(attributes.ToString("D"));           // 34


Console.WriteLine(((DayOfWeek)7).ToString("X"));       // 00000007
Console.WriteLine(ConsoleColor.Cyan.ToString("X"));    // 0000000B

var attributes = FileAttributes.Hidden | FileAttributes.Archive;
Console.WriteLine(attributes.ToString("X"));           // 00000022---
date_added: 2025-01-26
tags: []
---
Up: [[C]]
___
 
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```

```
 
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
