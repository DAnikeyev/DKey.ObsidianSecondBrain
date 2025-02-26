---
date_added: 2025-02-26
tags:
  - web
---
Up: [Protocol](Protocol.md)
___
 **WebSocket** is a computer [communications protocol](https://en.wikipedia.org/wiki/Communications_protocol "Communications protocol"), providing a [simultaneous two-way](https://en.wikipedia.org/wiki/Full-duplex "Full-duplex") communication channel over a single [TCP(-IP)](TCP(-IP).md) connection.

### Key features of WebSockets

1. **Full-Duplex Communication**: Both the client and server can send messages independently of each other, allowing for more interactive and dynamic web applications.
    
2. **Persistent Connection**: Once established, the WebSocket connection remains open, reducing the overhead of establishing new connections for each message exchange.
    
3. **Low Latency**: Because the connection is persistent, WebSockets can provide lower latency communication compared to traditional HTTP requests, which require a new connection for each request/response cycle.
    
4. **Efficiency**: WebSockets use a lightweight frame format, which reduces the amount of data overhead compared to HTTP headers.


### Ping/Pong Mechanism

To maintain the connection and ensure that both the client and server are still reachable, WebSockets often use a "ping/pong" mechanism:

- **Ping**: Either the client or server can send a "ping" frame to the other party.
- **Pong**: The recipient of a ping frame should respond with a "pong" frame.

This mechanism helps detect if the connection is still alive and can also be used to measure latency. The frequency of these ping/pong messages can be configured based on the application's needs.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
