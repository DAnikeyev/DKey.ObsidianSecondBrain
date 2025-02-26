---
date_added: 2025-02-26
tags:
  - web
---
Up: [Network](Network.md)
___
**port number** is a number assigned to uniquely identify a connection endpoint and to direct data to a specific service.
At the software level, within an operating system, a port is a logical construct that identifies a specific process or a type of network service. A port is associated with an [IP-address](IP-address.md) of the host, as well as the type of protocol used for communication.

### Example Scenario:

- **Application A:** Uses TCP on port 8080.
- **Application B:** Uses UDP on port 8080.

In this scenario, both applications can run simultaneously on the same machine without conflict because they are using different protocols. The operating system's networking stack will route incoming traffic to the correct application based on the protocol specified in the incoming packets.


## Common Port Numbers:

- **HTTP:** Port 80
- **HTTPS:** Port 443
- **SSH:** Port 22
- **FTP:** Port 21
- **SMTP:** Port 25
- **DNS:** Port 53

0-1024 are well-known ports, 1025-49151 are registered ports, and 49152-65535 are dynamic or private ports.

For example, 135-139 are used by Windows file sharing, 445 is used by Microsoft-DS, 1433 is used by Microsoft SQL Server, and 3306 is used by MySQL.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
