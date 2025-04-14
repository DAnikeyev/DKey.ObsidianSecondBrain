---
date_added: 2025-04-03
tags:
  - csharp
---
Up: [Exception](Exception.md)
___
```cs
public class MyFileNotFoundException : Exception
{
}
```
The following best practices concern custom exception types:

- [End exception class names with `Exception`](https://learn.microsoft.com/en-us/dotnet/standard/exceptions/best-practices-for-exceptions#end-exception-class-names-with-exception)
- [Include three constructors](https://learn.microsoft.com/en-us/dotnet/standard/exceptions/best-practices-for-exceptions#include-three-constructors)
- [Provide additional properties as needed](https://learn.microsoft.com/en-us/dotnet/standard/exceptions/best-practices-for-exceptions#provide-additional-properties-as-needed)

Exception types must implement the following three public constructors:

- public NewException()
    
- public NewException(string)
    
- public NewException(string, Exception)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
