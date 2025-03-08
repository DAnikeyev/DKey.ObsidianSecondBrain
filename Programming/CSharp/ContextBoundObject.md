---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [Application domain](Application%20domain.md)
___
When multiple threads try to access methods of the `ContextBoundObject`, the synchronization context ensures that only one thread can execute a method at a time. Other threads are blocked until the current thread finishes its execution.

>[!Info]
> You have to set [Synchronisation attribute](Synchronisation%20attribute.md) and inherite ContextBoundObject

It works like automatic [[lock]]

```cs
using System;
using System.Runtime.Remoting.Contexts;

// Context attribute to specify synchronization
[Synchronization]
public class SynchronizedObject : ContextBoundObject
{
    private int counter = 0;

    public void IncrementCounter()
    {
        // This method is automatically synchronized across threads
        counter++;
        Console.WriteLine($"Counter value: {counter}");
        // Simulate some work
        System.Threading.Thread.Sleep(100);
    }

    public int GetCounter()
    {
        return counter;
    }
}

class Program
{
    static void Main()
    {
        var syncObject = new SynchronizedObject();

        // Create multiple threads to access the synchronized object
        var threads = new System.Threading.Thread[5];
        for (int i = 0; i < 5; i++)
        {
            threads[i] = new System.Threading.Thread(() =>
            {
                for (int j = 0; j < 3; j++)
                {
                    syncObject.IncrementCounter();
                }
            });
            threads[i].Start();
        }

        // Wait for all threads to complete
        foreach (var thread in threads)
        {
            thread.Join();
        }

        Console.WriteLine($"Final counter value: {syncObject.GetCounter()}");
    }
}
```


## Attributes
```cs
// Example context attributes
[Synchronization]           // Provides automatic synchronization
[CallbackObject]           // Enables asynchronous callbacks
[SecurityProperty]         // Enforces security policies
```

## ContextProperties
```cs
// Получить информацию о контексте и вывести идентификатор контекста.
Context ctx = Thread.CurrentContext;
Console.WriteLine("{0} object in context {1}", this.ToString(), ctx.ContextID); foreach(IContextProperty itfCtxProp in ctx.ContextProperties)
Console.WriteLine("-> Ctx Prop: {0}", itfCtxProp.Name);
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
