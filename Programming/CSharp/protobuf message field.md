---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [protobuf message](protobuf%20message.md)
___
 Message fields can be one of the following:

- _Singular_ (can also be `optional` or `implicit`(not recommended, will have default value even if not set for non-message types))
- repeated
- map <key, value>
## Singular
Can be any type, [[protobuf enum]] [[protobuf scalar]] or [protobuf message](protobuf%20message.md)

## Repeated
Repeated Fields are Packed by Default
In proto3, `repeated` fields of scalar numeric types use `packed` encoding by default.

## Map

```protobuf
map<string, int32> my_map = 1;

// Is equivalent to:

message MyMapEntry {
  string key = 1;
  int32 value = 2;
}

message MyMap {
  repeated MyMapEntry entries = 1;
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
