---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [Value Type](Value%20Type.md)
___
16 bit Value type that accepts literal, including hexadecimal `\x` , unicode `\u`  or escape sequence like '\n'.

Is a [Struct](Struct.md)

When you write `char a = 'a';` compiler (or runtime) handles the assignment in a convenient way.
 
 ```cs
 var chars = new[]
{
    'j',
    '\u006A',
    '\x006A',
    (char)106,
};
Console.WriteLine(string.Join(" ", chars));  // output: j j j j
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
