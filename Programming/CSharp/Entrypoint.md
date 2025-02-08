---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Running an application](Running%20an%20application.md)
___
 For executable application an entry point is the Main method. This method is the first method that is called when the program is executed. The Main method can be declared in any class, but it must be static and it should not return a value. StartUp object can be specified by property
 
  ```cs
  <StartupObject>YourNamespace.YourClass</StartupObject>
```

in [csproj file](csproj%20file.md).

 The `Main` method can return `void` or `int`. If it returns `int`, the integer value is used as the exit code of the application, which can be useful for indicating success or failure to the operating system or calling process. 
The Main method can have parameters, but none are required.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
