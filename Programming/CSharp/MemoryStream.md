---
date_added: 2025-03-08
tags:
  - csharp
---
Up: [Stream](Stream.md)
___
Creates a stream whose backing store is memory. Memory streams created with an unsigned byte array provide a non-resizable stream of the data. When using a byte array, you can neither append to nor shrink the stream, although you might be able to modify the existing contents depending on the parameters passed into the constructor. Empty memory streams are resizable, and can be written to and read from.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
