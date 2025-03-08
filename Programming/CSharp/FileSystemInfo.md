---
date_added: 2025-03-08
tags:
  - csharp
---
Up: [System.IO](System.IO.md)
___
 base class for [FileInfo](FileInfo.md) and [[DirectoryInfo]]

| Property         | Description                                                                                                                                                        |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `Attributes`     | Gets or sets the attributes associated with the current file, represented by the `FileAttributes` enumeration (e.g., read-only, encrypted, hidden, or compressed). |
| `CreationTime`   | Gets or sets the creation time of the current file or directory.                                                                                                   |
| `Exists`         | Can be used to determine whether the specified file or directory exists.                                                                                           |
| `Extension`      | Retrieves the file extension.                                                                                                                                      |
| `FullName`       | Gets the full path to the file or directory.                                                                                                                       |
| `LastAccessTime` | Gets or sets the time of the last access to the current file or directory.                                                                                         |
| `LastWriteTime`  | Gets or sets the time of the last write to the current file or directory.                                                                                          |
| `Name`           | Gets the name of the current file or directory.                                                                                                                    |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
