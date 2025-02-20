---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [proto file](proto%20file.md)
___
 You can add an optional `package` specifier to a `.proto` file to prevent name clashes between protocol message types.

```protobuf
package foo.bar;
message Open { ... }
```

You can then use the package specifier when defining fields of your message type:

```protobuf
message Foo {
  ...
  foo.bar.Open open = 1;
  ...
}
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
