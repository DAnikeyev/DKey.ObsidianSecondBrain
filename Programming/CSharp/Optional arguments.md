---
date_added: 2025-03-01
tags:
  - csharp
---
Up: [Method](Method.md)
___
 Parameters can also be optional. You must supply a default value for optional parameters, which must be
the last ones defined:
 ```csharp
 public void TestMethod(int notOptionalNumber, int optionalNumber = 42)
{
Console.WriteLine(optionalNumber + notOptionalNumber);
}
 ```

>[!Warning]
> Changing default value is dangerous, because the consumer might not know about that change

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
