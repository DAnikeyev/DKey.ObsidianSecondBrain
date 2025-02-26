---
date_added: 2025-02-26
tags:
  - web
---
Up: [Network](Network.md)
___
The Open Systems Interconnection (OSI) model is a reference model from the International Organization for Standardization (ISO) that "provides a common basis for the coordination of standards development for the purpose of systems interconnection."

| OSI Model Layer | Layer Number | Protocol Data Unit (PDU) | Function                                                                                                                                          |
| --------------- | ------------ | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Application     | 7            | Data                     | High-level protocols such as for resource sharing or remote file access, e.g., HTTP.                                                              |
| Presentation    | 6            | Data                     | Translation of data between a networking service and an application; including character encoding, data compression, and encryption/decryption.   |
| Session         | 5            | Data                     | Managing communication sessions, i.e., continuous exchange of information in the form of multiple back-and-forth transmissions between two nodes. |
| Transport       | 4            | Segment, Datagram        | Reliable transmission of data segments between points on a network, including segmentation, acknowledgement, and multiplexing.                    |
| Network         | 3            | Packet                   | Structuring and managing a multi-node network, including addressing, routing, and traffic control.                                                |
| Data Link       | 2            | Frame                    | Transmission of data frames between two nodes connected by a physical layer.                                                                      |
| Physical        | 1            | Bit, Symbol              | Transmission and reception of raw bit streams over a physical medium.                                                                             |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
