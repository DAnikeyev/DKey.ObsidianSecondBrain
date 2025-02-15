---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 The **SequentialAttribute** is used on a test to specify that NUnit should generate test cases by selecting individual data items provided for the parameters of the test, without generating additional combinations.
## Example

The following test will be executed three times.

```csharp
[Test, Sequential]
public void MyTest(
    [Values(1, 2, 3)] int x,
    [Values("A", "B")] string s)
{
    /* ... */
}
```

MyTest is called three times, as follows:

```csharp
MyTest(1, "A")
MyTest(2, "B")
MyTest(3, null)
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
