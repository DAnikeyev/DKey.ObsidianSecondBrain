---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 is a [Test runner](Test%20runner.md) for running tests in all contexts (for example, continuous integration (CI) pipelines, CLI, Visual Studio Test Explorer, and VS Code Text Explorer). The NUnit runner is embedded directly in your NUnit test projects, and there are no other app dependencies, such as `vstest.console` or `dotnet test`, needed to run your tests.

## Configurations and filters

### .runsettings

The NUnit runner supports the [runsettings](https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-platform-extensions-vstest-bridge#runsettings-support) through the command-line option `--settings`. The following commands show examples.

Using `dotnet run`:

.NET CLI

```
dotnet run --project Contoso.MyTests -- --settings config.runsettings
```

Using `dotnet exec`:

.NET CLI

```
dotnet exec Contoso.MyTests.dll --settings config.runsettings
```

-or-

.NET CLI

```
dotnet Contoso.MyTests.dll --settings config.runsettings
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
