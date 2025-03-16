---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [ASP.NET Core](ASP.NET%20Core.md)
___
Middleware in ASP.NET Core is a component that sits in the request processing pipeline. Each middleware component receives an HTTP request, can perform operations on it (such as authentication, logging, or modifying headers), and then passes control to the next middleware in the pipeline. framework [ASP.NET Core](ASP.NET%20Core.md) uses here [[Chain of Responcibility]] design pattern.

It is declared using app.Use method:

```cs
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Http;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

// Custom middleware that logs the request path
app.Use(async (context, next) =>
{
    Console.WriteLine($"Request for: {context.Request.Path}");
    // Call the next middleware in the pipeline
    await next.Invoke();
});

// Define a simple endpoint
app.MapGet("/", () => "Hello, middleware!");

// Start the application
app.Run();
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
