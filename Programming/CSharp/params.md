---
date_added: 2025-03-01
tags:
  - csharp
---
Up: [[Method]]
___
  ```csharp
 public void AnyNumberOfArguments(params int[] data)
{
	foreach (var x in data)
	{
		Console.WriteLine(x);
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
