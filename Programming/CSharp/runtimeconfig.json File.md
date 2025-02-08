---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Compilation process](Compilation%20process.md)
___
   
This configuration file specifies the shared runtime and its version that your application depends on. It helps the .NET host determine which runtime version to load and can include additional runtime settings.
 ```json
 {
  "runtimeOptions": {
    "tfm": "net5.0",
    "framework": {
      "name": "Microsoft.NETCore.App",
      "version": "5.0.0"
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
