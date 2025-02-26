---
date_added: 2025-02-26
tags:
  - web
---
Up: [[HTTP]]
___
## HTTP1

A lot of data needs to be transfered for every resouorce transfer. That was improved in HTTP 1.1
![](Pasted%20image%2020250226081738.png)
## HTTP1.1

Introduced persistant connections
Also pipelines  (send request before getting previous response) and chunk loading
![](Pasted%20image%2020250226081859.png)
## HTTP2
Binary framing layer: Messages are divided into smaller unit (frames) that work better with streams and [TCP(-IP)](TCP(-IP).md) connection.

Full request and response [Http Multiplexing](Http%20Multiplexing.md). That fixed Head-Of-Line blocking problem when preparation of first response blocks responding next ones.

Stream Prioritization allows devs to configure order of [Web Page](Web%20Page.md) loading

Server Push allows multiple responces in a sequence to start processing data before getting everything wtihout waiting for another request. 

HPack is a compression, that makes headers smaller especially for repeated communication

![](Pasted%20image%2020250226082259.png)

## HTTP3
Uses [QUIC](QUIC.md) instead of [TCP(-IP)](TCP(-IP).md).

Reduces latency and handle packet loss better.

Uses QUIC connection ID to handle switching between networks (Wifi to 4G for example)

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
