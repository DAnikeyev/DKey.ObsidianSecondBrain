---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [Testing in dotnet](Testing%20in%20dotnet.md)
___

| Feature/Framework           | xUnit                                                 | NUnit                                        | MSTest                                                |
| --------------------------- | ----------------------------------------------------- | -------------------------------------------- | ----------------------------------------------------- |
| **Overview**                | Modern, community-focused unit testing tool for .NET. | Traditional unit testing framework for .NET. | Microsoft's official unit testing framework for .NET. |
| **Test Method Attribute**   | `[Fact]`, `[Theory]`                                  | `[Test]`, `[TestCase]`                       | `[TestMethod]`                                        |
| **Setup/Teardown**          | Constructor/`Dispose`                                 | `[SetUp]`, `[TearDown]`                      | `[TestInitialize]`, `[TestCleanup]`                   |
| **Parameterized Tests**     | `[Theory]`, `InlineData`                              | `[TestCase]`                                 | `[DataTestMethod]`, `[DataRow]`                       |
| **Parallel Test Execution** | Yes                                                   | With configuration                           | Yes                                                   |
| **Assertions**              | Rich set of assertions                                | Rich set of assertions                       | Rich set of assertions                                |
| **Extensibility**           | High                                                  | High                                         | Moderate                                              |
| **Test Discovery**          | Convention-based                                      | Attribute-based                              | Attribute-based                                       |
| **Test Fixtures**           | Class/Collection fixtures                             | `[TestFixture]`                              | `[TestClass]`                                         |
| **IDE Integration**         | Excellent                                             | Excellent                                    | Excellent                                             |
| **Mocking Support**         | Via third-party libraries                             | Via third-party libraries                    | Via third-party libraries                             |
| **Documentation**           | Good                                                  | Good                                         | Good                                                  |
| **Community and Ecosystem** | Strong                                                | Strong                                       | Strong                                                |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
