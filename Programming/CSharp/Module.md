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
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
