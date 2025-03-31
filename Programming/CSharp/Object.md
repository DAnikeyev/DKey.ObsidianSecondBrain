---
date_added: 2024-10-08
tags:
  - csharp
sr-due: 2025-04-04
sr-interval: 3
sr-ease: 259
---
Up: [Reference Type](Reference%20Type.md)
___

As indicated earlier, all .NET classes are ultimately derived from System.Object. In fact, if you don’t
specify a base class when you define a class, the compiler automatically assumes that it derives from Object.


## Methods

| [Equals(Object, Object)](https://learn.microsoft.com/en-us/dotnet/api/system.object.equals?view=net-9.0#system-object-equals\(system-object-system-object\))                            | Determines whether the specified object instances are considered equal.                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Equals(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.object.equals?view=net-9.0#system-object-equals\(system-object\))                                                  | Determines whether the specified object is equal to the current object.                                                                             |
| [Finalize()](https://learn.microsoft.com/en-us/dotnet/api/system.object.finalize?view=net-9.0#system-object-finalize)                                                                   | Allows an object to try to free resources and perform other cleanup operations before it is reclaimed by garbage collection.                        |
| [GetHashCode()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gethashcode?view=net-9.0#system-object-gethashcode)                                                          | Serves as the default hash function.                                                                                                                |
| [GetType()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gettype?view=net-9.0#system-object-gettype)                                                                      | Gets the [Type](https://learn.microsoft.com/en-us/dotnet/api/system.type?view=net-9.0) of the current instance.                                     |
| [MemberwiseClone()](https://learn.microsoft.com/en-us/dotnet/api/system.object.memberwiseclone?view=net-9.0#system-object-memberwiseclone)                                              | Creates a shallow copy of the current [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0).                            |
| [ReferenceEquals(Object, Object)](https://learn.microsoft.com/en-us/dotnet/api/system.object.referenceequals?view=net-9.0#system-object-referenceequals\(system-object-system-object\)) | Determines whether the specified [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0) instances are the same instance. |
| [ToString()](https://learn.microsoft.com/en-us/dotnet/api/system.object.tostring?view=net-9.0#system-object-tostring)                                                                   | Returns a string that represents the current object.                                                                                                |

Value of any type can be assigned to a variable of type `object` except [Ref Struct](Ref%20Struct.md). For [[Value type]]  [Boxing and Unboxing](Boxing%20and%20Unboxing) is used.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
