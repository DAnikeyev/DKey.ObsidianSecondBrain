---
date_added: 2025-02-26
tags:
  - web
---
Up: [Internet Protocol](Internet%20Protocol.md)
___

| Feature                           | IPv4                                                   | IPv6                                                                                              |
| --------------------------------- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| Address Length                    | 32-bit address length (approx. 4.3 billion addresses)  | 128-bit address length (approx. 340 undecillion addresses)                                        |
| Address Format                    | Decimal format, four octets (e.g., 192.168.1.1)        | Hexadecimal format, eight groups (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334)                  |
| Header Complexity                 | 20-60 bytes, includes checksum, options, fragmentation | 40 bytes, simplified, no checksum, uses extension headers                                         |
| Address Configuration             | Manual, DHCP, automatic private IP addressing          | SLAAC, DHCPv6, manual configuration                                                               |
| Security                          | Optional, typically via IPsec                          | Mandatory IPsec support                                                                           |
| Fragmentation                     | Routers and hosts can fragment packets                 | Only sending hosts can fragment packets                                                           |
| Broadcasting                      | Supports broadcasting                                  | Uses multicast and anycast, no broadcasting                                                       |
| Quality of Service (QoS)          | Limited support via Type of Service (ToS) field        | Improved support with Flow Label field                                                            |
| Network Address Translation (NAT) | Widely used due to address space limitations           | Generally not needed, supports end-to-end connectivity                                            |
| Maximum packet size               | 65,535 bytes                                           | Up to 4,294,967,295 bytes (But data payload is still 65,535 bytes), see **Jumbo Payload** option. |

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
