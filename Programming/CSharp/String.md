---
date_added: 2025-01-26
tags:
  - csharp
sr-due: 2025-04-05
sr-interval: 4
sr-ease: 276
---
Up: [Reference Type](Reference%20Type.md)
___
 Represents a sequence of characters. Also strings a [Reference Type](Reference%20Type.md) , comparison is overridden to behave like value type. Strings are [Immutable](Immutable.md)
Internally, the text is stored as a sequential read-only collection of `System.Char` objects. The `System.String.Length` property of a string represents the number of `Char` objects it contains, not the number of Unicode characters. To access the individual Unicode code points in a string, you can use the `System.Globalization.StringInfo` object.

>[!Info]
> string is an alias for `System.String` in C#.
## String literals
```cs
//Raw string literals:
"""
This is a multi-line
    string literal with the second line indented.
"""

"""""
This raw string literal has four """", count them: """" four!
embedded quote characters in a sequence. That's why it starts and ends
with five double quotes.

You could extend this example with as many embedded quotes as needed for your text.
"""""

var message = """
"This is a very important message."
""";
Console.WriteLine(message);
// output: "This is a very important message."
```


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
