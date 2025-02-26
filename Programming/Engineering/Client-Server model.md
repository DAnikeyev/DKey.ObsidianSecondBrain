---
date_added: 2025-02-26
tags:
  - design
---
Up: [Architecture](Architecture.md)
___
The **client–server model** is a structure that partitions tasks or workloads between the providers of a resource or [[service]], called [Server](Server.md), and service requesters, called [[Client]].
 ![Model](Pasted%20image%2020250226053507.png)

## Example

When a [bank](https://en.wikipedia.org/wiki/Bank "Bank") customer accesses [online banking](https://en.wikipedia.org/wiki/Online_banking "Online banking") services with a [web browser](https://en.wikipedia.org/wiki/Web_browser "Web browser") (the client), the client initiates a request to the bank's web server. The customer's [login](https://en.wikipedia.org/wiki/Login "Login") [credentials](https://en.wikipedia.org/wiki/Credential "Credential") are compared against a [database](https://en.wikipedia.org/wiki/Database "Database"), and the webserver accesses that [database server](https://en.wikipedia.org/wiki/Database_server "Database server") as a client. An [application server](https://en.wikipedia.org/wiki/Application_server "Application server") interprets the returned data by applying the bank's [business logic](https://en.wikipedia.org/wiki/Business_logic "Business logic") and provides the [output](https://en.wikipedia.org/wiki/Input/output "Input/output") to the webserver. Finally, the webserver returns the result to the client web browser for display.

In each step of this sequence of client–server message exchanges, a computer processes a request and returns data. This is the request-response messaging pattern. When all the requests are met, the sequence is complete.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
