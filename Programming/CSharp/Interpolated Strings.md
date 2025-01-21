---
date_added: 2025-01-21
tags: []
---
Up: [CSharp](CSharp.md)
___
 The `$` character identifies a string literal as an _interpolated string_. An interpolated string is a string literal that might contain _interpolation expressions_.
```cs
var name = "Mark";
var date = DateTime.Now;

// Composite formatting:
Console.WriteLine("Hello, {0}! Today is {1}, it's {2:HH:mm} now.", name, date.DayOfWeek, date);
// String interpolation:
Console.WriteLine($"Hello, {name}! Today is {date.DayOfWeek}, it's {date:HH:mm} now.");
// Both calls produce the same output that is similar to:
// Hello, Mark! Today is Wednesday, it's 19:40 now.
```
To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
