---
date_added: 2025-03-25
tags:
  - csharp
---
Up: [TCP(-IP)](TCP(-IP).md)
___

The following are key control flags used in the TCP protocol, which underlies HTTP communication. These flags help manage the establishment, maintenance, and termination of connections, as well as the reliable transmission of data.

>[!Info]
> FIN signal is used as a Cancellation of [Http Request](Http%20Request.md) signalling, for example to [ASP.Net](ASP.Net.md) to cancel [Cancellation Token](Cancellation%20Token.md) if it exists in a method.

- **SYN (Synchronize):**  
  Used to initiate a TCP connection. The client sends a SYN packet to the server to request a connection.

- **ACK (Acknowledgment):**  
  Used to acknowledge the receipt of data. An ACK packet is sent by the receiver to confirm that it has received the data correctly.
 
- NACK (Negative Acknowledgment): This is a signal sent by the receiver to the sender indicating that the data has not been received correctly or has been corrupted. NACK is used to request the sender to retransmit the data.

- **FIN (Finish):**  
  Used to gracefully terminate a TCP connection. When a client or server wants to close the connection, it sends a FIN packet.

- **RST (Reset):**  
  Used to abruptly terminate a TCP connection. An RST packet is sent when there is an error or when the connection needs to be closed immediately.

- **PSH (Push):**  
  Used to push data to the receiving application immediately. The PSH flag in a TCP packet indicates that the data should be delivered to the application without waiting for more data.

- **URG (Urgent):**  
  Indicates that the data contained in the packet should be processed immediately. The URG flag in a TCP packet marks the data as urgent.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
