---
date_added: 2025-03-18
tags:
  - csharp
---
Up: [Asynchronous programming](Asynchronous%20programming.md)
___
 happens when threads remain active and continue to execute, but due to constantly changing their state in response to each other, they never reach a point of actual progress. Essentially, the threads keep "dancing" around the synchronization problem without ever completing their tasks.
- In a [Deadlock](Deadlock.md), threads are stuck waiting and stop executing, consuming minimal CPU resources.
- In a livelock, threads continuously consume CPU resources by actively spinning or retrying, but they cannot complete their work because of the constant adjustments they make in reaction to one another.
```cs
using System;
using System.Threading;

public class LivelockExample
{
    // Flags representing whether each person is still waiting for help.
    private static bool isAliceHungry = true;
    private static bool isBobHungry = true;

    public static void Main(string[] args)
    {
        Thread aliceThread = new Thread(AssistAlice);
        Thread bobThread = new Thread(AssistBob);

        aliceThread.Start();
        bobThread.Start();

        // Let it run for a while so the livelock becomes apparent.
        Thread.Sleep(1000);

        Console.WriteLine("Intervening to break the livelock...");

        // Intervention: an external decision is made so that they stop yielding.
        isAliceHungry = false;
        isBobHungry = false;

        aliceThread.Join();
        bobThread.Join();

        Console.WriteLine("Both threads have proceeded after intervention.");
    }

    private static void AssistAlice()
    {
        while (isAliceHungry && isBobHungry)
        {
            Console.WriteLine("Alice: I will help Bob because he looks hungry.");
            // Simulate Alice yielding control to Bob.
            Thread.Sleep(100);
        }
        Console.WriteLine("Alice: I got the help I needed and will continue.");
    }

    private static void AssistBob()
    {
        while (isAliceHungry && isBobHungry)
        {
            Console.WriteLine("Bob: I will help Alice because she looks hungry.");
            // Simulate Bob yielding control to Alice.
            Thread.Sleep(100);
        }
        Console.WriteLine("Bob: I got the help I needed and will continue.");
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
