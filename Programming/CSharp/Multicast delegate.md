---
date_added: 2025-02-27
tags:
  - csharp
---
Up: [Delegate](Delegate.md)
___
 Represents a multicast delegate; that is, a delegate that can have more than one element in its invocation list. 
 Actually [Delegate Operator](Delegate%20Operator.md) creates multicast delegate
## Methods
| Member               | Purpose                                                                                                                                                                                                                                        |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Method               | This property returns a System.Reflection.Method object that represents the details of the static method supported by the delegate.                                                                                                            |
| Target               | If the method to be invoked is defined at the object level (i.e., it is not static), Target returns the object that represents the method supported by the delegate. If the returned Target value is null, the method to be invoked is static. |
| Combine()            | This static method adds a method to the list supported by the delegate. In C#, this method is called using the overloaded += operation as a shorthand notation.                                                                                |
| GetInvocationList()  | This method returns an array of System.Delegate types, each representing a specific method available for invocation.                                                                                                                           |
| Remove() RemoveAll() | These static methods remove a method (or all methods) from the delegate's invocation list. In C#, the Remove() method can be implicitly called using the overloaded -= operation.                                                              |

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
