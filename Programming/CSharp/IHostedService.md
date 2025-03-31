---
date_added: 2025-03-23
tags:
  - csharp
---
Up: [IServiceCollection](IServiceCollection.md)
___
 IHostedService is an interface for implementing background services in ASP.NET Core applications that run during the application's lifetime.
The interface has two key methods:  
 - StartAsync - Called when the application starts
 - StopAsync - Called during graceful shutdown

```cs
public class MyBackgroundService : BackgroundService  
{  
    private readonly ILogger<MyBackgroundService> _logger;  
    
    public MyBackgroundService(ILogger<MyBackgroundService> logger)  
    {        _logger = logger;  
    }    
    
    protected override async Task ExecuteAsync(CancellationToken stoppingToken)  
    {        _logger.LogInformation("Background service starting");  
        while (!stoppingToken.IsCancellationRequested)  
        {            _logger.LogInformation("Background service running");  
            // Your background logic here  
            await Task.Delay(TimeSpan.FromMinutes(5), stoppingToken);  
        }
    }
}
```

>[!Info]
> BackgroundService implements IHostedService and IDisposable. The ExecuteAsync method is called when the application starts, and it runs until the application is shut down.

### Registering in [WebApplicationBuilder](WebApplicationBuilder.md):
 ```cs
 builder.Services.AddHostedService<MyBackgroundService>();
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
