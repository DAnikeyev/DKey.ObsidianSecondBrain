---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [System.IO](System.IO.md)
___
 Performs operations on string instances that contain file or directory path information. These operations are performed in a cross-platform manner.
### Examples:
1. **Combine**:
    
    - Combines two or more strings into a single path.
    - Example: `Path.Combine("folder", "file.txt")` results in `"folder/file.txt"` on Unix or `"folder\file.txt"` on Windows.
2. **GetDirectoryName**:
    
    - Returns the directory information for the specified path string.
    - Example: `Path.GetDirectoryName("/folder/file.txt")` returns `"/folder"`.
3. **GetFileName**:
    
    - Returns the file name and extension of the specified path string.
    - Example: `Path.GetFileName("/folder/file.txt")` returns `"file.txt"`.
4. **GetFileNameWithoutExtension**:
    
    - Returns the file name without the extension of the specified path string.
    - Example: `Path.GetFileNameWithoutExtension("/folder/file.txt")` returns `"file"`.
5. **GetExtension**:
    
    - Returns the extension of the specified path string.
    - Example: `Path.GetExtension("/folder/file.txt")` returns `".txt"`.
6. **GetFullPath**:
    
    - Returns the absolute path for the specified path string.
    - Example: `Path.GetFullPath("file.txt")` might return `"/current/directory/file.txt"`.
7. **GetTempPath**:
    
    - Returns the path of the current system's temporary folder.
    - Example: `Path.GetTempPath()` might return `"/tmp/"` on Unix or `"C:\Users\Username\AppData\Local\Temp\"` on Windows.
8. **GetRandomFileName**:
    
    - Returns a random file name.
    - Example: `Path.GetRandomFileName()` might return `"a3b4c5.tmp"`.
9. **ChangeExtension**:
    
    - Changes the extension of a path string.
    - Example: `Path.ChangeExtension("/folder/file.txt", ".md")` results in `"/folder/file.md"`.
10. **HasExtension**:
    
    - Determines whether a path includes a file name extension.
    - Example: `Path.HasExtension("/folder/file.txt")` returns `true`.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
