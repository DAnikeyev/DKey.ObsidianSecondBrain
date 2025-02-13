---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 .NET test driver used to execute unit tests.
 ```cs
 dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL> | <EXE>]
    [--test-adapter-path <ADAPTER_PATH>]
    [-a|--arch <ARCHITECTURE>]
    [--artifacts-path <ARTIFACTS_DIR>]
    [--blame]
    [--blame-crash]
    [--blame-crash-dump-type <DUMP_TYPE>]
    [--blame-crash-collect-always]
    [--blame-hang]
    [--blame-hang-dump-type <DUMP_TYPE>]
    [--blame-hang-timeout <TIMESPAN>]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_NAME>]
    [-d|--diag <LOG_FILE>]
    [-f|--framework <FRAMEWORK>]
    [-e|--environment <NAME="VALUE">]
    [--filter <EXPRESSION>]
    [--interactive]
    [-l|--logger <LOGGER>]
    [--no-build]
    [--nologo]
    [--no-restore]
    [-o|--output <OUTPUT_DIRECTORY>]
    [--os <OS>]
    [--results-directory <RESULTS_DIR>]
    [-r|--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>]
    [-t|--list-tests]
    [-v|--verbosity <LEVEL>]
    [<args>...]
    [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## Filter option details

`--filter <EXPRESSION>`

`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.

`<property>` is an attribute of the `Test Case`. The following are the properties supported by popular unit test frameworks:

|Test Framework|Supported properties|
|---|---|
|MSTest|- FullyQualifiedName<br>- Name<br>- ClassName<br>- Priority<br>- TestCategory|
|xUnit|- FullyQualifiedName<br>- DisplayName<br>- Category|
|NUnit|- FullyQualifiedName<br>- Name<br>- Category<br>- Priority|

The `<operator>` describes the relationship between the property and the value:

|Operator|Function|
|---|---|
|`=`|Exact match|
|`!=`|Not exact match|
|`~`|Contains|
|`!~`|Not contains|

`<value>` is a string. All the lookups are case insensitive.


```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
