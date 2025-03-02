---
date_added: 2025-03-01
tags:
  - csharp
---
Up: [Method](Method.md)
___
 Invoking methods, the variable name need not be added to the invocation. However, if you have a method
signature like the following to move a rectangle
`public void MoveAndResize(int x, int y, int width, int height)`
and you invoke it with the following code snippet, it’s not clear from the invocation what numbers are used
for what:
`r.MoveAndResize(30, 40, 20, 40);`
You can change the invocation to make it immediately clear what the numbers mean:
`r.MoveAndResize(x: 30, y: 40, width: 20, height: 40);`

Combines well with [[Optional arguments]]
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
