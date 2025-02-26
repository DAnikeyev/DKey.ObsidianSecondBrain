---
date_added: 2025-02-26
tags:
  - web
---
Up: [Internet Protocol](Internet%20Protocol.md)
___
 In computing, a firewall is a network security system that monitors and controls incoming and outgoing network traffic based on configurable security rules.

1. Packet Filtering:  
    Firewalls inspect data packets and determine whether to allow or block them based on criteria such as source and destination IP addresses, port numbers, and protocols.
    
2. Stateful Inspection:  
    Beyond basic packet filtering, stateful firewalls maintain context about active connections and can make decisions based on the state of a connection, ensuring that only packets that are part of a valid conversation are allowed.
    
3. Access Control:  
    Firewalls enforce access control policies by determining which types of traffic can pass through. This can include:
    
    - Allowing or denying traffic based on IP address.
    - Specifying which ports or services (e.g., HTTP, HTTPS, FTP) can communicate.
4. Network Address Translation (NAT):  
    Many firewalls implement NAT to hide the internal network structure from the outside world, allowing multiple devices on a local network to share a single public IP address.
    
5. Application Layer Filtering:  
    Advanced firewalls, sometimes known as Next-Generation Firewalls (NGFW), can inspect the actual content of the traffic, which allows for filtering on application protocols (like HTTP, HTTPS, FTP, etc.), detecting potential threats hidden in the payload.
    
6. Intrusion Prevention and Detection:  
    Firewalls may include integrated systems to detect and sometimes prevent suspicious activities, protecting against attacks such as port scanning, denial-of-service (DoS), and other cyber threats.
    
7. Logging and Monitoring:  
    They often provide logging and monitoring features that record attempted access and traffic patterns. This data can be useful for forensic analysis and real-time security management.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
