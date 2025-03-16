---
date_added: 2025-03-13
tags:
  - csharp
  - web
---
Up: [ASP.Net](ASP.Net.md)
___
 IWebHost and IWebHostBuilder are two important interfaces in ASP.NET Core that play distinct roles in running your web application.

Overview:

• IWebHost

- Represents the web host which is responsible for managing the lifetime of the app and its infrastructure.
- It encapsulates the server (such as Kestrel), request processing pipeline, and all middleware.
- Once created and started, the host accepts HTTP requests and processes them via the ASP.NET Core pipeline.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
