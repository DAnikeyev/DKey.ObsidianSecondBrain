---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [System.IO](System.IO.md)
___
 #### Properties

1. **Name**:
    
    - Gets the name of the file.
    - Example: `fileInfo.Name` might return `"file.txt"`.
2. **FullName**:
    
    - Gets the full path of the file.
    - Example: `fileInfo.FullName` might return `"/path/to/file.txt"`.
3. **Directory**:
    
    - Gets an instance of the `DirectoryInfo` class for the directory containing the file.
    - Example: `fileInfo.Directory` provides access to directory-related operations.
4. **DirectoryName**:
    
    - Gets the full path of the directory containing the file.
    - Example: `fileInfo.DirectoryName` might return `"/path/to"`.
5. **Length**:
    
    - Gets the size of the file in bytes.
    - Example: `fileInfo.Length` might return `1024` for a 1 KB file.
6. **Extension**:
    
    - Gets the file extension.
    - Example: `fileInfo.Extension` might return `".txt"`.
7. **CreationTime**:
    
    - Gets or sets the creation time of the file.
    - Example: `fileInfo.CreationTime` might return a `DateTime` object representing when the file was created.
8. **LastAccessTime**:
    
    - Gets or sets the last access time of the file.
    - Example: `fileInfo.LastAccessTime` might return a `DateTime` object.
9. **LastWriteTime**:
    
    - Gets or sets the last write time of the file.
    - Example: `fileInfo.LastWriteTime` might return a `DateTime` object.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
