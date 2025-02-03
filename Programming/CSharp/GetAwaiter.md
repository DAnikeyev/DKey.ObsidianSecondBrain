---
date_added: 2025-02-03
tags:
  - csharp
---
Up: [[await]]
___
 GetAwaiter Method lets you to await object as a Task. Also you can define method as an [Extension method](Extension%20method.md) to use it with any object. You can even do something like `await 2.Seconds();`
 or `await 2;`

```cs
public class Delay()
{
	private TimeSpan _delayTime = TimeSpan.FromSeconds(2);
	
	public TaskAwaiter GetAwaiter()
    {
        return Task.Delay(_delayTime).GetAwaiter();
    }
}

public void Main()
{
    await new Delay();
}
```

```


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
