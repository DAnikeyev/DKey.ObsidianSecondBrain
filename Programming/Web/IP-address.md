---
date_added: 2025-02-26
tags:
  - web
---
Up: [[Internet Protocol]]
___
 Internet Protocol address is a unique number assigned to a computer that is connected to the internet. It is used to identify the computer and communicate with other devices. It is a numerical lable such as 192.0.2.1 for [[IPv4]] and 2001:0db8:85a3:0000:0000:8a2e:0370:7334 for [[IPv6]].

## Localhost
127.0.0.1 is the IP address of the local computer. It is used to test network connections and troubleshoot problems. It is also known as the loopback address.

## Local adresses

192.168.*.* is a private IP address that is used for local networks. It is not routable on the internet and is used for internal communication between devices on the same network. 

## Masks and subnet

The subnet mask is used to divide the IP address into two parts: the network address and the host address. The network address is used to identify the network, while the host address is used to identify the individual device on the network. t can be used to define if a computer is in a [LAN](LAN.md) and to route the data depending on that. 

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
