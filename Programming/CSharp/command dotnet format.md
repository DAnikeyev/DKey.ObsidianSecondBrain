---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 ```cs
 dotnet format [<PROJECT | SOLUTION>] [command] [options]

dotnet format -h|--help
```
Formats code in the files according to default rules or  
 an _.editorconfig_ file like that:
 ```cs
 # top-most EditorConfig file
root = true

# Unix-style newlines with a newline ending every file
[*]
end_of_line = lf
insert_final_newline = true

# 4 space indentation
[*.{js,css,html}]
indent_style = space
indent_size = 4

# Tab indentation (no size specified)
[*.md]
indent_style = tab

# Trailing whitespace trimming for all files
trim_trailing_whitespace = true
```

[Examples](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-format#examples)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
