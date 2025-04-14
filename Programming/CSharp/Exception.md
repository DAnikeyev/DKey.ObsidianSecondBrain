---
date_added: 2025-01-31
tags:
  - csharp
sr-due: 2025-04-04
sr-interval: 3
sr-ease: 250
---
Up: [Exception handling statements](Exception%20handling%20statements.md)
___
## Common exceptions
1. **System.Exception**: This is the base class for all exceptions in C#. It is a good practice to catch more specific exceptions, but `Exception` can be used as a catch-all.
    
2. **System.ArgumentException**: This exception is thrown when one of the arguments provided to a method is not valid.
    
3. **System.ArgumentNullException**: A subclass of `ArgumentException`, this exception is thrown when a null reference is passed to a method that does not accept it as a valid argument.
    
4. **System.ArgumentOutOfRangeException**: Another subclass of `ArgumentException`, this exception is thrown when the value of an argument is outside the allowable range of values as defined by the invoked method.
    
5. **System.InvalidOperationException**: This exception is thrown when a method call is invalid for the object's current state.
    
6. **System.NullReferenceException**: This exception is thrown when there is an attempt to dereference a null object reference.
    
7. **System.IndexOutOfRangeException**: This exception is thrown when an attempt is made to access an element of an array or collection with an index that is outside its bounds.
    
8. **System.IO.IOException**: This exception is thrown when an I/O error occurs. It is the base class for exceptions thrown while accessing information using streams, files, and directories.
    
9. **System.NotImplementedException**: This exception is thrown when a requested method or operation is not implemented.
    
10. **System.NotSupportedException**: This exception is thrown when an invoked method is not supported, or when there is an attempt to read, seek, or write to a stream that does not support the invoked functionality.
    
11. **System.FormatException**: This exception is thrown when the format of an argument is invalid, such as when parsing a string to a number and the string is not in a correct format.
    
12. **System.OutOfMemoryException**: This exception is thrown when there is not enough memory to continue the execution of a program.
    
13. **System.OverflowException**: This exception is thrown when an arithmetic operation in a checked context overflows.
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

### Hresult
HRESULT is a 32-bit value, divided into three different fields: a severity code, a facility code, and an error code. The severity code indicates whether the return value represents information, warning, or error. The facility code identifies the area of the system responsible for the error. The error code is a unique number that is assigned to represent the exception. Each exception is mapped to a distinct HRESULT. You can set it in constructor.

### ApplicationException
Were supposed to be for custom exception, but not used now for this, some exception derive from it like `TargetInvocationException`

### Performance:
Avoid using Exceptions as data filters. For example, use `int.TryParse` instead of `int.Parse` inside try-catch block.

### Line
`#line` preprocessor directive can be used to specify the line number in the source file at which a particular piece of code appears. This can be useful when debugging.

### If exception is not caught
.NET runtime would catch it. If an exception occurs that
your code does not handle, the execution flow simply passes right out of your program and is trapped by this
catch block in the .NET runtime. The runtime then displays an error message to the user and terminates the program. Exception is also sent to Windows Event Log. See EventViewer.

### CLS compliant
RuntimeWrappedException : Exception may be used to wrap exceptions that are not CLS-compliant.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
