---
date_added: 2025-04-03
tags:
  - csharp
---
Up: [[Task]]
___
## awaiting task that has not started
```cs
var task = new Task(()=>DoSomething());

//wait indefinetly, no one launched task
await task;
```

## await inside lock
won't compile, might lead to [Deadlock](Deadlock.md)
![](Pasted%20image%2020250403012235.png)

## Solving [Deadlock](Deadlock.md) for blocked UI [Synchronisation Context](Synchronisation%20Context.md)

If [Synchronisation Context](Synchronisation%20Context.md) calls `Post` some Task continuation to current blocked thread that is waiting `FooAsync` the deadlock might happen.
![](Pasted%20image%2020250403013554.png)
OR
![](Pasted%20image%2020250403013749.png)
because [[Task]].Run is invoked on a [ThreadPool](ThreadPool.md) with default context.

For [WinForms](WinForms) solution is ![](Pasted%20image%2020250403014105.png)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
