---
date_added: 2025-02-03
tags:
  - web
---
up: [[Protocol]]
___
 is a language agnostic, high-performance Remote Procedure Call (RPC) framework. (google protocol)
 Here are some key features of gRPC:

1. **Protocol Buffers**: gRPC uses [Protobuf](Protobuf.md) (protobufs) as its interface definition language. Protobufs are a language-agnostic, binary serialization format that is both efficient and easy to use. They define the structure of the data and the service methods.
    
2. **HTTP/2**: gRPC leverages HTTP/2 as its transport protocol, which provides several benefits such as multiplexing multiple requests over a single connection, flow control, header compression, and bidirectional streaming.
    
3. **Cross-Platform**: gRPC supports multiple programming languages, including but not limited to C++, Java, Python, Go, Ruby, and C#. This makes it suitable for heterogeneous environments where different services might be implemented in different languages.
    
4. **Streaming**: gRPC supports different types of streaming: unary (single request and response), server streaming (single request and multiple responses), client streaming (multiple requests and single response), and bidirectional streaming (multiple requests and responses).
    
5. **Performance**: Due to its use of HTTP/2 and Protocol Buffers, gRPC is designed to be highly performant, with low latency and high throughput.
    
6. **Authentication and Security**: gRPC provides built-in support for authentication and security, including integration with SSL/TLS for secure communication.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
