---
date_added: 2025-02-27
tags:
  - csharp
---
Up: [Event](Event.md)
___
 ```csharp
     // Declare the delegate (if using non-generic pattern).
    public delegate EventHandler SampleEventHandler(object sender, DataEventArgs e);
    
	public void TestEventParser((object sender, DataEventArgs e)
	{
		Console.WriteLine($"DataEventArgs: {e.Value}");
		// Unsuscribe the event
		SampleEvent -= TestEventParser;
	}
	
    // Declare the event.
    public event EventHandler SampleEvent;

	public void Init
	{
		SampleEvent += TestEventParser;
	}
    // Wrap the event in a protected virtual method
    // to enable derived classes to raise the event.
    protected virtual void RaiseSampleEvent()
    {
        // Raise the event in a thread-safe manner using the ?. operator.
        SampleEvent?.Invoke(this, new SampleEventArgs("Hello"));
    }
 ```

While both `EventHandler` and custom delegates can be used to define events, `EventHandler` is preferred for its simplicity, standardization, and alignment with .NET conventions.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
