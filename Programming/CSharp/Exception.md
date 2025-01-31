---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Exception handling statements](Exception%20handling%20statements.md)
___
## Constructors

| [Exception()](https://learn.microsoft.com/en-us/dotnet/api/system.exception.-ctor?view=net-9.0#system-exception-ctor)                                                  | Initializes a new instance of the [Exception](https://learn.microsoft.com/en-us/dotnet/api/system.exception?view=net-9.0) class.                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Exception(String, Exception)](https://learn.microsoft.com/en-us/dotnet/api/system.exception.-ctor?view=net-9.0#system-exception-ctor(system-string-system-exception)) | Initializes a new instance of the [Exception](https://learn.microsoft.com/en-us/dotnet/api/system.exception?view=net-9.0) class with a specified error message and a reference to the inner exception that is the cause of this exception. |
| [Exception(String)](https://learn.microsoft.com/en-us/dotnet/api/system.exception.-ctor?view=net-9.0#system-exception-ctor(system-string))                             | Initializes a new instance of the [Exception](https://learn.microsoft.com/en-us/dotnet/api/system.exception?view=net-9.0) class with a specified error message.                                                                            |

## Properties

| [Data](https://learn.microsoft.com/en-us/dotnet/api/system.exception.data?view=net-9.0#system-exception-data)                               | Gets a collection of key/value pairs that provide additional user-defined information about the exception.                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| [HelpLink](https://learn.microsoft.com/en-us/dotnet/api/system.exception.helplink?view=net-9.0#system-exception-helplink)                   | Gets or sets a link to the help file associated with this exception.                                                                         |
| [HResult](https://learn.microsoft.com/en-us/dotnet/api/system.exception.hresult?view=net-9.0#system-exception-hresult)                      | Gets or sets HRESULT, a coded numerical value that is assigned to a specific exception.                                                      |
| [InnerException](https://learn.microsoft.com/en-us/dotnet/api/system.exception.innerexception?view=net-9.0#system-exception-innerexception) | Gets the [Exception](https://learn.microsoft.com/en-us/dotnet/api/system.exception?view=net-9.0) instance that caused the current exception. |
| [Message](https://learn.microsoft.com/en-us/dotnet/api/system.exception.message?view=net-9.0#system-exception-message)                      | Gets a message that describes the current exception.                                                                                         |
| [Source](https://learn.microsoft.com/en-us/dotnet/api/system.exception.source?view=net-9.0#system-exception-source)                         | Gets or sets the name of the application or the object that causes the error.                                                                |
| [StackTrace](https://learn.microsoft.com/en-us/dotnet/api/system.exception.stacktrace?view=net-9.0#system-exception-stacktrace)             | Gets a string representation of the immediate frames on the call stack.                                                                      |
| [TargetSite](https://learn.microsoft.com/en-us/dotnet/api/system.exception.targetsite?view=net-9.0#system-exception-targetsite)             | Gets the method that throws the current exception.                                                                                           |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
