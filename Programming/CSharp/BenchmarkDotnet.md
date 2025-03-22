---
date_added: 2025-03-19
tags:
  - csharp
---
Up: [Performance](Performance.md)
___
 BenchmarkDotNet is an open-source benchmarking tool for .NET that makes it easy to measure the performance of your code. It handles all the complexities involved in reliable benchmarking, such as:

- Warming up the JIT compiler
- Handling garbage collection appropriately
- Running enough iterations to get statistically significant results
- Presenting results in a clear, actionable format

```cs
[Config(typeof(Config))]
public class MyBenchmarks
{
    [Benchmark]
    public void Method1() { /* ... */ }
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
