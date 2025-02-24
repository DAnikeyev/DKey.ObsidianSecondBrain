---
date_added: 2025-02-24
tags:
  - web
---
Up: [gRPC](gRPC.md)
___
```protobuf
rpc Unary(RequestType) returns (ResponseType);
rpc ServerStreaming(RequestType) returns (stream ResponseType);
rpc ClientStreaming(stream RequestType) returns (ResponseType);
rpc Duplex(stream RequestType) returns (stream ResponseType);
  // nomenclature: duplex === bidirectional streaming
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
