---
date_added: 2024-10-08
tags:
  - dotnet
---
Up: [CLR](CLR.md)
___
The stack in C# (under the CLR) is a region of memory used for short-lived data such as method arguments, local variables, and return addresses for method calls. When a method is invoked, the CLR creates a new stack frame (or activation record) for that method call, storing its arguments and local variables on the stack; once the method returns, its stack frame is popped off, freeing that memory immediately.

Each [Thread](Thread.md) has it's own stack, which is created when the thread is started and destroyed when the thread is terminated. The size of the stack is fixed when the thread is created and can be set using the `Thread` constructor or the `Thread` class's `MaxStackSize` property.

 Value types (like int, float, struct) typically go on the stack (unless they are part of a larger object on the heap), whereas reference types (like classes) store their object data on the heap, while the reference itself resides on the stack.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
