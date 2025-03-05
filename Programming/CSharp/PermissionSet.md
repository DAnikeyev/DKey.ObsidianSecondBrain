---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [Application domain](Application%20domain.md)
___
is part of the `System.Security.Permissions` namespace and is used to control access to files and directories.

 ```cs
 // Grant read access to a specific environment variable 
 EnvironmentPermission readEnvPermission = new EnvironmentPermission(EnvironmentPermissionAccess.Read, "PATH");
  
// Grant write access to a specific registry key 
RegistryPermission registryWritePermission = new RegistryPermission(RegistryPermissionAccess.Write, @"HKEY_LOCAL_MACHINE\Software\ExampleKey");

// Grant permission to execute code SecurityPermission 
executePermission = new SecurityPermission(SecurityPermissionFlag.Execution);

// Grant permission to use all windows and user input events 
UIPermission uiPermission = new UIPermission(UIPermissionWindow.AllWindows, UIPermissionClipboard.AllClipboard);

// Grant read access to a specific file

FileIOPermission readPermission = new FileIOPermission(FileIOPermissionAccess.Read, @"C:\example.txt");

```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
