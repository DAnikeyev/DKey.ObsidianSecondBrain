---
date_added: 2025-03-22
tags:
  - csharp
---
Up: [Channel T](Channel%20T.md)
___
## Generator
```csharp
static ChannelReader<string> CreateMessenger(string msg, int count)
{
    var ch = Channel.CreateUnbounded<string>();
    var rnd = new Random();

    Task.Run(async () =>
    {
        for (int i = 0; i < count; i++)
        {
            await ch.Writer.WriteAsync($"{msg} {i}");
            await Task.Delay(TimeSpan.FromSeconds(rnd.Next(3)));
        }
        ch.Writer.Complete();
    });

    return ch.Reader;
}
```

## Multiplexer (Merger)
```csharp
static ChannelReader<T> Merge<T>(
    ChannelReader<T> first, ChannelReader<T> second)
{
    var output = Channel.CreateUnbounded<T>();

    Task.Run(async () =>
    {
        await foreach (var item in first.ReadAllAsync())
            await output.Writer.WriteAsync(item);
    });
    Task.Run(async () =>
    {
        await foreach (var item in second.ReadAllAsync())
            await output.Writer.WriteAsync(item);
    });

    return output;
}
```

## Demultiplexer
```csharp
static IList<ChannelReader<T>> Split<T>(ChannelReader<T> ch, int n)
{
    var outputs = new Channel<T>[n];

    for (int i = 0; i < n; i++)
        outputs[i] = Channel.CreateUnbounded<T>();

    Task.Run(async () =>
    {
        var index = 0;
        await foreach (var item in ch.ReadAllAsync())
        {
            await outputs[index].Writer.WriteAsync(item);
            index = (index + 1) % n;
        }

        foreach (var ch in outputs)
            ch.Writer.Complete();
    });

    return outputs.Select(ch => ch.Reader).ToArray();
}
```

### Timeout
```csharp
var joe = CreateMessenger("Joe", 10);
var cts = new CancellationTokenSource();
cts.CancelAfter(TimeSpan.FromSeconds(5));

try
{
    await foreach (var item in joe.ReadAllAsync(cts.Token))
        Console.WriteLine(item);

    Console.WriteLine("Joe sent all of his messages."); 
}
catch (OperationCanceledException)
{
    Console.WriteLine("Joe, you are too slow!");
}
```

## Quit
```csharp
 Task.Run(async () =>
    {
        var rnd = new Random();
        for (int i = 0; i < count; i++)
        {
            if (token.IsCancellationRequested)
            {
                await ch.Writer.WriteAsync($"{msg} says bye!");
                break;
            }
            await ch.Writer.WriteAsync($"{msg} {i}");
            await Task.Delay(TimeSpan.FromSeconds(rnd.Next(0, 3)));
        }
        ch.Writer.Complete();
    });
```

## Pipeline
```csharp
var fileGen = GetFilesRecursively("path_to/node_modules");
var sourceCodeFiles = FilterByExtension(
    fileGen, new HashSet<string> { ".js", ".ts" });
var counter = GetLineCount(sourceCodeFiles);
```
![](Pasted%20image%2020250322050621.png)

### Error handling
To achieve good error handling, our pipeline needs to satisfy the following:

1. Invalid input should not propagate to the next stage
2. Invalid input should not cause the pipeline to stop. The pipeline should continue to process the inputs thereafter.
3. The pipeline should not swallow errors. All the errors should be reported.

```cs
+     (ChannelReader<(FileInfo file, int lines)> output,
+      ChannelReader<string> errors)
    GetLineCount(ChannelReader<FileInfo> input)
    {
        var output = Channel.CreateUnbounded<(FileInfo, int)>();
+       var errors = Channel.CreateUnbounded<string>();

        Task.Run(async () =>
        {
            await foreach (var file in input.ReadAllAsync())
            {
                var lines = CountLines(file);
+               if (lines == 0)
+                   await errors.Writer.WriteAsync(
+                       $"[Error] Empty file {file}");
+               else
+                   await output.Writer.WriteAsync((file, lines));
            }
            output.Writer.Complete();
+           errors.Writer.Complete();
        });
+       return (output, errors);
    }
    ```

## Cancellation
```csharp
ChannelReader<string> GetFilesRecursively(
    string root, CancellationToken token = default)
{
    var output = Channel.CreateUnbounded<string>();

    async Task WalkDir(string path)
    {
        if (token.IsCancellationRequested)
            throw new OperationCanceledException();
            
        foreach (var file in Directory.GetFiles(path))
            await output.Writer.WriteAsync(file, token);
            
        var tasks = Directory.GetDirectories(path).Select(WalkDir);
        await Task.WhenAll(tasks.ToArray()));
    }

    Task.Run(async () =>
    {
        try
        {
            await WalkDir(root);
        }
        catch (OperationCanceledException) { Console.WriteLine("Cancelled."); }
        finally { output.Writer.Complete(); }
    });

    return output;
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
