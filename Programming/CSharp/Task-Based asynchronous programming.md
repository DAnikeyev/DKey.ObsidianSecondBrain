---
date_added: 2025-01-30
tags:
  - csharp
---
Up: [Asynchronous programming](Asynchronous%20programming.md)
___
## Positives
 - Workflow is easy to manage and understand
 - Supports [Cancellation Token](Cancellation%20Token.md) usage and progress reporting
 - [[Task]] can be awaited to avoid [ThreadPool](ThreadPool.md) starvation
 - Tasks integrates **Error Handling**
## Negatives
 - Debugging task-based code can sometimes be more challenging due to the abstraction layer.
 - Overhead of creating and managing tasks, including working with **State machine**
## Naming
Async methods should be named that way:
`Async Task\<Tresult> GetAsync();`

The parameters of a TAP method should match the parameters of its synchronous counterpart and should be provided in the same order. `Out` or `ref` should be avoided entirely
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
