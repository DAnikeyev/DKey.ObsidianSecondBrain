---
date_added: 2025-03-08
tags:
  - csharp
---
Up: [Stream](Stream.md)
___
 Microsoft improved the performance of all streams in the .NET Framework by including a built-in buffer. The performance noticeably improved by applying a BufferedStream to existing streams, such as a FileStream or MemoryStream. Applying a BufferedStream to an existing .NET Framework stream results in a double buffer.

>[!Info]
> So in .net 3+ BufferedStream is mostly useless

A buffer is a block of bytes in memory used to cache data, thereby reducing the number of calls to the operating system. Buffers improve read and write performance. A buffer can be used for either reading or writing, but never both simultaneously.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
