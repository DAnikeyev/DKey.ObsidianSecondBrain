---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___

The Category attribute provides an alternative to suites for dealing with groups of tests.
Some runners, including the Console Runner, allow specifying categories to be included in or excluded from the run.
 ```csharp

  [Category("LongRunning")]
```

## Custom category attribute

Here's an example that creates a category of Critical tests. It works just like any other category, but has a simpler syntax. A test reporting system might make use of the attribute to provide special reports.

```csharp
[AttributeUsage(AttributeTargets.Method, AllowMultiple=false)]
public class CriticalAttribute : CategoryAttribute
{ }
```

```csharp
[Test, Critical]
public void MyTest()
{ /*...*/ }
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
