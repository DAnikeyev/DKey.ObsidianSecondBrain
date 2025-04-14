---
date_added: 2025-03-19
tags:
  - csharp
---
Up: [Performance](Performance.md)
___
 - **Efficient Data Handling**:
    - Avoid unnecessary  [Boxing and Unboxing](Boxing%20and%20Unboxing.md) of value types.
    - Use [Span T](Span%20T.md) and [Memory T](Memory%20T.md) for efficient handling of contiguous memory.
    - Minimize allocations by reusing objects.
- **Optimized Collections**:
    - Use the appropriate collection type for your use case (e.g., `List<T>`, `Dictionary<TKey, TValue>`).
    - Consider using specialized collections like `ConcurrentDictionary` for thread-safe operations.
- **[Parallel](Parallel%20class.md) and [Asynchronous programming](Asynchronous%20programming.md)**:
    - Use [async](async.md) and [await](await.md) for asynchronous operations to avoid blocking threads.
    - Utilize the [Task Parallel Library](Task%20Parallel%20Library.md) (TPL) for parallel processing.
- **Efficient String Handling**:
    - Use [StringBuilder](StringBuilder.md) for concatenating multiple strings.
    - Avoid frequent string modifications.
- **Code Optimization**:
    - Profile and benchmark your code to identify bottlenecks.
    - Use caching to store frequently accessed data.
- **Efficient Logging**:    
    - Implement efficient logging mechanisms to minimize overhead.
    - Use asynchronous logging to avoid blocking operations.
### Effective Task Usage

- Use async/await for I/O-bound operations
- Use `Task.Run` for CPU-bound operations
- Consider `ValueTask` for high-performance scenarios
- Use `ConfigureAwait(false)` when appropriate
### Benchmarking
- Use [[BenchmarkDotNet]] for accurate performance measurements
- Profile before optimizing to identify bottlenecks
- Measure in release mode with realistic data sets
### [[Finalizer]]
 - Be carefull with objects with finalizers, as they are not cleaned, but put in [FinalizationQueue](FinalizationQueue.md) first during [Garbage collection process](Garbage%20collection%20process.md)
 - Use [Dispose](Dispose.md) pattern for deterministic cleanup
## Collections
 - Use [ArrayPool](ArrayPool.md) if you need to allocate and deallocate arrays frequently
 - Define the initial capacity of collections to avoid resizing
## Strings
 - Use [StringBuilder](StringBuilder.md) for efficient string concatenation
 - Avoid unnecessary string operations especially in cycles
 - Use [String Intern](String%20Intern.md) for memory optimization
 - Instead of reusing `key.ToLower()` in a loop, store it in a variable and reuse it or use `String.Compare (...,... StringComparison.OrdinalIgnoreCase)`
### Use [[Cache practices]]

## LINQ
 - Use [IEnumerable](IEnumerable.md) instead of [IList](IList.md) if possible
 - Don't call Any or Count before foreach
 - Don't use ToArray or ToList if you don't need to, so that [Deferred Execution in LINQ](Deferred%20Execution%20in%20LINQ.md) can be used
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
