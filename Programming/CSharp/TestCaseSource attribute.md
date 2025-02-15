---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [[NUnit]]
___

Is a way to feed the sequence of test cases to a test method. The method that provides the test cases must be public, static, and return an IEnumerable. The test method is then marked with the TestCaseSource attribute, specifying the class and method that provides the data.

 ```csharp
[TestFixture]
public class MyTests
{
    [TestCaseSource(typeof(MyDataClass), nameof(MyDataClass.TestCases))]
    public int DivideTest(int n, int d)
    {
        return n / d;
    }
}

public class MyDataClass
{
    public static IEnumerable TestCases
    {
        get
        {
            yield return new TestCaseData(12, 3).Returns(4);
            yield return new TestCaseData(12, 2).Returns(6);
            yield return new TestCaseData(12, 4).Returns(3);
        }
    }
}
```

## Sources for generic methods using TestCaseData

As of NUnit 4.1, it is possible to explicitly specify the generic types to be used for a generic method. This may be useful when any of the test case arguments differ from the desired generic types. When omitted, NUnit will infer the generic type arguments based on the passed values from the `TestCaseSource`.

```csharp
[TestFixture]
public class MyExplicitlyTypedTests
{
    [TestCaseSource(nameof(ExplicitTypeArgsTestCases))]
    public void ExplicitTypeArgs<T>(T input)
    {
        Assert.That(typeof(T), Is.EqualTo(typeof(long)));
    }

    private static IEnumerable<TestCaseData> ExplicitTypeArgsTestCases()
    {
        yield return new TestCaseData(2) { TypeArgs = new[] { typeof(long) } };
        yield return new TestCaseData(2L) { TypeArgs = new[] { typeof(long) } };
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
