---
date_added: 2025-03-03
tags:
  - csharp
---
Up: [[Exception]]
___
Is a mechanism provided by the .NET Framework to guarantee that certain critical code – such as cleanup code in finally blocks – is executed reliably even in situations where the runtime is under extreme stress (for example, during an out-of-memory situation or when asynchronous exceptions occur).

 ```csharp
 
        // The following prepares a constrained execution region for the try-finally block.
        // It does not affect code before or after this region.
        RuntimeHelpers.PrepareConstrainedRegions();
        try
        {
            Console.WriteLine("Inside try block of CER.");
            // Simulate some work that might throw an exception.
            throw new InvalidOperationException("Simulated exception.");
        }
        catch (Exception ex)
        {
            Console.WriteLine("Exception caught: " + ex.Message);
        }
        finally
        {
            // This finally block is executed reliably even under constrained conditions.
            Console.WriteLine("Finally block executed reliably.");
        }

        Console.WriteLine("Exiting Main.");
 ```
Или 
 ```csharp
 // Используем атрибут, определенный в пространстве имен
// System.Runtime.ConstrainedExecution
[ReliabilityContract(Consistency.WillNotCorruptState, Cer.Success)]
public static void M() { }
}
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
