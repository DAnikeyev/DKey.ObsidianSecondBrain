---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [Reflection](Reflection.md)
___


Contains methods to create types of objects locally or remotely, or obtain references to existing remote objects. This class cannot be inherited.

>[!Info]
> Is part of System, not System.Reflections

### Example

```cs
using System;
using System.Reflection;

class Program
{
    static void Main(string[] args)
    {
        // Load the assembly
        Assembly assembly = Assembly.LoadFrom("path_to_your_assembly.dll");

        // Get the type containing the method
        Type type = assembly.GetType("Namespace.ClassName");

        // Create an instance of the type
        object instance = Activator.CreateInstance(type);

        // Get the method to invoke
        MethodInfo method = type.GetMethod("MethodName");

        // Invoke the method
        method.Invoke(instance, null);
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
