---
date_added: 2025-03-19
tags:
  - csharp
---
Up: [Performance](Performance.md)
___
Is part of System.Diagnostics namespace

Provides a set of methods and properties that you can use to accurately measure elapsed time.
## Constructors

Expand table

|   |   |
|---|---|
|[Stopwatch()](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.-ctor?view=net-9.0#system-diagnostics-stopwatch-ctor)|Initializes a new instance of the [Stopwatch](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch?view=net-9.0) class.|

## Fields

Expand table

|   |   |
|---|---|
|[Frequency](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.frequency?view=net-9.0#system-diagnostics-stopwatch-frequency)|Gets the frequency of the timer as the number of ticks per second. This field is read-only.|
|[IsHighResolution](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.ishighresolution?view=net-9.0#system-diagnostics-stopwatch-ishighresolution)|Indicates whether the timer is based on a high-resolution performance counter. This field is read-only.|

## Properties

Expand table

|   |   |
|---|---|
|[Elapsed](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.elapsed?view=net-9.0#system-diagnostics-stopwatch-elapsed)|Gets the total elapsed time measured by the current instance.|
|[ElapsedMilliseconds](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.elapsedmilliseconds?view=net-9.0#system-diagnostics-stopwatch-elapsedmilliseconds)|Gets the total elapsed time measured by the current instance, in milliseconds.|
|[ElapsedTicks](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.elapsedticks?view=net-9.0#system-diagnostics-stopwatch-elapsedticks)|Gets the total elapsed time measured by the current instance, in timer ticks.|
|[IsRunning](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.isrunning?view=net-9.0#system-diagnostics-stopwatch-isrunning)|Gets a value indicating whether the [Stopwatch](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch?view=net-9.0) timer is running.|

## Methods

Expand table

|   |   |
|---|---|
|[Equals(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.object.equals?view=net-9.0#system-object-equals\(system-object\))|Determines whether the specified object is equal to the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[GetElapsedTime(Int64, Int64)](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.getelapsedtime?view=net-9.0#system-diagnostics-stopwatch-getelapsedtime\(system-int64-system-int64\))|Gets the elapsed time between two timestamps retrieved using [GetTimestamp()](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.gettimestamp?view=net-9.0#system-diagnostics-stopwatch-gettimestamp).|
|[GetElapsedTime(Int64)](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.getelapsedtime?view=net-9.0#system-diagnostics-stopwatch-getelapsedtime\(system-int64\))|Gets the elapsed time since the `startingTimestamp` value retrieved using [GetTimestamp()](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.gettimestamp?view=net-9.0#system-diagnostics-stopwatch-gettimestamp).|
|[GetHashCode()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gethashcode?view=net-9.0#system-object-gethashcode)|Serves as the default hash function.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[GetTimestamp()](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.gettimestamp?view=net-9.0#system-diagnostics-stopwatch-gettimestamp)|Gets the current number of ticks in the timer mechanism.|
|[GetType()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gettype?view=net-9.0#system-object-gettype)|Gets the [Type](https://learn.microsoft.com/en-us/dotnet/api/system.type?view=net-9.0) of the current instance.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[MemberwiseClone()](https://learn.microsoft.com/en-us/dotnet/api/system.object.memberwiseclone?view=net-9.0#system-object-memberwiseclone)|Creates a shallow copy of the current [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0).<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[Reset()](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.reset?view=net-9.0#system-diagnostics-stopwatch-reset)|Stops time interval measurement and resets the elapsed time to zero.|
|[Restart()](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.restart?view=net-9.0#system-diagnostics-stopwatch-restart)|Stops time interval measurement, resets the elapsed time to zero, and starts measuring elapsed time.|
|[Start()](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.start?view=net-9.0#system-diagnostics-stopwatch-start)|Starts, or resumes, measuring elapsed time for an interval.|
|[StartNew()](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.startnew?view=net-9.0#system-diagnostics-stopwatch-startnew)|Initializes a new [Stopwatch](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch?view=net-9.0) instance, sets the elapsed time property to zero, and starts measuring elapsed time.|
|[Stop()](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.stop?view=net-9.0#system-diagnostics-stopwatch-stop)|Stops measuring elapsed time for an interval.|
|[ToString()](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.tostring?view=net-9.0#system-diagnostics-stopwatch-tostring)|Returns the [Elapsed](https://learn.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch.elapsed?view=net-9.0#system-diagnostics-stopwatch-elapsed) time as a string.|
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
