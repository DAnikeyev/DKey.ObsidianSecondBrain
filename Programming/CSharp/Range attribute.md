---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 The **RangeAttribute** is used to specify a range of values to be provided for an individual parameter of a parameterized test method.
RangeAttribute supports the following constructors:

```csharp
public RangeAttribute(int from, int to);
public RangeAttribute(int from, int to, int step);
public RangeAttribute(long from, long to, long step);
public RangeAttribute(float from, float to, float step);
public RangeAttribute(double from, double to, double step);
```

## Example

The following test will be executed nine times.

```csharp
[Test]
public void MyTest(
    [Values(1, 2, 3)] int x,
    [Range(0.2, 0.6, 0.2)] double d)
{
    /* ... */
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
