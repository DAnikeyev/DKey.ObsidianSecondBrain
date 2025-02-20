---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [protobuf types](protobuf%20types.md)
___
packing and unpacking of unknown types is handled by respective Protobuf library methods, like Any.Unpack<\T>() in C#
## Any

```protobuf
import "google/protobuf/any.proto";

message ErrorStatus {
  string message = 1;
  repeated google.protobuf.Any details = 2;
}

```

 ```csharp
 using Google.Protobuf.WellKnownTypes;

// Assume you have a message type called MyMessage
MyMessage myMessage = new MyMessage { /* set fields */ };

// Pack the message into an Any
Any any = Any.Pack(myMessage);

// Attempt to unpack the message
if (any.TryUnpack(out MyMessage unpackedMessage))
{
    // Successfully unpacked, use unpackedMessage
    Console.WriteLine("Unpacking successful!");
}
else
{
    // Unpacking failed, handle the error
    Console.WriteLine("Unpacking failed.");
}
 ```
## One of
```protobuf
message SampleMessage {
  oneof test_oneof {
    string name = 4;
    SubMessage sub_message = 9;
  }
}
```

 ```csharp
 SampleMessage message = new SampleMessage();
message.Name = "Example"; // Sets the 'name' field
Console.WriteLine(message.TestOneofCase); // Outputs: Name

message.Id = 123; // Sets the 'id' field, unsetting 'name'
Console.WriteLine(message.TestOneofCase); // Outputs: Id
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
