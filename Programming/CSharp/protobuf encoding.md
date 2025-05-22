---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [Protobuf](Protobuf.md)
___
 The protocol buffer _wire format_, which defines the details of how your message is sent on the wire and how much space it consumes on disk.
## A Simple Message

Let’s say you have the following very simple message definition:

```protobuf
message Test1 {
  optional int32 a = 1;
}
```

In an application, you create a `Test1` message and set `a` to 150. You then serialize the message to an output stream. If you were able to examine the encoded message, you’d see three bytes:

```protobuf
08 96 01
```

So far, so small and numeric – but what does it mean? If you use the Protoscope tool to dump those bytes, you’d get something like `1: 150`. How does it know this is the contents of the message?

## Base 128 Varints

Variable-width integers, or _varints_, are at the core of the wire format. They allow encoding unsigned 64-bit integers using anywhere between one and ten bytes, with small values using fewer bytes.

Each byte in the varint has a _continuation bit_ that indicates if the byte that follows it is part of the varint. This is the _most significant bit_ (MSB) of the byte (sometimes also called the _sign bit_). The lower 7 bits are a payload; the resulting integer is built by appending together the 7-bit payloads of its constituent bytes.

So, for example, here is the number 1, encoded as `` `01` `` – it’s a single byte, so the MSB is not set:

```protobuf
0000 0001
^ msb
```

And here is 150, encoded as `` `9601` `` – this is a bit more complicated:

```protobuf
10010110 00000001
^ msb    ^ msb
```

How do you figure out that this is 150? First you drop the MSB from each byte, as this is just there to tell us whether we’ve reached the end of the number (as you can see, it’s set in the first byte as there is more than one byte in the varint). These 7-bit payloads are in little-endian order. Convert to big-endian order, concatenate, and interpret as an unsigned 64-bit integer:

```protobuf
10010110 00000001        // Original inputs.
 0010110  0000001        // Drop continuation bits.
 0000001  0010110        // Convert to big-endian.
   00000010010110        // Concatenate.
 128 + 16 + 4 + 2 = 150  // Interpret as an unsigned 64-bit integer.
```

Because varints are so crucial to protocol buffers, in protoscope syntax, we refer to them as plain integers. `150` is the same as `` `9601` ``.

## Message Structure

A protocol buffer message is a series of key-value pairs. The binary version of a message just uses the field’s number as the key – the name and declared type for each field can only be determined on the decoding end by referencing the message type’s definition (i.e. the `.proto` file)
When a message is encoded, each key-value pair is turned into a _record_ consisting of the field number, a wire type and a payload. The wire type tells the parser how big the payload after it is.

| ID  | Name   | Used For                                                 |
| --- | ------ | -------------------------------------------------------- |
| 0   | VARINT | int32, int64, uint32, uint64, sint32, sint64, bool, enum |
| 1   | I64    | fixed64, sfixed64, double                                |
| 2   | LEN    | string, bytes, embedded messages, packed repeated fields |
| 3   | SGROUP | group start (deprecated)                                 |
| 4   | EGROUP | group end (deprecated)                                   |
| 5   | I32    | fixed32, sfixed32, float                                 |

# Var length

_Length prefixes_ are another major concept in the wire format. The `LEN` wire type has a dynamic length, specified by a varint immediately after the tag, which is followed by the payload as usual.

Consider this message schema:

```protobuf
message Test2 {
  optional string b = 2;
}
```

A record for the field `b` is a string, and strings are `LEN`-encoded. If we set `b` to `"testing"`, we encoded as a `LEN` record with field number 2 containing the ASCII string `"testing"`. The result is `` `120774657374696e67` ``. Breaking up the bytes,

```protobuf
12 07 [74 65 73 74 69 6e 67]
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
