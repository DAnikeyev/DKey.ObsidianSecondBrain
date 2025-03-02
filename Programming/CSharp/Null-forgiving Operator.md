---
date_added: 2025-01-22
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___
For [[Nullable Reference Type]] `!`  is used to suppress the warning that the value can be null. This is useful when you are sure that the value is not null.

```cs
[TestMethod, ExpectedException(typeof(ArgumentNullException))]
public void NullNameShouldThrowTest()
{
    var person = new Person(null!);
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
