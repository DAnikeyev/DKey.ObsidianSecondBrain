---
date_added: 2025-02-27
tags:
  - csharp
---
Up: [Delegate](Delegate.md)
___
Follows [Asynchronous Programming Model (APM)](Asynchronous%20Programming%20Model%20(APM).md)
### BeginInvoke

- **Purpose**: Starts the asynchronous execution of a delegate.
- **Parameters**:
  - The same parameters as the delegate.
  - An `AsyncCallback` delegate.
  - An object representing state information.
- **Returns**: An [[IAsyncResult]] that can be used to monitor the progress of the asynchronous operation.

### EndInvoke

- **Purpose**: Retrieves the result of the asynchronous operation started by `BeginInvoke`.
- **Parameters**:
  - The `IAsyncResult` returned by `BeginInvoke`.
- **Behavior**: Blocks until the asynchronous call completes.
- **Returns**: The result of the delegate.

### GetInvocationList

- **Purpose**: Returns an array of delegates that represent the methods currently assigned to the delegate.
- **Usage**: Can be used to inspect or invoke each method individually.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
