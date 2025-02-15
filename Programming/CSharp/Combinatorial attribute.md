---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 The **CombinatorialAttribute** is used on a test to specify that NUnit should generate test cases for all possible combinations of the individual data items provided for the parameters of a test.

The following test will be executed six times:

```csharp
[Test, Combinatorial]
public void MyTest(
    [Values(1, 2, 3)] int x,
    [Values("A", "B")] string s)
{
    ...
}
```

MyTest is called six times, as follows:

```csharp
MyTest(1, "A")
MyTest(1, "B")
MyTest(2, "A")
MyTest(2, "B")
MyTest(3, "A")
MyTest(3, "B")
```

this is also a default behaviour without that tag, that could be overriden. 
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
