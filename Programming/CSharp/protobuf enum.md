---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [protobuf types](protobuf%20types.md)
___
 When you’re defining a message type, you might want one of its fields to only have one of a predefined list of values. Enumerator constants must be in the range of a 32-bit integer.
>[!Info]
> In proto3, the first value defined in an enum definition **must** have the value zero and should have the name `ENUM_TYPE_NAME_UNSPECIFIED` or `ENUM_TYPE_NAME_UNKNOWN`. This is because:
> - There must be a zero value, so that we can use 0 as a numeric [default value](https://protobuf.dev/programming-guides/proto3/#default).
> - The zero value needs to be the first element, for compatibility with the [proto2](https://protobuf.dev/programming-guides/proto2) semantics where the first enum value is the default unless a different value is explicitly specified.

### Enum Value Aliases

You can define aliases by assigning the same value to different enum constants. To do this you need to set the `allow_alias` [[protobuf option]] to `true`.

```protobuf
enum Corpus {
  CORPUS_UNSPECIFIED = 0;
  CORPUS_UNIVERSAL = 1;
  CORPUS_WEB = 2;
  CORPUS_IMAGES = 3;
  CORPUS_LOCAL = 4;
  CORPUS_NEWS = 5;
  CORPUS_PRODUCTS = 6;
  CORPUS_VIDEO = 7;
}

message SearchRequest {
  string query = 1;
  int32 page_number = 2;
  int32 results_per_page = 3;
  Corpus corpus = 4;
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
