---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [WebApplication (ASP)](WebApplication%20(ASP).md)
___
 • Acts as a factory or builder for configuring and constructing a WebApplication instance.  
• Introduced in .NET 6, it combines the setup of services, configuration, and middleware registration in a single, streamlined API.  
• It automatically registers default services (like configuration, logging, and dependency injection) and allows you to add custom configuration through its Services property.  
• You can modify host settings (such as command-line arguments and configuration files) directly using the builder's properties before building the final application.

## Example
```cs
var builder = WebApplication.CreateBuilder(args);

// Configure services
builder.Services.AddControllers();
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();

// Configure logging
builder.Logging.AddConsole();

// Add custom configuration
builder.Configuration.AddJsonFile("appsettings.custom.json", optional: true);

// Configure hosting
builder.Host.ConfigureHostOptions(options => {
    options.ShutdownTimeout = TimeSpan.FromSeconds(30);
});

// Build the WebApplication
var app = builder.Build();
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
