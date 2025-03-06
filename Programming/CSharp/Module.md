---
date_added: 2025-02-02
tags:
  - csharp
---
Up: [Reflection](Reflection.md)
___
 Module is a part of assembly. You migh have multiple modules for different reasons:

1. [[Separation of Concerns]]
2. Language [Interoperability](Interoperability.md)
3. Incremental Compilation
4. Security and access control
5. Resource management

Module class lets you to access module data
```cs
using System.Reflection;
using System;
public class Program {

    public static void Main() {
        Class1 c1 = new Class1();
        //  Show the current module.
        Module m = c1.GetType().Module;
        Console.WriteLine("The current module is {0}.", m.Name);

        //  List all modules in the assembly.
        Assembly curAssembly = typeof(Program).Assembly;
        Console.WriteLine("The current executing assembly is {0}.", curAssembly);

        Module[] mods = curAssembly.GetModules();
        foreach (Module md in mods) {
            Console.WriteLine("This assembly contains the {0} module", md.Name);
        }
        Console.ReadLine();
    }
}
class Class1 {
}
```

It's very uncommon to have more than one module in assembly from C#, usually it's done by other languages like C++/CLI. 
 But here how you can do that:

1. **Compile Each Source File into a Module:**
    
    - Use the C# compiler to compile each source file into a module. This is done using the `/target:module` option.
    
    ```bash
    csc /target:module /out:Module1.netmodule Module1.cs
    csc /target:module /out:Module2.netmodule Module2.cs
    ```
    
    This will produce `Module1.netmodule` and `Module2.netmodule`.
    
2. **Link Modules into a Single Assembly:**
    
    - Use the C# compiler again to link the modules into a single assembly.
    
    ```bash
    csc /out:MyAssembly.dll /target:library Module1.netmodule Module2.netmodule
    ```
    
    This will produce `MyAssembly.dll` containing both modules.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
