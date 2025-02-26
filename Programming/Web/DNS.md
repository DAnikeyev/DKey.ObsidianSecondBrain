---
date_added: 2025-02-26
tags:
  - web
---
Up: [Internet Protocol](Internet%20Protocol.md)
___
 The Domain Name System (DNS) is a hierarchical and distributed name service that provides a naming system for computers, services, and other resources on the Internet or other [Internet Protocol](Internet%20Protocol.md) networks.
t associates various information with domain names (identification strings) assigned to each of the associated entities.

Most prominently, it translates readily memorized domain names to the numerical [IP-address](IP-address.md) needed for locating and identifying computer services and devices with the underlying network protocols.

Name servers and a communication protocol implement the Domain Name System. A DNS name server is a server that stores the DNS records for a domain; a DNS name server responds with answers to queries against its database. 

>[!Info]
> If local DNS server doesn't have the information it will query other DNS servers for example managed by **regional internet providers** to find the information. 

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
