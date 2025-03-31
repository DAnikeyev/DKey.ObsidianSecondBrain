---
date_added: 2025-01-29
tags:
  - csharp
sr-due: 2025-03-28
sr-interval: 3
sr-ease: 250
---
Up: [CSharp Fundamentals](CSharp%20Fundamentals.md)
___
 ![](Pasted%20image%2020250129011204.png)
Asynchornious programming allows thread to execute code without blocking other threads. It is useful for I/O or GUI operations, like reading files or making network requests. The main thread can continue to do other work while waiting for the I/O operation to complete. 

```cs
static async Task Main(string[] args)
{
    Coffee cup = PourCoffee();
    Console.WriteLine("coffee is ready");

    var eggsTask = FryEggsAsync(2);
    var baconTask = FryBaconAsync(3);
    var toastTask = MakeToastWithButterAndJamAsync(2);

    var eggs = await eggsTask;
    Console.WriteLine("eggs are ready");

    var bacon = await baconTask;
    Console.WriteLine("bacon is ready");

    var toast = await toastTask;
    Console.WriteLine("toast is ready");

    Juice oj = PourOJ();
    Console.WriteLine("oj is ready");
    Console.WriteLine("Breakfast is ready!");
}
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
