---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Running an application](Running%20an%20application.md)
___
 A small native host embedded into the executable, compiled for the target OS and architecture. When you run your self-contained app, that native host starts up first, loads the bundled .NET runtime libraries, and then transfers control to your project’s managed entry point. Can be created by publishing or building the application with the `--self-contained` option.
 
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
