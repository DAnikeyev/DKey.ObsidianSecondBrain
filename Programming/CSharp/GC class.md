---
date_added: 2025-02-17
tags:
  - csharp
---
Up: [Garbage Collector](Garbage%20Collector.md)
___
Controls the system garbage collector, a service that automatically reclaims unused memory.

## Properties

|   |   |
|---|---|
|[MaxGeneration](https://learn.microsoft.com/en-us/dotnet/api/system.gc.maxgeneration?view=net-9.0#system-gc-maxgeneration)|Gets the maximum number of generations that the system currently supports.|

## Methods

|   |   |
|---|---|
|[AddMemoryPressure(Int64)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.addmemorypressure?view=net-9.0#system-gc-addmemorypressure\(system-int64\))|Informs the runtime of a large allocation of unmanaged memory that should be taken into account when scheduling garbage collection.|
|[AllocateArray<T>(Int32, Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.allocatearray?view=net-9.0#system-gc-allocatearray-1\(system-int32-system-boolean\))|Allocates an array.|
|[AllocateUninitializedArray<T>(Int32, Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.allocateuninitializedarray?view=net-9.0#system-gc-allocateuninitializedarray-1\(system-int32-system-boolean\))|Allocates an array while skipping zero-initialization, if possible.|
|[CancelFullGCNotification()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.cancelfullgcnotification?view=net-9.0#system-gc-cancelfullgcnotification)|Cancels the registration of a garbage collection notification.|
|[Collect()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.collect?view=net-9.0#system-gc-collect)|Forces an immediate garbage collection of all generations.|
|[Collect(Int32, GCCollectionMode, Boolean, Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.collect?view=net-9.0#system-gc-collect\(system-int32-system-gccollectionmode-system-boolean-system-boolean\))|Forces a garbage collection from generation 0 through a specified generation, at a time specified by a [GCCollectionMode](https://learn.microsoft.com/en-us/dotnet/api/system.gccollectionmode?view=net-9.0) value, with values that specify whether the collection should be blocking and compacting.|
|[Collect(Int32, GCCollectionMode, Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.collect?view=net-9.0#system-gc-collect\(system-int32-system-gccollectionmode-system-boolean\))|Forces a garbage collection from generation 0 through a specified generation, at a time specified by a [GCCollectionMode](https://learn.microsoft.com/en-us/dotnet/api/system.gccollectionmode?view=net-9.0) value, with a value specifying whether the collection should be blocking.|
|[Collect(Int32, GCCollectionMode)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.collect?view=net-9.0#system-gc-collect\(system-int32-system-gccollectionmode\))|Forces a garbage collection from generation 0 through a specified generation, at a time specified by a [GCCollectionMode](https://learn.microsoft.com/en-us/dotnet/api/system.gccollectionmode?view=net-9.0) value.|
|[Collect(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.collect?view=net-9.0#system-gc-collect\(system-int32\))|Forces an immediate garbage collection from generation 0 through a specified generation.|
|[CollectionCount(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.collectioncount?view=net-9.0#system-gc-collectioncount\(system-int32\))|Returns the number of times garbage collection has occurred for the specified generation of objects.|
|[EndNoGCRegion()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.endnogcregion?view=net-9.0#system-gc-endnogcregion)|Ends the no GC region latency mode.|
|[GetAllocatedBytesForCurrentThread()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.getallocatedbytesforcurrentthread?view=net-9.0#system-gc-getallocatedbytesforcurrentthread)|Gets the total number of bytes allocated to the current thread since the beginning of its lifetime.|
|[GetConfigurationVariables()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.getconfigurationvariables?view=net-9.0#system-gc-getconfigurationvariables)|Gets the configurations used by the garbage collector.|
|[GetGCMemoryInfo()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.getgcmemoryinfo?view=net-9.0#system-gc-getgcmemoryinfo)|Gets garbage collection memory information.|
|[GetGCMemoryInfo(GCKind)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.getgcmemoryinfo?view=net-9.0#system-gc-getgcmemoryinfo\(system-gckind\))|Gets garbage collection memory information.|
|[GetGeneration(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.getgeneration?view=net-9.0#system-gc-getgeneration\(system-object\))|Returns the current generation number of the specified object.|
|[GetGeneration(WeakReference)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.getgeneration?view=net-9.0#system-gc-getgeneration\(system-weakreference\))|Returns the current generation number of the target of a specified weak reference.|
|[GetTotalAllocatedBytes(Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.gettotalallocatedbytes?view=net-9.0#system-gc-gettotalallocatedbytes\(system-boolean\))|Gets a count of the bytes allocated over the lifetime of the process. The returned value does not include any native allocations.|
|[GetTotalMemory(Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.gettotalmemory?view=net-9.0#system-gc-gettotalmemory\(system-boolean\))|Retrieves the heap size excluding fragmentation. For example if the total GC heap size is 100mb and fragmentation, ie, space taken up by free objects, takes up 40mb, this API would report 60mb. A parameter indicates whether this method can wait a short interval before returning, to allow the system to collect garbage and finalize objects.|
|[GetTotalPauseDuration()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.gettotalpauseduration?view=net-9.0#system-gc-gettotalpauseduration)|Gets the total amount of time paused in GC since the beginning of the process.|
|[KeepAlive(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.keepalive?view=net-9.0#system-gc-keepalive\(system-object\))|References the specified object, which makes it ineligible for garbage collection from the start of the current routine to the point where this method is called.|
|[RefreshMemoryLimit()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.refreshmemorylimit?view=net-9.0#system-gc-refreshmemorylimit)|Instructs the Garbage Collector to reconfigure itself by detecting the various memory limits on the system.|
|[RegisterForFullGCNotification(Int32, Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.registerforfullgcnotification?view=net-9.0#system-gc-registerforfullgcnotification\(system-int32-system-int32\))|Specifies that a garbage collection notification should be raised when conditions favor full garbage collection and when the collection has been completed.|
|[RegisterNoGCRegionCallback(Int64, Action)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.registernogcregioncallback?view=net-9.0#system-gc-registernogcregioncallback\(system-int64-system-action\))|Registers a callback to be invoked when a certain amount of memory is allocated in the no GC region.|
|[RemoveMemoryPressure(Int64)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.removememorypressure?view=net-9.0#system-gc-removememorypressure\(system-int64\))|Informs the runtime that unmanaged memory has been released and no longer needs to be taken into account when scheduling garbage collection.|
|[ReRegisterForFinalize(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.reregisterforfinalize?view=net-9.0#system-gc-reregisterforfinalize\(system-object\))|Requests that the system call the finalizer for the specified object for which [SuppressFinalize(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.suppressfinalize?view=net-9.0#system-gc-suppressfinalize\(system-object\)) has previously been called.|
|[SuppressFinalize(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.suppressfinalize?view=net-9.0#system-gc-suppressfinalize\(system-object\))|Requests that the common language runtime not call the finalizer for the specified object.|
|[TryStartNoGCRegion(Int64, Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.trystartnogcregion?view=net-9.0#system-gc-trystartnogcregion\(system-int64-system-boolean\))|Attempts to disallow garbage collection during the execution of a critical path if a specified amount of memory is available, and controls whether the garbage collector does a full blocking garbage collection if not enough memory is initially available.|
|[TryStartNoGCRegion(Int64, Int64, Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.trystartnogcregion?view=net-9.0#system-gc-trystartnogcregion\(system-int64-system-int64-system-boolean\))|Attempts to disallow garbage collection during the execution of a critical path if a specified amount of memory is available for the large object heap and the small object heap, and controls whether the garbage collector does a full blocking garbage collection if not enough memory is initially available.|
|[TryStartNoGCRegion(Int64, Int64)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.trystartnogcregion?view=net-9.0#system-gc-trystartnogcregion\(system-int64-system-int64\))|Attempts to disallow garbage collection during the execution of a critical path if a specified amount of memory is available for the large object heap and the small object heap.|
|[TryStartNoGCRegion(Int64)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.trystartnogcregion?view=net-9.0#system-gc-trystartnogcregion\(system-int64\))|Attempts to disallow garbage collection during the execution of a critical path if a specified amount of memory is available.|
|[WaitForFullGCApproach()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.waitforfullgcapproach?view=net-9.0#system-gc-waitforfullgcapproach)|Returns the status of a registered notification for determining whether a full, blocking garbage collection by the common language runtime is imminent.|
|[WaitForFullGCApproach(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.waitforfullgcapproach?view=net-9.0#system-gc-waitforfullgcapproach\(system-int32\))|Returns, in a specified time-out period, the status of a registered notification for determining whether a full, blocking garbage collection by the common language runtime is imminent.|
|[WaitForFullGCApproach(TimeSpan)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.waitforfullgcapproach?view=net-9.0#system-gc-waitforfullgcapproach\(system-timespan\))|Returns, in a specified time-out period, the status of a registered notification for determining whether a full, blocking garbage collection by the common language runtime is imminent.|
|[WaitForFullGCComplete()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.waitforfullgccomplete?view=net-9.0#system-gc-waitforfullgccomplete)|Returns the status of a registered notification for determining whether a full, blocking garbage collection by the common language runtime has completed.|
|[WaitForFullGCComplete(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.waitforfullgccomplete?view=net-9.0#system-gc-waitforfullgccomplete\(system-int32\))|Returns, in a specified time-out period, the status of a registered notification for determining whether a full, blocking garbage collection by common language the runtime has completed.|
|[WaitForFullGCComplete(TimeSpan)](https://learn.microsoft.com/en-us/dotnet/api/system.gc.waitforfullgccomplete?view=net-9.0#system-gc-waitforfullgccomplete\(system-timespan\))|Returns the status of a registered notification about whether a blocking garbage collection has completed. May wait indefinitely for a full collection.|
|[WaitForPendingFinalizers()](https://learn.microsoft.com/en-us/dotnet/api/system.gc.waitforpendingfinalizers?view=net-9.0#system-gc-waitforpendingfinalizers)|Suspends the current thread until the thread that is processing the queue of finalizers has emptied that queue.|

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
