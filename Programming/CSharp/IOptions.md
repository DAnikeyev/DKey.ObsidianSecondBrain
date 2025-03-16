---
date_added: 2025-03-14
tags:
  - csharp
---
Up: [DIContainer](DIContainer.md)
___
 IOptions is part of Microsoft's configuration and options framework, primarily used in [ASP.NET Core](ASP.NET%20Core.md) applications to provide a strongly-typed approach to configuration. It helps manage application settings in a type-safe manner and integrates seamlessly with the dependency injection (DI) container.

## Core Interfaces in the Options Pattern

1. **`IOptions<TOptions>`** - Provides access to the current options values
2. **`IOptionsSnapshot<TOptions>`** - Similar to IOptions but is reloaded on every request
3. **`IOptionsMonitor<TOptions>`** - Similar to IOptions but supports change notifications and recomputes options when the underlying source changes


## Usage

If you have appSettings Class:
```cs
public class AppSettings
{
    public string ConnectionString { get; set; }
    public int MaxRetryCount { get; set; }
    public bool EnableLogging { get; set; }
}
```

And appsettings.json
```json
{
  "AppSettings": {
    "ConnectionString": "Server=myServerAddress;Database=myDataBase;User Id=myUsername;Password=myPassword;",
    "MaxRetryCount": 3,
    "EnableLogging": true
  }
}
```

Then configuration can be loaded to [WebApplication (ASP)](WebApplication%20(ASP).md) like that:
```cs

var builder = WebApplication.CreateBuilder(args);

// Configure strongly typed options
builder.Services.Configure<AppSettings>(
    builder.Configuration.GetSection("AppSettings"));
```


Injection:
```cs
public class MyService
{
    private readonly AppSettings _settings;
    
    public MyService(IOptions<AppSettings> options)
    {
        _settings = options.Value; // Access the current options values
    }
    
    public void DoSomething()
    {
        var connectionString = _settings.ConnectionString;
        var maxRetryCount = _settings.MaxRetryCount;
        
        // Use the settings...
    }
}
```


## Benefits of Using IOptions

1. **Strongly typed** - Provides compile-time checking of option names
2. **Dependency injection** - Makes testing easier through mock options
3. **Change notifications** - Can react to configuration changes at runtime
4. **Separation of concerns** - Decouples configuration from the services using it
5. **Multiple sources** - Can load options from various sources (JSON files, environment variables, etc.)

## Best Practices

1. Keep options classes focused on specific functionality areas
2. Use data annotations for validation
3. Consider using IOptionsSnapshot for options that may change
4. Use IOptionsMonitor for long-lived services that need to react to changes
5. Use named options to manage multiple configurations of the same type


## Other usage options:

#### Delegate

 ```csharp
 builder.Services.Configure<MySettings>(options =>
{
    options.Setting1 = "DirectValue1";
    options.Setting2 = 456;
});
 ```

#### Custom configuration source
```cs
public class CustomConfigurationSource : IConfigurationSource
{
    public IConfigurationProvider Build(IConfigurationBuilder builder)
    {
        return new CustomConfigurationProvider();
    }
}

public class CustomConfigurationProvider : ConfigurationProvider
{
    public override void Load()
    {
        // Load your custom configuration data here
        Data = new Dictionary<string, string>
        {
            { "MySettings:Setting1", "CustomValue1" },
            { "MySettings:Setting2", "789" }
        };
    }
}

// Usage in Program.cs
var builder = WebApplication.CreateBuilder(args);
builder.Configuration.Add(new CustomConfigurationSource());
builder.Services.Configure<MySettings>(builder.Configuration.GetSection("MySettings"));
```


#### Environmental variables
You can also configure options using environment variables. ASP.NET Core automatically maps environment variables to configuration keys.

```bash
export MySettings__Setting1=EnvValue1
export MySettings__Setting2=101
```

In your application, you can bind these environment variables to your options class:

```csharp
builder.Services.Configure<MySettings>(builder.Configuration.GetSection("MySettings"));
```


#### **Using In-Memory Collection**
```cs
var inMemorySettings = new Dictionary<string, string>
{
    { "MySettings:Setting1", "InMemoryValue1" },
    { "MySettings:Setting2", "202" }
};

builder.Configuration.AddInMemoryCollection(inMemorySettings);
builder.Services.Configure<MySettings>(builder.Configuration.GetSection("MySettings"));
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
