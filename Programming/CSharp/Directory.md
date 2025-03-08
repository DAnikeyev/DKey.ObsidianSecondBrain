---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [System.IO](System.IO.md)
___
 Exposes static methods for creating, moving, and enumerating through directories and subdirectories. This class cannot be inherited.

| Method                                              | Description                                                                                             |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| `CreateDirectory(string path)`                      | Creates all directories and subdirectories in the specified path.                                       |
| `Delete(string path)`                               | Deletes an empty directory from a specified path.                                                       |
| `Delete(string path, bool recursive)`               | Deletes the specified directory and, if specified, its subdirectories and files.                        |
| `Exists(string path)`                               | Determines whether the given path refers to an existing directory.                                      |
| `GetFiles(string path)`                             | Returns the names of files in the specified directory.                                                  |
| `GetFiles(string path, string searchPattern)`       | Returns the names of files that match the specified search pattern in the specified directory.          |
| `GetDirectories(string path)`                       | Returns the names of subdirectories in the specified directory.                                         |
| `GetDirectories(string path, string searchPattern)` | Returns the names of subdirectories that match the specified search pattern in the specified directory. |
| `GetFileSystemEntries(string path)`                 | Returns an array of file system entries (files and directories) in the specified path.                  |
| `GetCurrentDirectory()`                             | Gets the current working directory of the application.                                                  |
| `SetCurrentDirectory(string path)`                  | Sets the application's current working directory to the specified path.                                 |
| `GetParent(string path)`                            | Retrieves the parent directory of the specified path.                                                   |
| `Move(string sourceDirName, string destDirName)`    | Moves a file or a directory and its contents to a new location.                                         |
| `EnumerateFiles(string path)`                       | Returns an enumerable collection of file names in a specified directory.                                |
| `EnumerateDirectories(string path)`                 | Returns an enumerable collection of directory names in a specified directory.                           |
| `EnumerateFileSystemEntries(string path)`           | Returns an enumerable collection of file system entries in a specified directory.                       |


### Example
 ```csharp
 using System;
using System.IO;

namespace ConsoleApplication
{
    class Program
    {
        static void Main(string[] args)
        {
            string sourceDirectory = @"C:\current";
            string archiveDirectory = @"C:\archive";

            try
            {
                var txtFiles = Directory.EnumerateFiles(sourceDirectory, "*.txt");

                foreach (string currentFile in txtFiles)
                {
                    string fileName = currentFile.Substring(sourceDirectory.Length + 1);
                    Directory.Move(currentFile, Path.Combine(archiveDirectory, fileName));
                }
            }
            catch (Exception e)
            {
                Console.WriteLine(e.Message);
            }
        }
    }
}
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
