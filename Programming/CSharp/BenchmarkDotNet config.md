---
date_added: 2025-03-19
tags:
  - csharp
---
Up: [BenchmarkDotnet](BenchmarkDotnet.md)
___
The `ManualConfig` class allows you to create a fully customized configuration.
## Job
Jobs in BenchmarkDotNet define the environment and runtime characteristics for your benchmarks. Your example configures the following job parameters:

#### Parameters

1. **LaunchCount**: Controls how many times BenchmarkDotNet will launch a separate process to run the benchmark. Multiple launches help reduce environmental noise. Your config uses 1, which is suitable for quick development cycles.
    
2. **WarmupCount**: Determines how many iterations are performed before the actual measurements begin. This allows the JIT compiler to optimize the code and reach a steady state. You've set this to 1, which is minimal - in production benchmarks, the default (automatically determined) is typically better.
    
3. **IterationCount**: Specifies how many measurement iterations will be performed. Each iteration provides a measurement data point. You've set 4 iterations, which is relatively low. For publishable results, consider more iterations or letting BenchmarkDotNet determine this automatically.
    
4. **InvocationCount**: Defines how many times the benchmark method will be called within a single iteration. For quick benchmarks, higher values reduce measurement overhead. You've set 4 invocations.
    
5. **UnrollFactor**: Controls how many benchmark method invocations will be performed in a single method call. This affects loop unrolling and can impact measurements. You've set this to 2.

 ```cs
 using BenchmarkDotNet.Columns;  
using BenchmarkDotNet.Configs;  
using BenchmarkDotNet.Jobs;  
using BenchmarkDotNet.Reports;  
  
namespace PerformanceDemo;  
  
public class Config : ManualConfig  
{  
    public Config()  
    {        AddJob(Job.Default  
            .WithLaunchCount(1)  
            .WithWarmupCount(1)  
            .WithIterationCount(4)  
            .WithInvocationCount(4)  
            .WithUnrollFactor(2));  
        AddLogger(Console.Default);  
  
        WithOptions(ConfigOptions.DisableOptimizationsValidator);  
  
        AddColumnProvider(DefaultColumnProviders.Instance);  
        SummaryStyle = SummaryStyle.Default.WithMaxParameterColumnWidth(50);  
    }}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
