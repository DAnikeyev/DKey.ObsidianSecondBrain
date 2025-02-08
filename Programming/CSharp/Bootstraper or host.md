---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Application](Application.md)
___
 Is the source that runs your application. For example when running
 
```powershell
dotnet someApp.exe
```

The dotnet CLI executable itself acts as the host in a framework-dependent deployment.It reads configuration files (such as .runtimeconfig.json and .deps.json) that are located alongside your application, determines the correct shared runtime version, resolves dependencies, and ultimately loads your application’s assemblies.

For self-contained deployments, your application’s executable (someApp.exe) includes an embedded host. In this case, the host code is bundled into the executable so that it can run independently of a separately installed .NET runtime.
## Functions: 
1. **Dependency Installation**: Ensures that all necessary components, libraries, or frameworks (like the .NET runtime) are installed on the target machine.
    
2. **Configuration**: Sets up configuration files or environment variables needed by the application.
    
3. **Version Checking**: Verifies that the correct versions of dependencies are present and updates them if necessary.
    
4. **Initial Setup**: Performs any initial setup tasks required before the main application can start, such as setting up databases or initializing services.
    
5. **Launching the Application**: Once all prerequisites are met, the bootstrapper launches the main application.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
