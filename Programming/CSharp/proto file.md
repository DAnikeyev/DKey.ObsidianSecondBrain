---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [gRPC](gRPC.md), [Protobuf](Protobuf.md)
___
 file that specifiies contracts to use. Grpc.Tools library is used to generate code from this file. 
 
```protobuf
 syntax = "proto3";

package usermanagement;

// The user message definition
message User {
  int32 id = 1;
  string name = 2;
  string email = 3;
}

// The request message containing the user's ID
message GetUserRequest {
  int32 id = 1;
}

// The response message containing the user details
message GetUserResponse {
  User user = 1;
}

// The request message for creating a new user
message CreateUserRequest {
  string name = 1;
  string email = 2;
}

// The response message for creating a new user
message CreateUserResponse {
  User user = 1;
}

// The user management service definition
service UserManagement {
  // RPC to create a new user
  rpc CreateUser(CreateUserRequest) returns (CreateUserResponse);

  // RPC to get a user by ID
  rpc GetUser(GetUserRequest) returns (GetUserResponse);
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
