---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [Reference Type](Reference%20Type.md)
___
 Represents a sequence of characters. Also strings a reference type, comparison is overridden to behave like value type.

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


## Interpolation

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
