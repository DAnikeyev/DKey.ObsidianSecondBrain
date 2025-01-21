---
date_added: 2025-01-21
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___
 You use lambda expressions to create anonymous function.
 Expressions lambda that has an expression as its body:
 ```csharp
 (input-parameters) => expression
 ```
 Statements lambda that has a statement block as its body:
 ```csharp
 (input-parameters) => { statement; }
 ```
Any lambda expression can be converted to a [Delegate](Delegate.md) type.
>[!Info]
> Values van be discarded by using the underscore character (_).

## Async lambda:

```cs
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
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
