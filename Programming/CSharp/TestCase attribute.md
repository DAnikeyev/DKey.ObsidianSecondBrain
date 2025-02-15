---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 ```csharp
[TestCase(12, 3, 4)]
[TestCase(12, 2, 6)]
[TestCase(12, 4, 3)]
public void DivideTest(int n, int d, int q)
{
    Assert.That(n / d, Is.EqualTo(q));
}
```

**TestCaseAttribute** may appear one or more times on a test method, which may also carry other attributes providing test data. The method may optionally be marked with the [Test Attribute](https://docs.nunit.org/articles/nunit/writing-tests/attributes/test.html) as well.

By using the named parameter `ExpectedResult` this test set may be simplified further:

```csharp
[TestCase(12, 3, ExpectedResult = 4)]
[TestCase(12, 2, ExpectedResult = 6)]
[TestCase(12, 4, ExpectedResult = 3)]
public int DivideTest(int n, int d)
{
    return n / d;
}
```

TestCaseAttribute supports a number of additional named parameters:

- **Author** sets the author of the test.
- **Category** provides a comma-delimited list of categories for this test.
- **Description** sets the description property of the test.
- **ExcludePlatform** specifies a comma-delimited list of platforms on which the test should not run.
- **ExpectedResult** sets the expected result to be returned from the method, which must have a compatible return type.
- **Explicit** is set to true in order to make the individual test case Explicit. Use **Reason** to explain why.
- **Ignore** causes the test case to be ignored and specifies the reason.
- **IgnoreReason** causes this test case to be ignored and specifies the reason.
- **IncludePlatform** specifies a comma-delimited list of platforms on which the test should run.
- **Reason** specifies the reason for not running this test case. Use in conjunction with **Explicit**.
- **TestName** provides a name for the test. If not specified, a name is generated based on the method name and the arguments provided. See [Template Based Test Naming](https://docs.nunit.org/articles/nunit/running-tests/Template-Based-Test-Naming.html).
- **TestOf** specifies the Type that this test is testing (this is not used within NUnit during test execution, but may serve a purpose for the test author)
- **TypeArgs** specifies the `Type`s to be used when targeting a generic test method. (_NUnit 4.1+_)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
