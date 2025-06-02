---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [[LINQ]]
___
 In LINQ, many methods (e.g., `Where`, `Select`, `SelectMany`, `Skip`, `Take`) are "deferred". This means they build a query expression and wait to run until you iterate over the results or force immediate execution (for example, with `ToList()`, `Count()`, or `First()`).

![](Pasted%20image%2020250602185106.png)
## How to Identify a Deferred Method

• Typically returns an `IEnumerable<T>` and doesn't transform the sequence into a final value or collection on the spot.  
• Creates query expressions (method chains) without performing any actual iteration.  
• Requires a "finalizing" step — such as enumeration by `foreach` or calling a method like `ToList` or `Count` — to execute.

## Patterns Indicating Deferred Execution

1. Chaining of query operators that return `IEnumerable<T>` (e.g., `Where(...).Select(...)`).
2. No materialization or "terminal" step inside the method: it doesn't collect or compute aggregate results but returns another sequence.

## When Deferred Execution is Better

• You want to avoid unnecessary work if the sequence is never (or only partly) traversed.  
• Large data sets: compute results only when needed rather than up-front.  
• Makes pipelines more flexible — you can add, remove, or change parts of the chain, and only the final enumerated version is evaluated.

## Compiler generated state machine

Consider using [Enumerable.Prepend](Enumerable.Prepend.md) 
   The `Prepend` method is implemented as a call to an inner iterator method (often named something like `PrependIterator`). This method:
   - First yields the element you want to prepend.
   - Then yields each element from the source sequence.

   The use of `yield return` makes the method a deferred execution iterator. The code inside the iterator method doesn't run until you start enumerating over the returned sequence.
   
#### **Compiler-Generated State Machine:**  
   When you use `yield return`, the C# compiler translates your iterator into a compiler-generated class that implements `IEnumerable<T>` and `IEnumerator<T>`. This state machine takes care of:
   - Storing the current position in the sequence.
   - Keeping track of the next element to be returned.
   - Resuming execution on each call to `MoveNext()`.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
