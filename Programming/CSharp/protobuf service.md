---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [proto file](proto%20file.md)
___
 If you want to use your message types with an RPC you can define an RPC service interface in a `.proto` file and the protocol buffer compiler will generate service interface code and stubs in your chosen language.
 
```protobuf
service SearchService {
  rpc Search(SearchRequest) returns (SearchResponse);
}
```

## Stream
is used for [gRPC](gRPC.md) to send and receive a stream of messages. 
```ProtoBuf
service Service{
rpc updload(stream Data) returns (google.protobuf.Empty);
rpc download(google.protobuf.Empty) returns (stream Data); 
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
