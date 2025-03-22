---
date_added: 2025-01-29
tags:
  - csharp
---
Up: [Asynchronous programming](Asynchronous%20programming.md)
___
Thread class creates and controls a thread, sets its priority, and gets its status.
Main methods are **Start, Sleep, Join, Priority, Interrupt, Abort, IsAlive, IsBackground,** **ManagedThreadId**, **ThreadState**.
## Usage
Thread has a parameterized constructor that takes a `delegate void ParameterizedThreadStart(Object obj);` as an argument. 

**Basic Thread Creation and Execution**
```cs
// Method 1: Using Thread class directly
Thread thread = new Thread(() => {
    // Your work here
    Console.WriteLine("Thread is running");
});
thread.Start();

// Method 2: Using ParameterizedThreadStart for passing parameters
Thread thread = new Thread(new ParameterizedThreadStart(WorkMethod));
thread.Start(parameterObject);
```

**Thread Sleep and Synchronization**
```cs
// Pause execution for specified milliseconds
Thread.Sleep(2000); // Pauses for 2 seconds

// Thread synchronization using lock
private static object _lockObject = new object();
lock (_lockObject)
{
    // Thread-safe code here
}
```

Thread Management
```cs
Thread thread = new Thread(() => {
    // Work here
});

// Set thread properties
thread.IsBackground = true; // Makes it a background thread
thread.Priority = ThreadPriority.Normal;

// Start the thread
thread.Start();

// Wait for thread to complete
thread.Join();

// Check thread state
bool isAlive = thread.IsAlive;
```

>[!Info]
> Thread.Sleep(0) is used to yield the processor to other threads of the same or higher priority. It is a way to give other threads a chance to run.
> Thread.Sleep(1) explicitly requests a sleep (even if brief) period


## Constructors

| [Thread(ParameterizedThreadStart, Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.-ctor?view=net-9.0#system-threading-thread-ctor(system-threading-parameterizedthreadstart-system-int32)) | Initializes a new instance of the [Thread](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread?view=net-9.0) class, specifying a delegate that allows an object to be passed to the thread when the thread is started and specifying the maximum stack size for the thread. |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Thread(ParameterizedThreadStart)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.-ctor?view=net-9.0#system-threading-thread-ctor(system-threading-parameterizedthreadstart))                     | Initializes a new instance of the [Thread](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread?view=net-9.0) class, specifying a delegate that allows an object to be passed to the thread when the thread is started.                                                      |
| [Thread(ThreadStart, Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.-ctor?view=net-9.0#system-threading-thread-ctor(system-threading-threadstart-system-int32))                           | Initializes a new instance of the [Thread](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread?view=net-9.0) class, specifying the maximum stack size for the thread.                                                                                                       |
| [Thread(ThreadStart)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.-ctor?view=net-9.0#system-threading-thread-ctor(system-threading-threadstart))                                               | Initializes a new instance of the [Thread](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread?view=net-9.0) class.                                                                                                                                                         |
## Properties

|                                                                                                                                                                       |                                                                                                                                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ApartmentState](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.apartmentstate?view=net-9.0#system-threading-thread-apartmentstate)             | **Obsolete.**<br><br>Gets or sets the apartment state of this thread.                                                                                                                                      |
| [CurrentCulture](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.currentculture?view=net-9.0#system-threading-thread-currentculture)             | Gets or sets the culture for the current thread.                                                                                                                                                           |
| [CurrentPrincipal](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.currentprincipal?view=net-9.0#system-threading-thread-currentprincipal)       | Gets or sets the thread's current principal (for role-based security).                                                                                                                                     |
| [CurrentThread](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.currentthread?view=net-9.0#system-threading-thread-currentthread)                | Gets the currently running thread.                                                                                                                                                                         |
| [CurrentUICulture](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.currentuiculture?view=net-9.0#system-threading-thread-currentuiculture)       | Gets or sets the current culture used by the Resource Manager to look up culture-specific resources at run time.                                                                                           |
| [ExecutionContext](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.executioncontext?view=net-9.0#system-threading-thread-executioncontext)       | Gets an [ExecutionContext](https://learn.microsoft.com/en-us/dotnet/api/system.threading.executioncontext?view=net-9.0) object that contains information about the various contexts of the current thread. |
| [IsAlive](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.isalive?view=net-9.0#system-threading-thread-isalive)                                  | Gets a value indicating the execution status of the current thread.                                                                                                                                        |
| [IsBackground](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.isbackground?view=net-9.0#system-threading-thread-isbackground)                   | Gets or sets a value indicating whether or not a thread is a background thread.                                                                                                                            |
| [IsThreadPoolThread](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.isthreadpoolthread?view=net-9.0#system-threading-thread-isthreadpoolthread) | Gets a value indicating whether or not a thread belongs to the managed thread pool.                                                                                                                        |
| [ManagedThreadId](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.managedthreadid?view=net-9.0#system-threading-thread-managedthreadid)          | Gets a unique identifier for the current managed thread.                                                                                                                                                   |
| [Name](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.name?view=net-9.0#system-threading-thread-name)                                           | Gets or sets the name of the thread.                                                                                                                                                                       |
| [Priority](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.priority?view=net-9.0#system-threading-thread-priority)                               | Gets or sets a value indicating the scheduling priority of a thread.                                                                                                                                       |
| [ThreadState](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.threadstate?view=net-9.0#system-threading-thread-threadstate)                      | Gets a value containing the states of the current thread.                                                                                                                                                  |

## Methods

|   |   |
|---|---|
|[Abort()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.abort?view=net-9.0#system-threading-thread-abort)|**Obsolete.**<br><br>Raises a [ThreadAbortException](https://learn.microsoft.com/en-us/dotnet/api/system.threading.threadabortexception?view=net-9.0) in the thread on which it is invoked, to begin the process of terminating the thread. Calling this method usually terminates the thread.|
|[Abort(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.abort?view=net-9.0#system-threading-thread-abort(system-object))|**Obsolete.**<br><br>Raises a [ThreadAbortException](https://learn.microsoft.com/en-us/dotnet/api/system.threading.threadabortexception?view=net-9.0) in the thread on which it is invoked, to begin the process of terminating the thread while also providing exception information about the thread termination. Calling this method usually terminates the thread.|
|[AllocateDataSlot()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.allocatedataslot?view=net-9.0#system-threading-thread-allocatedataslot)|Allocates an unnamed data slot on all the threads. For better performance, use fields that are marked with the [ThreadStaticAttribute](https://learn.microsoft.com/en-us/dotnet/api/system.threadstaticattribute?view=net-9.0) attribute instead.|
|[AllocateNamedDataSlot(String)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.allocatenameddataslot?view=net-9.0#system-threading-thread-allocatenameddataslot(system-string))|Allocates a named data slot on all threads. For better performance, use fields that are marked with the [ThreadStaticAttribute](https://learn.microsoft.com/en-us/dotnet/api/system.threadstaticattribute?view=net-9.0) attribute instead.|
|[BeginCriticalRegion()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.begincriticalregion?view=net-9.0#system-threading-thread-begincriticalregion)|Notifies a host that execution is about to enter a region of code in which the effects of a thread abort or unhandled exception might jeopardize other tasks in the application domain.|
|[BeginThreadAffinity()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.beginthreadaffinity?view=net-9.0#system-threading-thread-beginthreadaffinity)|Notifies a host that managed code is about to execute instructions that depend on the identity of the current physical operating system thread.|
|[DisableComObjectEagerCleanup()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.disablecomobjecteagercleanup?view=net-9.0#system-threading-thread-disablecomobjecteagercleanup)|Turns off automatic cleanup of runtime callable wrappers (RCW) for the current thread.|
|[EndCriticalRegion()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.endcriticalregion?view=net-9.0#system-threading-thread-endcriticalregion)|Notifies a host that execution is about to enter a region of code in which the effects of a thread abort or unhandled exception are limited to the current task.|
|[EndThreadAffinity()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.endthreadaffinity?view=net-9.0#system-threading-thread-endthreadaffinity)|Notifies a host that managed code has finished executing instructions that depend on the identity of the current physical operating system thread.|
|[Equals(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.object.equals?view=net-9.0#system-object-equals(system-object))|Determines whether the specified object is equal to the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[Finalize()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.finalize?view=net-9.0#system-threading-thread-finalize)|Ensures that resources are freed and other cleanup operations are performed when the garbage collector reclaims the [Thread](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread?view=net-9.0) object.|
|[FreeNamedDataSlot(String)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.freenameddataslot?view=net-9.0#system-threading-thread-freenameddataslot(system-string))|Eliminates the association between a name and a slot, for all threads in the process. For better performance, use fields that are marked with the [ThreadStaticAttribute](https://learn.microsoft.com/en-us/dotnet/api/system.threadstaticattribute?view=net-9.0) attribute instead.|
|[GetApartmentState()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.getapartmentstate?view=net-9.0#system-threading-thread-getapartmentstate)|Returns an [ApartmentState](https://learn.microsoft.com/en-us/dotnet/api/system.threading.apartmentstate?view=net-9.0) value indicating the apartment state.|
|[GetCompressedStack()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.getcompressedstack?view=net-9.0#system-threading-thread-getcompressedstack)|**Obsolete.**<br><br>Returns a [CompressedStack](https://learn.microsoft.com/en-us/dotnet/api/system.threading.compressedstack?view=net-9.0) object that can be used to capture the stack for the current thread.|
|[GetCurrentProcessorId()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.getcurrentprocessorid?view=net-9.0#system-threading-thread-getcurrentprocessorid)|Gets an ID used to indicate on which processor the current thread is executing.|
|[GetData(LocalDataStoreSlot)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.getdata?view=net-9.0#system-threading-thread-getdata(system-localdatastoreslot))|Retrieves the value from the specified slot on the current thread, within the current thread's current domain. For better performance, use fields that are marked with the [ThreadStaticAttribute](https://learn.microsoft.com/en-us/dotnet/api/system.threadstaticattribute?view=net-9.0) attribute instead.|
|[GetDomain()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.getdomain?view=net-9.0#system-threading-thread-getdomain)|Returns the current domain in which the current thread is running.|
|[GetDomainID()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.getdomainid?view=net-9.0#system-threading-thread-getdomainid)|Returns a unique application domain identifier.|
|[GetHashCode()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.gethashcode?view=net-9.0#system-threading-thread-gethashcode)|Returns a hash code for the current thread.|
|[GetNamedDataSlot(String)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.getnameddataslot?view=net-9.0#system-threading-thread-getnameddataslot(system-string))|Looks up a named data slot. For better performance, use fields that are marked with the [ThreadStaticAttribute](https://learn.microsoft.com/en-us/dotnet/api/system.threadstaticattribute?view=net-9.0) attribute instead.|
|[GetType()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gettype?view=net-9.0#system-object-gettype)|Gets the [Type](https://learn.microsoft.com/en-us/dotnet/api/system.type?view=net-9.0) of the current instance.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[Interrupt()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.interrupt?view=net-9.0#system-threading-thread-interrupt)|Interrupts a thread that is in the [WaitSleepJoin](https://learn.microsoft.com/en-us/dotnet/api/system.threading.threadstate?view=net-9.0#system-threading-threadstate-waitsleepjoin) thread state.|
|[Join()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.join?view=net-9.0#system-threading-thread-join)|Blocks the calling thread until the thread represented by this instance terminates, while continuing to perform standard COM and `SendMessage` pumping.|
|[Join(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.join?view=net-9.0#system-threading-thread-join(system-int32))|Blocks the calling thread until the thread represented by this instance terminates or the specified time elapses, while continuing to perform standard COM and SendMessage pumping.|
|[Join(TimeSpan)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.join?view=net-9.0#system-threading-thread-join(system-timespan))|Blocks the calling thread until the thread represented by this instance terminates or the specified time elapses, while continuing to perform standard COM and SendMessage pumping.|
|[MemberwiseClone()](https://learn.microsoft.com/en-us/dotnet/api/system.object.memberwiseclone?view=net-9.0#system-object-memberwiseclone)|Creates a shallow copy of the current [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0).<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[MemoryBarrier()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.memorybarrier?view=net-9.0#system-threading-thread-memorybarrier)|Synchronizes memory access as follows: The processor executing the current thread cannot reorder instructions in such a way that memory accesses prior to the call to [MemoryBarrier()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.memorybarrier?view=net-9.0#system-threading-thread-memorybarrier) execute after memory accesses that follow the call to [MemoryBarrier()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.memorybarrier?view=net-9.0#system-threading-thread-memorybarrier).|
|[ResetAbort()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.resetabort?view=net-9.0#system-threading-thread-resetabort)|**Obsolete.**<br><br>Cancels an [Abort(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.abort?view=net-9.0#system-threading-thread-abort(system-object)) requested for the current thread.|
|[Resume()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.resume?view=net-9.0#system-threading-thread-resume)|**Obsolete.**<br><br>Resumes a thread that has been suspended.|
|[SetApartmentState(ApartmentState)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.setapartmentstate?view=net-9.0#system-threading-thread-setapartmentstate(system-threading-apartmentstate))|Sets the apartment state of a thread before it is started.|
|[SetCompressedStack(CompressedStack)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.setcompressedstack?view=net-9.0#system-threading-thread-setcompressedstack(system-threading-compressedstack))|**Obsolete.**<br><br>Applies a captured [CompressedStack](https://learn.microsoft.com/en-us/dotnet/api/system.threading.compressedstack?view=net-9.0) to the current thread.|
|[SetData(LocalDataStoreSlot, Object)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.setdata?view=net-9.0#system-threading-thread-setdata(system-localdatastoreslot-system-object))|Sets the data in the specified slot on the currently running thread, for that thread's current domain. For better performance, use fields marked with the [ThreadStaticAttribute](https://learn.microsoft.com/en-us/dotnet/api/system.threadstaticattribute?view=net-9.0) attribute instead.|
|[Sleep(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.sleep?view=net-9.0#system-threading-thread-sleep(system-int32))|Suspends the current thread for the specified number of milliseconds.|
|[Sleep(TimeSpan)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.sleep?view=net-9.0#system-threading-thread-sleep(system-timespan))|Suspends the current thread for the specified amount of time.|
|[SpinWait(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.spinwait?view=net-9.0#system-threading-thread-spinwait(system-int32))|Causes a thread to wait the number of times defined by the `iterations` parameter.|
|[Start()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.start?view=net-9.0#system-threading-thread-start)|Causes the operating system to change the state of the current instance to [Running](https://learn.microsoft.com/en-us/dotnet/api/system.threading.threadstate?view=net-9.0#system-threading-threadstate-running).|
|[Start(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.start?view=net-9.0#system-threading-thread-start(system-object))|Causes the operating system to change the state of the current instance to [Running](https://learn.microsoft.com/en-us/dotnet/api/system.threading.threadstate?view=net-9.0#system-threading-threadstate-running), and optionally supplies an object containing data to be used by the method the thread executes.|
|[Suspend()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.suspend?view=net-9.0#system-threading-thread-suspend)|**Obsolete.**<br><br>Either suspends the thread, or if the thread is already suspended, has no effect.|
|[ToString()](https://learn.microsoft.com/en-us/dotnet/api/system.object.tostring?view=net-9.0#system-object-tostring)|Returns a string that represents the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[TrySetApartmentState(ApartmentState)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.trysetapartmentstate?view=net-9.0#system-threading-thread-trysetapartmentstate(system-threading-apartmentstate))|Sets the apartment state of a thread before it is started.|
|[UnsafeStart()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.unsafestart?view=net-9.0#system-threading-thread-unsafestart)|Causes the operating system to change the state of the current instance to [Running](https://learn.microsoft.com/en-us/dotnet/api/system.threading.threadstate?view=net-9.0#system-threading-threadstate-running).|
|[UnsafeStart(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.thread.unsafestart?view=net-9.0#system-threading-thread-unsafestart(system-object))|Causes the operating system to change the state of the current instance to [Running](https://learn.microsoft.com/en-us/dotnet/api/system.threading.threadstate?view=net-9.0#system-threading-threadstate-running), and optionally supplies an object containing data to be used by the method the thread executes.|
## Properties
 ```cs
 using System;
using System.Diagnostics;
using System.Threading;

public class Example2
{
   public static void Main()
   {
      var th = new Thread(ExecuteInForeground);
      th.Start();
      Thread.Sleep(1000);
      Console.WriteLine("Main thread ({0}) exiting...",
                        Thread.CurrentThread.ManagedThreadId);
   }

   private static void ExecuteInForeground()
   {
      var sw = Stopwatch.StartNew();
      Console.WriteLine("Thread {0}: {1}, Priority {2}",
                        Thread.CurrentThread.ManagedThreadId,
                        Thread.CurrentThread.ThreadState,
                        Thread.CurrentThread.Priority);
      do {
         Console.WriteLine("Thread {0}: Elapsed {1:N2} seconds",
                           Thread.CurrentThread.ManagedThreadId,
                           sw.ElapsedMilliseconds / 1000.0);
         Thread.Sleep(500);
      } while (sw.ElapsedMilliseconds <= 5000);
      sw.Stop();
   }
}
// The example displays output like the following:
//       Thread 3: Running, Priority Normal
//       Thread 3: Elapsed 0.00 seconds
//       Thread 3: Elapsed 0.51 seconds
//       Main thread (1) exiting...
//       Thread 3: Elapsed 1.02 seconds
//       Thread 3: Elapsed 1.53 seconds
//       Thread 3: Elapsed 2.05 seconds
//       Thread 3: Elapsed 2.55 seconds
//       Thread 3: Elapsed 3.07 seconds
//       Thread 3: Elapsed 3.57 seconds
//       Thread 3: Elapsed 4.07 seconds
//       Thread 3: Elapsed 4.58 seconds
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
