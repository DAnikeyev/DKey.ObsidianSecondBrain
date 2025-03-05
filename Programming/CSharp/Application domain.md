---
date_added: 2025-03-03
tags:
  - csharp
---
Up: [Application environment](Application%20environment.md)
___
  Is an instance of a running program In C#, an **application domain** is a mechanism used by the .NET runtime to isolate executed applications. It is a lightweight, logical container within a process that allows multiple .NET applications to run in the same process without affecting each other. [AppDomain](AppDomain.md) class can be used to manage domains. Domains can be loaded/unloaded independently.

  Reasons to have multiple domains:
  - **Isolation**: Each domain has its own memory space, so if one domain crashes, it does not affect other domains.
  - **Security**: Each domain can have its own security settings and permissions.
  - **Versioning**: Different domains can run different versions of the same assembly side by side.
  - Plugin Architecture: Domains can be used to load/unload plugins dynamically.
  - Dynamic code execution: Domains can be used to run code dynamically.
  - **Sandboxing**: Domains can be used to run untrusted code in a sandboxed environment.

While [Thread](Thread.md) contain [Memory stack](Memory%20stack.md), heap belongs to AppDomain so object
## Setting policies
```cs
//Can't write to "C:\":
var perm = new PermissionSet(PermissionState.None);
perm.AddPermission(new FileIOPermission(FileIOPermissionAccess.Read, "C:\\"));
AppDomain domain = AppDomain.CreateDomain("NewDomain", null, new AppDomainSetup(), perm);
var data = domain.CreateInstanceAndUnwrap("AssemblyName", "TypeName");

//Throws an exception if method tries to write to "C:\"

data.Method();
```
## Sharing resources
```cs

// In AppDomain B - Accessing the object from another domain
AppDomain domainA = AppDomain.CreateDomain("DomainA");
SharedService remoteService = (SharedService)domainA.CreateInstanceAndUnwrap(
    typeof(SharedService).Assembly.FullName, 
    typeof(SharedService).FullName);
string result = remoteService.GetData(); // Remote call across domains
```

### AssemblyLoadEventHandler
```cs
private static void InitDAD()
{
	// Эта логика будет выводить имя любой сборки,
	// загруженной в домен приложения после его создания.
	AppDomain defaultAD = AppDomain.CurrentDomain; defaultAD.AssemblyLoad += (o, s) =>
	{
		Console.WriteLine("{0} has been loaded!", s.LoadedAssembly.GetName().Name); };
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
