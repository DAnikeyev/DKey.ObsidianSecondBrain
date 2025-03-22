---
date_added: 2025-03-22
tags:
  - csharp
---
Up: [Creating Channel](Creating%20Channel.md)
___

|   |   |
|---|---|
|[BoundedChannelOptions(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.boundedchanneloptions.-ctor?view=net-9.0#system-threading-channels-boundedchanneloptions-ctor\(system-int32\))|Initializes the options.|

## Properties

|                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [AllowSynchronousContinuations](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channeloptions.allowsynchronouscontinuations?view=net-9.0#system-threading-channels-channeloptions-allowsynchronouscontinuations) | `true` if operations performed on a channel may synchronously invoke continuations subscribed to notifications of pending async operations; `false` if all continuations should be invoked asynchronously.<br><br>(Inherited from [ChannelOptions](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channeloptions?view=net-9.0)) |
| [Capacity](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.boundedchanneloptions.capacity?view=net-9.0#system-threading-channels-boundedchanneloptions-capacity)                                                  | Gets or sets the maximum number of items the bounded channel may store.                                                                                                                                                                                                                                                                                 |
| [FullMode](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.boundedchanneloptions.fullmode?view=net-9.0#system-threading-channels-boundedchanneloptions-fullmode)                                                  | Gets or sets the behavior incurred by write operations when the channel is full.                                                                                                                                                                                                                                                                        |
| [SingleReader](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channeloptions.singlereader?view=net-9.0#system-threading-channels-channeloptions-singlereader)                                                    | `true` readers from the channel guarantee that there will only ever be at most one read operation at a time; `false` if no such constraint is guaranteed.<br><br>(Inherited from [ChannelOptions](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channeloptions?view=net-9.0))                                                  |
| [SingleWriter](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channeloptions.singlewriter?view=net-9.0#system-threading-channels-channeloptions-singlewriter)                                                    | `true` if writers to the channel guarantee that there will only ever be at most one write operation at a time; `false` if no such constraint is guaranteed.<br><br>(Inherited from [ChannelOptions](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channeloptions?view=net-9.0))                                                |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
