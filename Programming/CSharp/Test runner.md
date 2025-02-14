---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [Testing in dotnet](Testing%20in%20dotnet.md)
___
 A test runner is responsible for discovering, executing, and reporting the results of tests.
### 1. Test Discovery

- **Function**: Identify and locate test methods within the codebase.
- **How**: Uses attributes (e.g., `[Test]`, `[TestMethod]`, `[Fact]`) to find methods designated as tests.
- **NUnit Example**: Discovers methods marked with `[Test]` or `[TestCase]`.

### 2. Test Execution

- **Function**: Run the discovered tests.
- **How**: Executes each test method, capturing the results (pass, fail, skip).
- **NUnit Example**: Executes methods marked with `[Test]` and manages parameterized tests with `[TestCase]`.

### 3. Result Reporting

- **Function**: Collect and present the results of the test execution.
- **How**: Aggregates test results and provides feedback in the form of reports, logs, or console output.
- **NUnit Example**: Outputs results to the console, IDE test explorer, or generates XML reports.

### 4. Setup and Teardown

- **Function**: Prepare the test environment before tests and clean up afterward.
- **How**: Executes setup methods before tests and teardown methods after tests.
- **NUnit Example**: Uses `[SetUp]` and `[TearDown]` for individual test methods, `[OneTimeSetUp]` and `[OneTimeTearDown]` for test fixtures.

### 5. Parallel Execution

- **Function**: Run tests concurrently to improve execution speed.
- **How**: Manages threads and processes to execute tests in parallel.
- **NUnit Example**: Supports parallel test execution with appropriate configuration.

### 6. Integration with Development Tools

- **Function**: Work seamlessly with IDEs, CI/CD pipelines, and other tools.
- **How**: Provides plugins/extensions for IDEs and integrates with CI tools like Azure DevOps, Jenkins, GitHub Actions.
- **NUnit Example**: NUnit has plugins for Visual Studio and can be used with `dotnet test` command for CI integration.

### 7. Handling Test Dependencies

- **Function**: Manage dependencies and ensure correct execution order.
- **How**: Uses attributes and configuration to manage test dependencies and order.
- **NUnit Example**: Tests within the same fixture can depend on setup methods to initialize shared state.
## Execution Control

### Running Tests in [[IDE]]

- **Process**:
    1. The developer triggers test execution from the IDE (e.g., Visual Studio).
    2. The IDE uses its integrated test runner (e.g., Visual Studio Test Runner) to discover and run tests.
    3. Results are displayed in the Test Explorer window, showing which tests passed, failed, or were skipped.

### Running Tests with [command dotnet test](command%20dotnet%20test.md)

- **Process**:
    1. The developer runs `dotnet test` from the command line.
    2. The .NET CLI invokes the appropriate test runner for the project (e.g., NUnit, xUnit, MSTest).
    3. The test runner discovers and executes tests, then reports results to the console.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
