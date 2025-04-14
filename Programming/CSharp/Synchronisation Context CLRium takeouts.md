---
date_added: 2025-04-02
tags:
  - csharp
---
Up: [Synchronisation Context](Synchronisation%20Context.md)
___

### Executing in different thread
 - If UI thread is doing something you can't force execution of your method from different thread
	 - you have to make a delegate
	 - and put it a scheduler of UI thread
- For any threads they have to take command from common place

### Developing your own component
 - If you need parallel execution you need to know
	 - Is [ThreadPool](ThreadPool.md) starving
	 - How many [Thread](Thread.md)s i can use?

>[!Error]
>  Thread pool can be put into a deadlock if a thread is waiting for the second thread, but second thread can execute because threadpool is full.

## [Synchronisation Context](Synchronisation%20Context.md)
Is abstraction of thread grouping.
Lets you group threads to distribute tasks among them

```cs
public class SynchronizationContext
{
    public static SynchronizationContext Current { get; }
    public virtual SynchronizationContext CreateCopy();

    public bool IsWaitNotificationRequired();
    public virtual void OperationCompleted();
    public virtual void OperationStarted();

    public virtual void Post(SendOrPostCallback d, object state);
    public virtual void Send(SendOrPostCallback d, object state);

    public static void SetSynchronizationContext(SynchronizationContext syncContext);

    protected void SetWaitNotificationRequired();
    public virtual int Wait(IntPtr[] waitHandles, bool waitAll, int millisecondsTimeout);
    protected static int WaitHelper(IntPtr[] waitHandles, bool waitAll, int millisecondsTimeout);
}

```

>[!Info]
>Post asynchronously calls a [Delegate](Delegate.md)
Send do that synchronously

![](Pasted%20image%2020250402202738.png)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
