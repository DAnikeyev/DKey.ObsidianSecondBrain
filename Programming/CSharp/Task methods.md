---
date_added: 2025-01-30
tags:
  - csharp
---
Up: [[Task]]
___
 
## Task.Run

```cs
public async void button1_Click(object sender, EventArgs e)
{
    textBox1.Text = await Task.Run(() =>
    {
        // … do compute-bound work here
        return answer;
    });
}
```

to use await inside:

```cs
public async void button1_Click(object sender, EventArgs e)
{
    pictureBox1.Image = await Task.Run(async() =>
    {
        using(Bitmap bmp1 = await DownloadFirstImageAsync())
        using(Bitmap bmp2 = await DownloadSecondImageAsync())
        return Mashup(bmp1, bmp2);
    });
}
```

## FromResult

Is a way to create a completed task with a specific result.

```cs
public Task<int> GetValueAsync(string key)
{
    int cachedValue;
    return TryGetCachedValue(out cachedValue) ?
        Task.FromResult(cachedValue) :
        GetValueAsyncInternal();
}

private async Task<int> GetValueAsyncInternal(string key)
{
    …
}
```

## WhenAll/WhenAny

```cs
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
await Task.WhenAll(asyncOps);
```

For exepction handling:
```cs
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    ...
}
```
In this case, if any asynchronous operation fails, all the exceptions will be consolidated in an [AggregateException](https://learn.microsoft.com/en-us/dotnet/api/system.aggregateexception) exception, which is stored in the [Task](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.task) that is returned from the [WhenAll](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.task.whenall) method. However, only one of those exceptions is propagated by the `await` keyword. If you want to examine all the exceptions, you can rewrite the previous code as follows:


```cs
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

## Delay

## Configure.Await

Everything after await keyword is a continuation task continuing in the original thread if argument is true. In UI we can't update UI element from different thread an the exception will be thrown. In libraries you want to use false to automate optimizations and avoid deadlocks when using Task.Wait because it will block the thread.

```cs
public async Task LoadDataAsync()
{
    // Simulate an asynchronous operation
    var data = await GetDataFromServerAsync().ConfigureAwait(true);

    // Update UI (ensure this runs on the UI thread)
    UpdateUI(data);
}

private async Task<string> GetDataFromServerAsync()
{
    // Simulate a network call
    await Task.Delay(1000);
    return "Data from server";
}

private void UpdateUI(string data)
{
    // Code to update UI elements
}
```

## Task.Wait

`Task.Wait` is a blocking call. When you call `Wait` on a `Task`, it blocks the calling thread until the task has completed. This means that the thread that calls `Wait` cannot do anything else until the task finishes.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
