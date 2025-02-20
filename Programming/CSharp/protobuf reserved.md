---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [proto file](proto%20file.md)
___
Reserved statements declare a range of field numbers or field names that cannot be used in this message.

If you [update](https://protobuf.dev/programming-guides/proto3/#updating) an enum type by entirely removing an enum entry, or commenting it out, future users can reuse the numeric value when making their own updates to the type. This can cause severe issues if they later load old instances of the same `.proto`, including data corruption, privacy bugs, and so on. One way to make sure this doesn’t happen is to specify that the numeric values (and/or names, which can also cause issues for JSON serialization) of your deleted entries are `reserved`. The protocol buffer compiler will complain if any future users try to use these identifiers. You can specify that your reserved numeric value range goes up to the maximum possible value using the `max` keyword.

Examples:
```protobuf
reserved 2, 15, 9 to 11;
reserved "foo", "bar";

enum Foo {
  reserved 2, 15, 9 to 11, 40 to max;
  reserved "FOO", "BAR";
}```

>[!Info]
> you can’t mix field names and numeric values in the same `reserved` statement
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
