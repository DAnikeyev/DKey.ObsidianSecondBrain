---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [ASP.NET Core](ASP.NET%20Core.md)
___
 Kestrel is a cross-platform, open-source web server for ASP.NET Core applications. It's the default web server implementation included with ASP.NET Core.

## Key Features and Characteristics

1. **Cross-Platform Web Server**:
    
    - Runs on Windows, macOS, and Linux
    - Built on .NET Core's networking stack
2. **High-Performance Server**:
    
    - Built for speed and designed to be efficient
    - Capable of handling thousands of concurrent connections
3. **HTTP Implementation**:
    
    - Supports HTTP/1.1, HTTP/2, and HTTP/3 protocols
    - Provides TLS support for HTTPS
4. **Integration Point**:
    
    - Often used as an edge server (directly exposed to the internet)
    - Can also be used behind a reverse proxy like IIS, Nginx, or Apache
5. **Core Component**:
    
    - Part of the ASP.NET Core stack
    - Hosts the ASP.NET Core middleware pipeline
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
