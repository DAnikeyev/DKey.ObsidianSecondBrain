---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 The **TimeoutAttribute** is used to specify a timeout value in milliseconds for a test case. If the test case runs longer than the time specified it is immediately cancelled and reported as a failure, with a message indicating that the timeout was exceeded. **MaxTimeAttribute** do the same but test does not stop to run, it just reports that time was exceeded.

 
>[!Info]
> When debugging a unit test, i.e. when a debugger is attached to the process, then the timeout is not enforced.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
