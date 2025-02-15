---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 The `Test` attribute is one way of marking a method inside a TestFixture class as a test.
 
 ```csharp
  [TestFixture]
  public class SuccessTests
  {
    // A simple test
    [Test]
    public void Add()
    { /* ... */ }

    // A test with a description property
    [Test(Description="My really cool test")]
    public void Add()
    { /* ... */ }

    // Alternate way to specify description as a separate attribute
    [Test, Description("My really really cool test")]
    public void Add()
    { /* ... */ }

    // A simple async test
    [Test]
    public async Task AddAsync()
    { /* ... */ }

    // Test with an expected result
    [Test(ExpectedResult = 4)]
    public int TestAdd()
    {
        return 2 + 2;
    }

    // Async test with an expected result
    [Test(ExpectedResult = 4)]
    public async Task<int> TestAdd()
    {
        await ...
        return 2 + 2;
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
