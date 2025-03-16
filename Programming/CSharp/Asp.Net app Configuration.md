---
date_added: 2025-03-14
tags:
  - csharp
---
Up: [ASP.NET Core](ASP.NET%20Core.md)
___
 Application settings are typically stored within appsettings.json, or there enviroment overridable version. Configuration is already registered in [Dependency Injection in AspNet](Dependency%20Injection%20in%20AspNet.md) container
 
Besides using [IOptions](IOptions.md) there is a Configuration method of [WebApplicationBuilder](WebApplicationBuilder.md) 

```cs
// Define configuration classes
public class DatabaseOptions
{
    public string ConnectionString { get; set; }
    public int Timeout { get; set; }
}

// In Startup.cs
public void ConfigureServices(IServiceCollection services)
{
    // Use IConfiguration to read and bind config sections
    services.Configure<DatabaseOptions>(Configuration.GetSection("Database"));
    
    // Register services
    services.AddSingleton<IDatabaseService, DatabaseService>();
}

// In a service
public class DatabaseService : IDatabaseService
{
    private readonly DatabaseOptions _options;
    
    // Inject IOptions<T>
    public DatabaseService(IOptions<DatabaseOptions> options)
    {
        _options = options.Value;
    }
    
    public void Connect()
    {
        // Use the strongly-typed options
        var connection = new DbConnection(_options.ConnectionString)
        {
            Timeout = _options.Timeout
        };
    }
}
```

## When to Use Each

- Use **IConfiguration** when:
    - You need access to multiple configuration sections
    - You're working in Startup.cs or Program.cs
    - You need raw configuration values
- Use `IOptions<T>` when:
    
    - You need strongly-typed access to configuration
    - You want design-time safety
    - You want to inject configuration into services
    - You need configuration validation or reloading capabilities
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
