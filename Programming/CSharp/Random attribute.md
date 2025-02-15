---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 RandomAttribute supports the following constructors:

```csharp
public Random(int count);
public Random(int min, int max, int count);
public Random(uint min, uint max, int count);
public Random(long min, long max, int count);
public Random(ulong min, ulong max, int count);
public Random(short min, short max, int count);
public Random(ushort min, ushort max, int count);
public Random(byte min, byte max, int count);
public Random(sbyte min, sbyte max, int count);
public Random(double min, double max, int count);
public Random(float min, float max, int count);
```

The following test will be executed fifteen times, three times for each value of x, each combined with 5 random doubles from -1.0 to +1.0.

```csharp
[Test]
public void MyTest(
    [Values(1, 2, 3)] int x,
    [Random(-1.0, 1.0, 5)] double d)
{
    ...
}
```

>[!Info]
> Is not seeded
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
