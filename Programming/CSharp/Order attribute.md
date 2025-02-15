---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 The **OrderAttribute** may be placed on a test method or fixture to specify the order in which tests are run within the fixture or other suite in which they are contained.
 
Tests with an `OrderAttribute` argument are started before any tests without the attribute.

```csharp
public class MyFixture
{
    [Test, Order(1)]
    public void TestA() { /* ... */ }


    [Test, Order(2)]
    public void TestB() { /* ... */ }

    [Test]
    public void TestC() { /* ... */ }
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
