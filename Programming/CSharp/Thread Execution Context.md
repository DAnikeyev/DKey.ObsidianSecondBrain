---
date_added: 2025-03-16
tags:
  - csharp
---
Up: [Thread](Thread.md)
___
 The ExecutionContext class provides a single container for all information relevant to a logical thread of execution. In .NET Framework, this includes security context, and call contex.

• Flowing Context Data:  
When you create a new thread, start a Task, or use asynchronous methods (e.g., via async/await), the current ExecutionContext is automatically captured. This captured context includes details such as security principal information and culture settings. When the new thread or asynchronous operation executes, it “inherits” this context automatically, ensuring consistency in behavior (e.g., in logging, security, and localization).

• Isolation and Safety:  
The ExecutionContext ensures that context-specific information is preserved across asynchronous calls without having to manually pass state through every call. This isolation makes multi-threaded programming safer and more predictable as the ambient data (like security or user information) remains consistent throughout an operation.

• Suppressing the Flow:  
There are cases where flowing the full ExecutionContext may not be desired (for performance reasons or because you want to run code with a “clean slate”). In these cases, the flow can be suppressed using methods such as ExecutionContext.SuppressFlow(). This is particularly useful in high-performance scenarios where you want to minimize overhead.

>[!Info]
> Things get more complicated when you move from a synchronous world to an asynchronous world.  All of a sudden, TLS becomes largely irrelevant.  In a synchronous world, if I do operation A, then operation B, and then operation C, all three of those operations happen on the same thread, and thus all three of those are subject to the ambient data stored on that thread. But in an asynchronous world, I might start A on one thread and have it complete on another, such that operation B may start or run on a different thread than A, and similarly such that C may start or run on a different thread than B.  This means that this ambient context we’ve come to rely on for controlling details of our execution is no longer viable, because TLS doesn’t “flow” across these async points.  Thread-local storage is specific to a thread, whereas these asynchronous operations aren’t tied to a specific thread.  There is, however, typically a logical flow of control, and we want this ambient data to flow with that control flow, such that the ambient data moves from one thread to another.  This is what ExecutionContext enables.
> Link: https://learn.microsoft.com/en-us/dotnet/api/system.threading.executioncontext?view=net-9.0

```cs
using System;
using System.Globalization;
using System.Security.Claims;
using System.Security.Principal;
using System.Threading;
using System.Threading.Tasks;

public class ExecutionContextWithSecurityAndCulture
{
    public static async Task Main(string[] args)
    {
        // Set the current security principal.
        var identity = new ClaimsIdentity(new[] { new Claim(ClaimTypes.Name, "Alice") });
        Thread.CurrentPrincipal = new ClaimsPrincipal(identity);
        
        // Set the current culture.
        Thread.CurrentThread.CurrentCulture = new CultureInfo("fr-FR");
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("fr-FR");

        Console.WriteLine("Main - Principal: " + Thread.CurrentPrincipal.Identity?.Name);
        Console.WriteLine("Main - Culture: " + Thread.CurrentThread.CurrentCulture.DisplayName);

        // Flow the ExecutionContext to an asynchronous operation.
        await Task.Run(() =>
        {
            // These values are captured by the ExecutionContext and should flow automatically.
            Console.WriteLine("Task - Principal: " + Thread.CurrentPrincipal.Identity?.Name);
            Console.WriteLine("Task - Culture: " + Thread.CurrentThread.CurrentCulture.DisplayName);
        });

        // To demonstrate CallContext/AsyncLocal, you could use AsyncLocal:
        // (Consider this as part of the ambient data flowing in the ExecutionContext.)
        AsyncLocal<string> asyncLocalData = new AsyncLocal<string> { Value = "Ambient Data" };
        await Task.Run(() =>
        {
            Console.WriteLine("Task - AsyncLocal Data: " + asyncLocalData.Value);
        });
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
