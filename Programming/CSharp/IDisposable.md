---
date_added: 2025-01-28
tags:
  - csharp
sr-due: 2025-04-04
sr-interval: 3
sr-ease: 250
---
Up: [Fundamental Interfaces](Fundamental%20Interfaces.md)
___
 IDisposable is mostly used to release [Unmanaged](Unmanaged.md) such as file handles, database connections, etc. It is implemented by classes that use unmanaged resources. It is a part of the System namespace.

## Methods
- Dispose() - It is used to release all the resources used by the object.

>[!Warning]
> It is a breaking change to add the [IDisposable](https://learn.microsoft.com/en-us/dotnet/api/system.idisposable) interface to an existing class. Because pre-existing consumers of your type cannot call [Dispose](https://learn.microsoft.com/en-us/dotnet/api/system.idisposable.dispose), you cannot be certain that unmanaged resources held by your type will be released.

>[!Info]
> IDisposable can be used with [Struct](Struct.md) but [Finalizer](Finalizer.md) cannot be used with Struct.

## Behaviour
 [Garbage Collector](Garbage%20Collector.md) does not call the Dispose method. It is the responsibility of the developer to call the Dispose method to release the resources.

# How to use [IDisposable](IDisposable.md) with [Finalizer](Finalizer.md)
If your class has:
• Only Managed Resources:  
– No finalizer needed since the runtime garbage collector handles managed objects automatically.  
– Implement IDisposable if you want deterministic release of resources (like file handles wrapped by a managed type) or to follow a standard disposal pattern.

• Only Unmanaged Resources:  
– Typically implement both IDisposable and a finalizer (Dispose pattern).  
– IDisposable allows deterministic cleanup when the user calls Dispose.  
– The finalizer is a backup so unmanaged resources are eventually freed if Dispose is never called.

• Both Managed and Unmanaged Resources:  
– Use the full IDisposable and finalizer (Dispose pattern) so you can safely free unmanaged resources in the finalizer and properly dispose managed resources when Dispose is called.


# Standard pattern

```cs
using System;
using System.IO;

public class ResourceHolderWithFinalizer : IDisposable
{
    private bool _disposed;
    private IntPtr _unmanagedHandle; // Example of an unmanaged resource handle
    private FileStream _fileStream;  // Example of a managed resource

    public ResourceHolderWithFinalizer(string filePath)
    {
        // Allocate an unmanaged resource (simulate via new IntPtr for demonstration)
        _unmanagedHandle = new IntPtr(1234); 
        // Open a file stream (managed resource)
        _fileStream = new FileStream(filePath, FileMode.OpenOrCreate);
    }

    // Public Dispose method (IDisposable implementation)
    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this); // Prevent the finalizer from running if already disposed
    }

    // Finalizer (C# destructor syntax)
    ~ResourceHolderWithFinalizer()
    {
        Dispose(false); // Cleanup only unmanaged resources
    }

    // The dispose pattern implementation
    protected virtual void Dispose(bool disposing)
    {
        if (!_disposed)
        {
            if (disposing)
            {
                // Here we dispose managed resources
                if (_fileStream != null)
                {
                    _fileStream.Dispose();
                    _fileStream = null;
                }
            }

            // Here we free unmanaged resources
            if (_unmanagedHandle != IntPtr.Zero)
            {
                // Release handle (for example, call CloseHandle(_unmanagedHandle) in Windows API)
                _unmanagedHandle = IntPtr.Zero;
            }

            _disposed = true;
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
