---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [System.Diagnostics](System.Diagnostics.md)
___
Represents a .dll or .exe file that is loaded into a particular process. Use ProcessModuleCollection to get the modules loaded by a process.

```cs

    ProcessModule myProcessModule;
    // Get all the modules associated with 'myProcess'.
    ProcessModuleCollection myProcessModuleCollection = myProcess.Modules;
    Console.WriteLine("Properties of the modules  associated "
        + "with 'notepad' are:");
    // Display the properties of each of the modules.
    for (int i = 0; i < myProcessModuleCollection.Count; i++)
    {
        myProcessModule = myProcessModuleCollection[i];
        Console.WriteLine("The moduleName is "
            + myProcessModule.ModuleName);
        Console.WriteLine("The " + myProcessModule.ModuleName + "'s base address is: "
            + myProcessModule.BaseAddress);
        Console.WriteLine("The " + myProcessModule.ModuleName + "'s Entry point address is: "
            + myProcessModule.EntryPointAddress);
        Console.WriteLine("The " + myProcessModule.ModuleName + "'s File name is: "
            + myProcessModule.FileName);
    }
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
