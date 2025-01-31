---
date_added: 2025-01-13
tags:
  - csharp
  - dotnet
---
Up: [[Class]]
___
Finalizers (historically referred to as **destructors**) are used to perform any necessary final clean-up when a class instance is being collected by the garbage collector. In most cases, you can avoid writing a finalizer by using the [System.Runtime.InteropServices.SafeHandle](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.interopservices.safehandle) or derived classes to wrap any unmanaged handle.

## Rules
- Finalizers cannot be defined in structs. They are only used with classes.
- A class can only have one finalizer.
- Finalizers cannot be inherited or overloaded.
- Finalizers cannot be called. They are invoked automatically.
- A finalizer does not take modifiers or have parameters.
## Example
 ```csharp
 class Car
{
    ~Car()  // finalizer
    {
        // cleanup statements...
    }
}
 ```
The finalizer implicitly calls [Finalize](https://learn.microsoft.com/en-us/dotnet/api/system.object.finalize) on the base class of the object. Therefore, a call to a finalizer is implicitly translated to the following code:

 ```csharp
 protected override void Finalize()
{
    try
    {
        // Cleanup statements...
    }
    finally
    {
        base.Finalize();
    }
}
 ```
The programmer has no control over when the finalizer is called; the garbage collector decides when to call it. It's possible to force garbage collection by calling [Collect](https://learn.microsoft.com/en-us/dotnet/api/system.gc.collect), but most of the time, this call should be avoided because it may create performance issues.
# References
 1. [[IDisposable]]
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
