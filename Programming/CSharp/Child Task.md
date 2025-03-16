---
date_added: 2025-03-16
tags:
  - csharp
---
Up: [[Task]]
___
A child task (or nested task) is a System.Threading.Tasks.Task instance that is created in the user delegate of another task, which is known as the parent task. A child task can be either detached or attached. A detached child task is a task that executes independently of its parent. An attached child task is a nested task that is created with the TaskCreationOptions.AttachedToParent option whose parent does not explicitly or by default prohibit it from being attached. A task may create any number of attached and detached child tasks, limited only by system resources.

## Detached child tasks

Although a child task is created by a parent task, by default it is independent of the parent task. In the following example, a parent task creates one simple child task. If you run the example code multiple times, you may notice that the output from the example differs from that shown, and also that the output may change each time you run the code. This occurs because the parent task and child tasks execute independently of each other; the child is a detached task. The example waits only for the parent task to complete, and the child task may not execute or complete before the console app terminates.


```cs
using System;
using System.Threading;
using System.Threading.Tasks;

public class Example
{
   public static void Main()
   {
      var parent = Task.Factory.StartNew(() => {
         Console.WriteLine("Outer task executing.");

         var child = Task.Factory.StartNew(() => {
            Console.WriteLine("Nested task starting.");
            Thread.SpinWait(500000);
            Console.WriteLine("Nested task completing.");
         });
      });

      parent.Wait();
      Console.WriteLine("Outer has completed.");
   }
}
// The example produces output like the following:
//        Outer task executing.
//        Nested task starting.
//        Outer has completed.
//        Nested task completing.
```

## Attached child tasks

Unlike detached child tasks, attached child tasks are closely synchronized with the parent. You can change the detached child task in the previous example to an attached child task by using the [TaskCreationOptions.AttachedToParent](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.taskcreationoptions#system-threading-tasks-taskcreationoptions-attachedtoparent) option in the task creation statement, as shown in the following example. In this code, the attached child task completes before its parent. As a result, the output from the example is the same each time you run the code.
```cs
using System;
using System.Threading;
using System.Threading.Tasks;

public class Example
{
   public static void Main()
   {
      var parent = Task.Factory.StartNew(() => {
            Console.WriteLine("Parent task executing.");
            var child = Task.Factory.StartNew(() => {
                  Console.WriteLine("Attached child starting.");
                  Thread.SpinWait(5000000);
                  Console.WriteLine("Attached child completing.");
            }, TaskCreationOptions.AttachedToParent);
      });
      parent.Wait();
      Console.WriteLine("Parent has completed.");
   }
}
// The example displays the following output:
//       Parent task executing.
//       Attached child starting.
//       Attached child completing.
//       Parent has completed.
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
