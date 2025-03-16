---
date_added: 2025-03-16
tags:
  - csharp
---
Up: [[Task]]
___
 Is accessing the property's get accessor blocks the calling thread until the asynchronous operation is complete. Can lead to [Deadlock](Deadlock.md)
 
 ```cs
using System;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        // Using Task.Result
        Task<int> task1 = GetNumberAsync();
        int result1 = task1.Result; // Blocks the thread until the task is complete
        Console.WriteLine($"Result using Task.Result: {result1}");

        // Using await
        int result2 = await GetNumberAsync(); // Asynchronously waits for the task to complete
        Console.WriteLine($"Result using await: {result2}");
    }

    static async Task<int> GetNumberAsync()
    {
        await Task.Delay(1000); // Simulate asynchronous work
        return 42;
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
