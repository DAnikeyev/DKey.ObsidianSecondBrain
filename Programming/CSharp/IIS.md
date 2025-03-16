---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [ASP.NET Core](ASP.NET%20Core.md)
___
 Internet Information Services is a server that can be used as a middleware between browser request and [[Kestrel]] or your [WebApplication (ASP)](WebApplication%20(ASP).md)
# Features
## Process Management

- **Application Pool Isolation**: Run multiple websites in separate worker processes
- **Auto-restart**: Automatically restart failed applications
- **Process recycling**: Scheduled restarts to prevent memory leaks
- **Rapid-fail protection**: Prevents repeated crash cycles

## Security Features

- **Windows Authentication**: Integrate with Active Directory
- **Request filtering**: Block malicious requests
- **IP restrictions**: Control access by IP address/range
- **SSL/TLS management**: Centralized certificate handling
- **URL Authorization**: Control access to resources based on URL patterns

## Performance Features

- **Static file compression**: Automatic compression of files
- **Output caching**: Cache responses to improve performance
- **Dynamic compression**: Compress dynamic content on the fly
- **HTTP/2 support**: Enhanced protocol performance
- **Connection limits**: Control concurrent connection numbers

## Administration

- **Graphical management console**: Easy administration through UI
- **Centralized logging**: Unified logging for troubleshooting
- **Remote management**: Administer servers remotely
- **PowerShell integration**: Automate administrative tasks
- **Web Deploy**: Streamlined application deployment

## Advanced Features

- **Request tracing**: Detailed tracing for troubleshooting
- **URL Rewrite**: Powerful URL manipulation rules
- **Failed Request Tracing**: Detailed diagnostics for failed requests
- **Media streaming capabilities**: Optimized for streaming content
- **Application Initialization**: Pre-warm applications on startup

## Enterprise Integration

- **Load balancing integration**: Works with ARR for load balancing
- **Shared configuration**: Centralize configuration across server farms
- **Delegation of administration**: Fine-grained control over who can manage what
- **Resource throttling**: Prevent resource exhaustion
- **Health monitoring**: Monitor application health metrics
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
