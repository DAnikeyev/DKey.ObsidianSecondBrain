---
date_added: 2025-03-08
tags:
  - csharp
---
Up: [System.IO](System.IO.md) [Directory](Directory.md)
___

>[!Info]
> `DirectoryInfo dir1 = new DirectoryInfо(".");` creates a `DirectoryInfo` object representing the current directory. Unlike using AppContext.BaseDirectory, this updates after Directory.SetCurrentDirectory is called.


### DirectoryInfo Properties

1. **Name**:
    
    - Gets the name of the directory.
    - Example: `directoryInfo.Name` might return `"Documents"`.
2. **FullName**:
    
    - Gets the full path of the directory.
    - Example: `directoryInfo.FullName` might return `"/path/to/Documents"`.
3. **Parent**:
    
    - Gets the parent directory as a `DirectoryInfo` object.
    - Example: `directoryInfo.Parent` provides access to the parent directory.
4. **Root**:
    
    - Gets the root portion of the directory as a `DirectoryInfo` object.
    - Example: `directoryInfo.Root` might return the root directory, such as `"/"` or `"C:\"`.
5. **Exists**:
    
    - Determines whether the directory exists.
    - Example: `directoryInfo.Exists` might return `true` if the directory exists.
6. **Extension**:
    
    - Gets the extension of the directory (usually an empty string for directories).
    - Example: `directoryInfo.Extension` might return `""`.
7. **CreationTime**:
    
    - Gets or sets the creation time of the directory.
    - Example: `directoryInfo.CreationTime` might return a `DateTime` object representing when the directory was created.
8. **LastAccessTime**:
    
    - Gets or sets the last access time of the directory.
    - Example: `directoryInfo.LastAccessTime` might return a `DateTime` object.
9. **LastWriteTime**:
    
    - Gets or sets the last write time of the directory.
    - Example: `directoryInfo.LastWriteTime` might return a `DateTime` object.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
