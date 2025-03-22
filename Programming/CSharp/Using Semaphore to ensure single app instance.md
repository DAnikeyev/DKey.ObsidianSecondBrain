---
date_added: 2025-03-18
tags:
  - csharp
---
Up: [Semaphore](Semaphore.md)
___
 ```cs
 using System;
using System.Threading;

public static class Program
{
    public static void Main()
    {
        bool createdNew;

        // Attempt to create a semaphore with the specified name
        using (new Semaphore(0, 1, "SomeUniqueStringIdentifyingMyApp", out createdNew))
        {
            if (createdNew)
            {
                // This thread creates the semaphore, so other instances of the application
                // cannot run. Execute the rest of the application...
            }
            else
            {
                // This thread opens an existing semaphore with the same name;
                // another instance of the application should be running.
                // Do nothing and wait for control to return from the Main method
                // to terminate the second instance of the application.
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
