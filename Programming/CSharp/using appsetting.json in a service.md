---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [appsettings.json file](appsettings.json%20file.md)
___
 for [ASP.Net](ASP.Net.md) configuration could be set like that:
 
Registering configuration:
```cs
public class Startup
{
    public IConfiguration Configuration { get; }

    public Startup(IConfiguration configuration)
    {
        Configuration = configuration;
    }

    public void ConfigureServices(IServiceCollection services)
    {
        // Bind the configuration section to the MyAppSettings class
        services.Configure<MyAppSettings>(Configuration.GetSection("MyAppSettings"));

        // Add other services
        services.AddControllersWithViews();
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        // Configure the HTTP request pipeline
    }
}
```

Injecting configuration:

```cs
using Microsoft.Extensions.Options;

public class MyService
{
    private readonly MyAppSettings _settings;

    public MyService(IOptions<MyAppSettings> options)
    {
        _settings = options.Value;
    }

    public void PrintSettings()
    {
        Console.WriteLine($"Setting1: {_settings.Setting1}");
        Console.WriteLine($"Setting2: {_settings.Setting2}");
    }
}
```

Configuring services:
```cs
public void ConfigureServices(IServiceCollection services)
{
    services.Configure<MyAppSettings>(Configuration.GetSection("MyAppSettings"));
    services.AddTransient<MyService>(); // Register your service

    services.AddControllersWithViews();
}
```

Building an application:
```cs
using Microsoft.AspNetCore.Hosting;
using Microsoft.Extensions.Hosting;

public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
