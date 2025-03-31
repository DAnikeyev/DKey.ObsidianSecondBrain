---
date_added: 2025-03-24
tags:
  - csharp
---
Up: [[async]]
___
1. **Event Handler Signature**: [EventHandler](EventHandler.md) in C# have a specific signature that returns `void`. Since you cannot change the return type of an event handler to `Task` or `Task<T>`, `async void` is used to allow asynchronous operations within the handler.
    
2. **Non-blocking UI**: In GUI applications, such as those using Windows Forms or WPF, event handlers often need to perform asynchronous operations (e.g., fetching data from a server) without blocking the UI thread. Using `async void` allows the event handler to perform these operations asynchronously.
 
 ```cs
 private async void Button_Click(object sender, EventArgs e)
{
    try
    {
        // Simulate an asynchronous operation
        await Task.Delay(1000);
        MessageBox.Show("Operation completed");
    }
    catch (Exception ex)
    {
        // Handle exceptions
        MessageBox.Show($"An error occurred: {ex.Message}");
    }
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
