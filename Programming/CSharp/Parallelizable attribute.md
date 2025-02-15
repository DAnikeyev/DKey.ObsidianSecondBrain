---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 The `ParallelizableAttribute` is used to indicate that a test and/or its descendants may be run in parallel with other tests. By default, no parallel execution takes place.

## ParallelScope Enumeration

This is a **[Flags]** enumeration used to specify which tests may run in parallel. It applies to the test upon which it appears and any subordinate tests. The following values are available to users:

| Value                    | Meaning                                                                           | Valid On          |
| ------------------------ | --------------------------------------------------------------------------------- | ----------------- |
| `ParallelScope.Self`     | the test itself may be run in parallel with other tests                           | Classes, Methods  |
| `ParallelScope.Children` | child tests may be run in parallel with one another                               | Assembly, Classes |
| `ParallelScope.Fixtures` | fixtures may be run in parallel with one another                                  | Assembly, Classes |
| `ParallelScope.All`      | the test and its descendants may be run in parallel with others at the same level | Classes, Methods  |
NonParallelizable Attribute prevents a test from running in parallel with other tests. It is used to override the ParallelizableAttribute at the test level.


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
