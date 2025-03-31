---
date_added: 2025-02-27
tags:
  - csharp
---
Up: [Delegate](Delegate.md)
___
  is a way to define an inline, unnamed [Method](Method.md) using the `delegate` keyword or [Lambda Expressions](Lambda%20Expressions.md)
  
   ```csharp
using System;

class Program
{
    delegate void PrintDelegate(string message);

    static void Main()
    {
        // Define an anonymous method and assign it to a delegate
        PrintDelegate print = delegate(string message)
        {
            Console.WriteLine(message);
        };

        // Use the delegate to call the anonymous method
        print("Hello, World!");
    }
}
 ```
1. An anonymous method does not have access to the ref and out parameters of the method that defines them.
2. An anonymous method cannot have local variables with the same names as the local [Captured variable](Captured%20variable.md) of the enclosing method.
3. An anonymous method can access instance variables (or static variables) from the context of the enclosing class.
4. An anonymous method can declare local variables with the same names as the members of the enclosing class (local variables have a separate context and hide external member variables).
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
