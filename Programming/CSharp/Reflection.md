---
date_added: 2025-02-02
tags:
  - csharp
sr-due: 2025-03-28
sr-interval: 3
sr-ease: 250
---
Up: [Other CSharp Features](Other%20CSharp%20Features.md)
___
System.Reflection contatins information about assemblies and the types defined within them.

#### Common Use Cases

1. **Dynamic Type Discovery**: You can use reflection to discover information about types at runtime, such as the methods, properties, and fields of a type.
2. **Dynamic Method Invocation**: Reflection allows you to invoke methods on objects dynamically at runtime without knowing their method signatures at compile time.
3. **Assembly Manipulation**: You can load and inspect assemblies, create instances of types, and manipulate their members.
4. **Custom Attributes**: Reflection is used to read custom attributes applied to classes, methods, or properties.
5. **Code Generation and Emission**: Tools like compilers and script engines use reflection to generate and emit code dynamically.

```cs
using System;
using System.Reflection;

namespace ReflectionExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Load the assembly (for this example, we use the executing assembly)
            Assembly assembly = Assembly.GetExecutingAssembly();

            // Display assembly information
            Console.WriteLine($"Assembly Full Name: {assembly.FullName}");
            Console.WriteLine($"Location: {assembly.Location}");

            // Get and display all types defined in the assembly
            Type[] types = assembly.GetTypes();
            foreach (Type type in types)
            {
                Console.WriteLine($"\nType: {type.FullName}");

                // Get and display all methods of the type
                MethodInfo[] methods = type.GetMethods();
                foreach (MethodInfo method in methods)
                {
                    Console.WriteLine($"  Method: {method.Name}");
                }
            }
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
