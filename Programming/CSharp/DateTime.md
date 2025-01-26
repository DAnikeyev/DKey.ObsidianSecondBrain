---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [Value Type](Value%20Type.md)
___
is a [Struct](Struct.md)
 ```cs
using System;
using System.Globalization;

DateTime now = DateTime.Now;
CultureInfo culture = new CultureInfo("fr-FR");
string formattedDate = now.ToString("D", culture); // Example output: "mardi 31 octobre 2023"
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```

Is a struct