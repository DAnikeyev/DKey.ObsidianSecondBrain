---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [proto file](proto%20file.md)
___
Has a name and a sequence of fields with type, name and a field number.
 
 ```proto
message SearchRequest {
  string query = 1;
  int32 page_number = 2;
  int32 results_per_page = 3;
}
```
### Assigning Field Numbers

You must give each field in your message definition a number between `1` and `536,870,911` with the following restrictions:

- The given number **must be unique** among all fields for that message.
- Field numbers `19,000` to `19,999` are reserved for the Protocol Buffers implementation. The protocol buffer compiler will complain if you use one of these reserved field numbers in your message.
- You cannot use any previously [reserved](https://protobuf.dev/programming-guides/proto3/#fieldreserved) field numbers or any field numbers that have been allocated to [extensions](https://protobuf.dev/programming-guides/proto2#extensions).
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
