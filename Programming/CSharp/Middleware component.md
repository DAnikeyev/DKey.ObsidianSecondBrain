---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [ASP.NET Core](ASP.NET%20Core.md)
___
 A middleware component in ASP.NET Core is a software assembly that is inserted into the application's request processing pipeline to handle requests and responses. Each middleware component performs a specific function in the HTTP pipeline and can either:

1. Process the incoming HTTP request
2. Pass the request to the next middleware in the pipeline
3. Short-circuit the pipeline and handle the request itself
4. Process the outgoing HTTP response

Use [IApplcationBuilder](IApplcationBuilder.md) or [[WebApplicationBuilder]]
## Common Built-in Middleware Components

ASP.NET Core includes many built-in middleware components:

1. **Authentication**: Provides authentication support
2. **Authorization**: Handles authorization capabilities
3. **CORS (Cross-Origin Resource Sharing)**: Adds CORS headers to responses
4. **Exception Handler**: Catches exceptions thrown by later middleware
5. **HTTPS Redirection**: Redirects HTTP requests to HTTPS
6. **Static Files**: Serves static files (images, CSS, JavaScript)
7. **Routing**: Routes requests to endpoints
8. **Session**: Establishes and maintains session state
9. **Response Caching**: Provides caching capabilities for responses
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
